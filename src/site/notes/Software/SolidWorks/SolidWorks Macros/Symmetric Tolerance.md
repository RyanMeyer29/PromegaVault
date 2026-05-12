---
{"dg-publish":true,"permalink":"/software/solid-works/solid-works-macros/symmetric-tolerance/","tags":["Software"],"dg-note-properties":{"tags":["Software"],"source":"personal_notes","last_updated":"2026-05-08"}}
---


#Software

A SolidWorks VBA macro that applies a symmetric tolerance to a selected dimension on a 2D drawing. Select a dimension, run the macro, type the tolerance value in document units, and hit enter. Eliminates the need to manually open dimension properties, switch to symmetric, and type the value each time.

The macro reads the document's length unit and converts the input to meters automatically, so typing `2` in an mm document gives +/- 2.00, and typing `0.005` in an inch document gives +/- .005.

To install: open the VBA editor in SolidWorks (Tools > Macro > Edit), paste the code, and save as a .swp file. Assign a keyboard shortcut via Tools > Customize > Keyboard, category Macros.

---

## Usage

1. Click a dimension on the drawing to select it
2. Run the macro (keyboard shortcut recommended)
3. Type the tolerance value in document units (e.g. 0.005 or 2) -- no +/- needed
4. Hit Enter -- macro applies symmetric tolerance immediately, no confirmation popup

---

## Code

```vb
Sub main()
    Dim swApp As Object
    Dim swModel As Object
    Dim swSelMgr As Object
    Dim tolVal As Double
    Dim userInput As String
    Dim conversionFactor As Double
    Dim lengthUnit As Long
    Dim retVal As Boolean

    Set swApp = Application.SldWorks
    Set swModel = swApp.ActiveDoc
    Set swSelMgr = swModel.SelectionManager

    If swSelMgr.GetSelectedObjectCount2(-1) = 0 Then
        MsgBox "Click a dimension first.", vbCritical
        Exit Sub
    End If

    userInput = InputBox("Enter symmetric tolerance value:" & Chr(10) & "(in document units -- e.g. 0.005 or 2)", "Symmetric Tolerance", "")

    If userInput = "" Then Exit Sub
    If Not IsNumeric(userInput) Then
        MsgBox "ERROR: Numeric value only.", vbCritical
        Exit Sub
    End If

    tolVal = CDbl(userInput)
    If tolVal <= 0 Then
        MsgBox "ERROR: Value must be greater than zero.", vbCritical
        Exit Sub
    End If

    ' Get document length unit and convert to meters
    lengthUnit = swModel.GetUserPreferenceIntegerValue(5)

    Select Case lengthUnit
        Case 0: conversionFactor = 0.001
        Case 1: conversionFactor = 0.01
        Case 2: conversionFactor = 1
        Case 3: conversionFactor = 0.0254
        Case 4, 5: conversionFactor = 0.3048
        Case 8: conversionFactor = 0.000001
        Case 9: conversionFactor = 0.0000254
        Case Else: conversionFactor = 0.001
    End Select

    Dim tolMeters As Double
    tolMeters = tolVal * conversionFactor

    ' EditDimensionProperties2 - TolType 4 = symmetric, TolMax = value, TolMin = 0
    retVal = swModel.EditDimensionProperties2( _
        4, tolMeters, 0, "", "", _
        True, 9, 2, True, 12, 12, _
        "", "", True, "", "", False)

    swModel.GraphicsRedraw2

    If Not retVal Then
        MsgBox "EditDimensionProperties2 returned False.", vbExclamation
    End If

End Sub
```

---

## Development Notes

The working API call uses `EditDimensionProperties2` (not `EditDimensionProperties3` which is documented but behaves differently). TolType `4` is the correct constant for symmetric tolerance -- not `3` as some forum posts suggest. The 17-parameter signature was confirmed via SolidWorks's built-in macro recorder, which is the most reliable way to find correct API patterns for any version.

---

> [!info]- Details & Notes
>
> **See also:** [[Software/SolidWorks/Solidworks\|SolidWorks]], [[Software/SolidWorks/SolidWorks Macros/JSON Property Filler\|JSON Property Filler]]
