---
{"dg-publish":true,"permalink":"/software/solid-works/solid-works-macros/json-property-filler/","tags":["Software"],"dg-note-properties":{"tags":["Software"],"source":"personal_notes","last_updated":"2026-05-07"}}
---


#Software

A SolidWorks VBA macro that reads a JSON file and fills custom part or assembly properties automatically. Run this on any open SolidWorks file, paste the path to the matching JSON, and it writes all properties in one shot and saves the file.

JSON files must be flat key/value format. See the Mixer Chuck JSONs below as a reference for the expected structure.

---

## Usage

1. Open the .SLDPRT or .SLDASM file in SolidWorks
2. Run the macro (keyboard shortcut or toolbar button)
3. In File Explorer, right-click the matching JSON and choose Copy as Path
4. Paste into the input box -- quotes are stripped automatically
5. Properties are written and the file is saved

## Setting Up a Keyboard Shortcut

1. Go to Tools > Customize > Keyboard tab
2. Category: Macros
3. Find the macro and assign a key combo (e.g. Ctrl+Shift+P)
4. Click OK

## Setting Up a Toolbar Button

1. Go to Tools > Customize > Commands tab
2. Category: Macros
3. Click New Macro Button, browse to the .swp file
4. Assign an icon and name, drag onto any toolbar

---

## Code

```vb
Sub main()
    Dim swApp As Object
    Dim swModel As Object

    Set swApp = Application.SldWorks
    If swApp Is Nothing Then
        MsgBox "ERROR: Could not connect to SolidWorks.", vbCritical
        Exit Sub
    End If

    Set swModel = swApp.ActiveDoc
    If swModel Is Nothing Then
        MsgBox "ERROR: No active document.", vbCritical
        Exit Sub
    End If

    ' --- Pick JSON via InputBox (paste path or use Copy as Path) ---
    Dim jsonPath As String
    jsonPath = InputBox("Paste the path to the JSON file:" & Chr(10) & "(Copy as Path works fine)", "Select JSON File", "")

    If jsonPath = "" Then
        MsgBox "Cancelled.", vbInformation
        Exit Sub
    End If

    ' Strip surrounding quotes if pasted via Copy as Path
    jsonPath = Trim(jsonPath)
    If Left(jsonPath, 1) = Chr(34) Then jsonPath = Mid(jsonPath, 2)
    If Right(jsonPath, 1) = Chr(34) Then jsonPath = Left(jsonPath, Len(jsonPath) - 1)

    If Dir(jsonPath) = "" Then
        MsgBox "ERROR: File not found." & Chr(10) & jsonPath, vbCritical
        Exit Sub
    End If

    ' --- Read JSON file ---
    Dim fileNum As Integer
    fileNum = FreeFile
    Dim jsonContent As String
    Dim fileLine As String

    Open jsonPath For Input As #fileNum
    Do While Not EOF(fileNum)
        Line Input #fileNum, fileLine
        jsonContent = jsonContent & fileLine
    Loop
    Close #fileNum

    ' --- Write properties ---
    Dim swProps As Object
    Set swProps = swModel.Extension.CustomPropertyManager("")

    Const swCustomInfoText As Integer = 30

    On Error Resume Next
    swProps.Delete "SAP #"
    swProps.Delete "Equipment #"
    On Error GoTo 0

    Dim keys(11) As String
    keys(0) = "SAP#"
    keys(1) = "Drawing#"
    keys(2) = "Description"
    keys(3) = "Material"
    keys(4) = "Finish"
    keys(5) = "DesignedBy"
    keys(6) = "DesignedDate"
    keys(7) = "ApprovedBy"
    keys(8) = "Equipment#"
    keys(9) = "Manufacturer"
    keys(10) = "OldNumber"
    keys(11) = "Revision"

    Dim i As Integer
    Dim resultMsg As String
    resultMsg = "Properties written and file saved!" & Chr(10) & Chr(10)

    For i = 0 To 11
        Dim val As String
        val = ExtractJsonValue(jsonContent, keys(i))
        On Error Resume Next
        swProps.Delete keys(i)
        swProps.Add3 keys(i), swCustomInfoText, val, 0
        On Error GoTo 0
        resultMsg = resultMsg & keys(i) & ": " & val & Chr(10)
    Next i

    swModel.Save
    MsgBox resultMsg, vbInformation, "Promega Properties Set"
End Sub

Function ExtractJsonValue(jsonStr As String, keyName As String) As String
    Dim searchKey As String
    searchKey = """" & keyName & """"

    Dim keyPos As Long
    keyPos = InStr(jsonStr, searchKey)
    If keyPos = 0 Then ExtractJsonValue = "": Exit Function

    Dim colonPos As Long
    colonPos = InStr(keyPos, jsonStr, ":")
    If colonPos = 0 Then ExtractJsonValue = "": Exit Function

    Dim openQuote As Long
    openQuote = InStr(colonPos, jsonStr, """")
    If openQuote = 0 Then ExtractJsonValue = "": Exit Function

    Dim closeQuote As Long
    closeQuote = InStr(openQuote + 1, jsonStr, """")
    If closeQuote = 0 Then ExtractJsonValue = "": Exit Function

    ExtractJsonValue = Mid(jsonStr, openQuote + 1, closeQuote - openQuote - 1)
End Function
```

---

## Mixer Chuck Use Case

JSON property files for all [[My Projects/Mixer Chuck\|Mixer Chuck]] parts. Stored in `My Projects/Mixer Chuck Part JSONs/`. See [[My Projects/Mixer Chuck Drawing Properties\|Mixer Chuck Drawing Properties]] for the full title block reference.

### Chuck Bodies
[[Chuck Style A.json|Chuck Style A]] (SAP 1016437)
[[Chuck Style B.json|Chuck Style B]] (SAP 1016438)
[[Chuck Style C.json|Chuck Style C]] (SAP 1016439)
[[Stop.json|Stop]] (SAP 1016455)
[[Collet Cap.json|Collet Cap]] (SAP 1016457)

### Spanner Tool
[[Spanner Tool Assembly.json|Spanner Tool Assembly]] (SAP 1016458)
[[Spanner Tool Head.json|Spanner Tool Head]] (SAP 1016458A)
[[Spanner Tool Handle.json|Spanner Tool Handle]] (SAP 1016458B)

### Chuck Tool
[[Chuck Tool Assembly.json|Chuck Tool Assembly]] (SAP 1016459)
[[Chuck Tool Handle.json|Chuck Tool Handle]] (SAP 1016459A — DELRIN)
[[Chuck Tool Head.json|Chuck Tool Head]] (SAP 1016459B — 316L SS)

> [!info]- Details & Notes
>
> **See also:** [[Software/SolidWorks/Solidworks\|Solidworks]], [[Software/SolidWorks/SolidWorks Templates\|SolidWorks Templates]], [[My Projects/Mixer Chuck\|Mixer Chuck]], [[My Projects/Mixer Chuck Drawing Properties\|Mixer Chuck Drawing Properties]]
