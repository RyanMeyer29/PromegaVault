---
{"dg-publish":true,"permalink":"/software/solid-works/solid-works-macros/default-lighting-setter/","tags":["Software"],"dg-note-properties":{"tags":["Software"],"aliases":["SetLights_ByIndex"],"source":"personal_notes","last_updated":"2026-05-15"}}
---


#Software

A SolidWorks VBA macro that sets the 4 default lights (1 Ambient + 3 Directional) on the active part or assembly template to a captured "novice default" preset. Written to fix the lighting on the [[Software/SolidWorks/SolidWorks Templates\|Promega templates]], which had been configured with flat, washed-out directional lighting that didn't match what a fresh SolidWorks default part renders with.

Run with a .prtdot or .asmdot open. Macro forces an isometric view, locks each directional light to the model via `IModelDoc2.LockLightToModel`, writes the captured values into each light's property array, and forces a graphics redraw and rebuild. Save the template afterward and repeat for each of the 6 templates (Part, Part_Inch, Part_Metric, Assembly, Assembly_Inch, Assembly_Metric).

To install: open the VBA editor in SolidWorks (Tools > Macro > Edit), paste the code, and save as a .swp file. Run it once per template.

---

## Usage

1. Open one template file in SolidWorks (.prtdot or .asmdot)
2. Run the macro (F5 in the VBA editor)
3. Watch the Immediate Window (Ctrl+G) for per-light status, especially `LockLightToModel err = 0` on each directional
4. Open Edit Light on each directional and confirm Lock to Model is checked
5. Visually verify the cube/model rendering matches a fresh File > New > Part
6. Save the template
7. Repeat for the remaining templates

---

## Code

```vb
'------------------------------------------------------------------------------
' SetLights_ByIndex.bas  (v6)
'
' Sets the 4 default lights on the active part or assembly to a captured preset.
' Uses LockLightToModel for the lock flag (single-purpose method, only method
' that actually reaches the renderer's lock state in SW 2022) and the by-index
' LightSourcePropertyValues setter for everything else.
'------------------------------------------------------------------------------
Option Explicit

' VBA type-pun helpers for packing a Long inside a Double.
Private Type DoubleRec
    dValue As Double
End Type

Private Type Int2Rec
    iLower As Long
    iUpper As Long
End Type

' OpenGL light type constants.
Private Const LIGHT_AMBIENT As Long = 1
Private Const LIGHT_DISTANT As Long = 4

' Color: white, packed RGB integer.
Private Const COLOR_WHITE As Long = 16777215

' Lock-to-model value used in the property array.
Private Const LOCK_ON  As Double = 1
Private Const LOCK_OFF As Double = 0

' --- Captured target values per light (from the novice default part dump) -----

' Light 0: Ambient
Private Const L0_BRIGHTNESS As Double = 0
Private Const L0_COLOR_G    As Double = 1
Private Const L0_COLOR_B    As Double = 1
Private Const L0_DX         As Double = 0
Private Const L0_DY         As Double = 0
Private Const L0_DZ         As Double = 0
Private Const L0_AMBIENT    As Double = 0.3
Private Const L0_SPECULAR   As Double = 0

' Light 1: Directional1 (front/upper-right key)
Private Const L1_BRIGHTNESS As Double = 0.3
Private Const L1_COLOR_G    As Double = 1
Private Const L1_COLOR_B    As Double = 1
Private Const L1_DX         As Double = 7.1
Private Const L1_DY         As Double = 7.1
Private Const L1_DZ         As Double = 0
Private Const L1_AMBIENT    As Double = 0.1
Private Const L1_SPECULAR   As Double = 0.3

' Light 2: Directional2 (back-left fill)
Private Const L2_BRIGHTNESS As Double = 0.1
Private Const L2_COLOR_G    As Double = 1
Private Const L2_COLOR_B    As Double = 1
Private Const L2_DX         As Double = -3.4
Private Const L2_DY         As Double = 6.1
Private Const L2_DZ         As Double = -7.1
Private Const L2_AMBIENT    As Double = 0
Private Const L2_SPECULAR   As Double = 0.3

' Light 3: Directional3 (back-left rim)
Private Const L3_BRIGHTNESS As Double = 0.2
Private Const L3_COLOR_G    As Double = 1
Private Const L3_COLOR_B    As Double = 1
Private Const L3_DX         As Double = -9.2
Private Const L3_DY         As Double = 3.4
Private Const L3_DZ         As Double = -1.8
Private Const L3_AMBIENT    As Double = 0
Private Const L3_SPECULAR   As Double = 0.3

' --- Pack helper --------------------------------------------------------------

Private Function PackLongAsDouble(ByVal lVal As Long) As Double
    Dim dr As DoubleRec
    Dim ir As Int2Rec
    ir.iLower = lVal
    ir.iUpper = 0
    LSet dr = ir
    PackLongAsDouble = dr.dValue
End Function

' --- Write the full property array for one light ------------------------------

Private Function ApplyLightArray(swModel As SldWorks.ModelDoc2, _
                                 ByVal i As Long, _
                                 ByVal lightType As Long, _
                                 ByVal brightness As Double, _
                                 ByVal colorG As Double, _
                                 ByVal colorB As Double, _
                                 ByVal dx As Double, _
                                 ByVal dy As Double, _
                                 ByVal dz As Double, _
                                 ByVal ambientVal As Double, _
                                 ByVal specularVal As Double) As Boolean

    Dim vProp As Variant
    vProp = swModel.LightSourcePropertyValues(i)
    If Not IsArray(vProp) Then
        ApplyLightArray = False
        Exit Function
    End If

    vProp(0) = PackLongAsDouble(lightType)
    vProp(1) = brightness
    vProp(2) = LOCK_ON
    vProp(3) = colorG
    vProp(4) = colorB
    vProp(5) = dx
    vProp(6) = dy
    vProp(7) = dz
    vProp(15) = ambientVal
    vProp(16) = specularVal
    vProp(17) = PackLongAsDouble(0)

    swModel.LightSourcePropertyValues(i) = vProp
    ApplyLightArray = True
End Function

' --- Verification --------------------------------------------------------------

Private Sub DumpLight(swModel As SldWorks.ModelDoc2, ByVal i As Long)
    Dim vProp As Variant
    vProp = swModel.LightSourcePropertyValues(i)
    Debug.Print "  AFTER write, light " & i & ":"
    Debug.Print "    name        = " & swModel.GetLightSourceName(i)
    Debug.Print "    prop(1) brt = " & vProp(1)
    Debug.Print "    prop(2) lck = " & vProp(2)
    Debug.Print "    prop(5,6,7) = (" & vProp(5) & ", " & vProp(6) & ", " & vProp(7) & ")"
    Debug.Print "    prop(15) am = " & vProp(15)
    Debug.Print "    prop(16) sp = " & vProp(16)
End Sub

' --- Entry point ---------------------------------------------------------------

Sub main()
    Dim swApp   As SldWorks.SldWorks
    Dim swModel As SldWorks.ModelDoc2

    Set swApp = Application.SldWorks
    Set swModel = swApp.ActiveDoc

    If swModel Is Nothing Then
        MsgBox "No active document. Open a part or assembly template first.", vbExclamation
        Exit Sub
    End If

    Dim modelType As Long
    modelType = swModel.GetType
    If modelType <> swDocPART And modelType <> swDocASSEMBLY Then
        MsgBox "Active document is not a part or assembly. Aborting.", vbExclamation
        Exit Sub
    End If

    Dim nLights As Long
    nLights = swModel.GetLightSourceCount
    Debug.Print "============================================================"
    Debug.Print "SetLights_ByIndex (v6) running on: " & swModel.GetPathName
    Debug.Print "Light count: " & nLights
    Debug.Print "------------------------------------------------------------"

    If nLights < 4 Then
        MsgBox "Expected at least 4 light sources, found " & nLights & ". Aborting.", vbExclamation
        Exit Sub
    End If

    ' Force isometric view for deterministic camera state.
    Debug.Print "Forcing isometric view..."
    swModel.ShowNamedView2 "*Isometric", -1
    swModel.ViewZoomtofit2

    ' --- STEP 1: Lock each directional light using LockLightToModel ---
    Debug.Print "Locking directionals via LockLightToModel..."
    On Error Resume Next
    swModel.LockLightToModel 1, True
    Debug.Print "  Light 1 LockLightToModel(True) err = " & Err.Number
    Err.Clear
    swModel.LockLightToModel 2, True
    Debug.Print "  Light 2 LockLightToModel(True) err = " & Err.Number
    Err.Clear
    swModel.LockLightToModel 3, True
    Debug.Print "  Light 3 LockLightToModel(True) err = " & Err.Number
    Err.Clear
    On Error GoTo 0

    ' --- STEP 2: Write the full property array for each light ---
    Dim ok0 As Boolean, ok1 As Boolean, ok2 As Boolean, ok3 As Boolean

    Debug.Print "Light 0 (Ambient) - property array write..."
    ok0 = ApplyLightArray(swModel, 0, LIGHT_AMBIENT, _
                          L0_BRIGHTNESS, L0_COLOR_G, L0_COLOR_B, _
                          L0_DX, L0_DY, L0_DZ, _
                          L0_AMBIENT, L0_SPECULAR)
    Debug.Print "  result = " & ok0

    Debug.Print "Light 1 (Directional1) - property array write..."
    ok1 = ApplyLightArray(swModel, 1, LIGHT_DISTANT, _
                          L1_BRIGHTNESS, L1_COLOR_G, L1_COLOR_B, _
                          L1_DX, L1_DY, L1_DZ, _
                          L1_AMBIENT, L1_SPECULAR)
    Debug.Print "  result = " & ok1

    Debug.Print "Light 2 (Directional2) - property array write..."
    ok2 = ApplyLightArray(swModel, 2, LIGHT_DISTANT, _
                          L2_BRIGHTNESS, L2_COLOR_G, L2_COLOR_B, _
                          L2_DX, L2_DY, L2_DZ, _
                          L2_AMBIENT, L2_SPECULAR)
    Debug.Print "  result = " & ok2

    Debug.Print "Light 3 (Directional3) - property array write..."
    ok3 = ApplyLightArray(swModel, 3, LIGHT_DISTANT, _
                          L3_BRIGHTNESS, L3_COLOR_G, L3_COLOR_B, _
                          L3_DX, L3_DY, L3_DZ, _
                          L3_AMBIENT, L3_SPECULAR)
    Debug.Print "  result = " & ok3

    ' --- STEP 3: Re-affirm lock state after property writes ---
    Debug.Print "Re-affirming lock state after property writes..."
    On Error Resume Next
    swModel.LockLightToModel 1, True
    swModel.LockLightToModel 2, True
    swModel.LockLightToModel 3, True
    Err.Clear
    On Error GoTo 0

    ' --- STEP 4: Force commit ---
    swModel.GraphicsRedraw2
    swModel.EditRebuild3
    swModel.ForceRebuild3 False
    swModel.SetSaveFlag

    Debug.Print "------------------------------------------------------------"
    Debug.Print "Verification dump:"
    DumpLight swModel, 0
    DumpLight swModel, 1
    DumpLight swModel, 2
    DumpLight swModel, 3
    Debug.Print "============================================================"

    Dim msg As String
    msg = "Lighting applied (v6: LockLightToModel then property array)." & vbCrLf & _
          "  Light 0: " & IIf(ok0, "OK", "FAIL") & vbCrLf & _
          "  Light 1: " & IIf(ok1, "OK", "FAIL") & vbCrLf & _
          "  Light 2: " & IIf(ok2, "OK", "FAIL") & vbCrLf & _
          "  Light 3: " & IIf(ok3, "OK", "FAIL") & vbCrLf & vbCrLf & _
          "Open Edit Light on each directional and verify Lock to Model " & _
          "is now checked. Compare to default visually. Save when done."
    MsgBox msg, vbInformation, "SetLights_ByIndex"

End Sub
```

---

## Development Notes

The big finding from building this macro: in SolidWorks 2022, the `LightSourcePropertyValues(i) = vProp` by-index setter writes the 19-element light property array correctly (you can dump it back and see the values land), but it does NOT reach the renderer's internal Lock-to-Model state. Same for `SetDirectionLightProperties(Name, ..., Fixed:=True, ...)` and `SetLightSourcePropertyValuesVB(...)` -- both either silently fail to set the lock flag or return False outright.

The only method that actually checks the Lock to Model box from VBA is the dedicated single-purpose `IModelDoc2.LockLightToModel(index, bLock)`. It takes a light index (0-based, same indexing as `GetLightSourceName` and the property array) and a Boolean. Call it before writing the rest of the properties. The macro also re-calls it after the property writes as belt-and-braces, since some macros report that array writes can reset the lock flag.

The method is undocumented on the current SolidWorks Help site (the help pages render with JavaScript and don't surface in static fetches), but it has existed in `IModelDoc2` since at least SW 2010 per an Eng-Tips forum macro that uses it alongside `SetLightSourcePropertyValuesVB`. The existence of a single-purpose method alongside the general property-array setter is the API team's de facto acknowledgment that lock state isn't reliably routable through the general setter.

### Light property array layout (confirmed for SW 2022)

The array returned by `LightSourcePropertyValues(i)` is 19 doubles indexed 0..18. Confirmed slots:
- prop(0): light type, packed as Long inside a Double via `LSet` trick (1 = ambient, 4 = directional)
- prop(1): brightness / diffuse
- prop(2): locked-to-model (1 = yes) -- value lands but does not reach renderer; use `LockLightToModel` instead
- prop(3), prop(4): color G, B normalized (no slot for R; only white tested)
- prop(5), prop(6), prop(7): direction X, Y, Z (for directional lights)
- prop(8) through prop(14): all zero on default lights, purpose unknown
- prop(15): ambient intensity
- prop(16): specularity
- prop(17): bDisable flag, packed as Long inside a Double (0 = enabled)
- prop(18): unknown, zero on defaults

### What did NOT work (failed approaches, for posterity)

- v1: single-pass array write. Values land in array but renderer ignores lock state.
- v2: two-pass write (lock first, then angles, with rebuild between). Caused renderer to normalize Light 1's direction vector down to ~0.29 magnitude.
- v3: single-pass with isometric view forced. Same as v1.
- v4: forced lock-state transition by writing prop(2)=0 then prop(2)=1 with rebuild between. Renderer still ignored.
- v5: typed setters `SetAmbientLightProperties` and `SetDirectionLightProperties` with renamed-to-unique light names. Returned True but renderer still ignored the lock state.

### Why the rendering was flat before the fix

If Lock to Model is unchecked on a directional light, the light is interpreted relative to the camera, not the model. The captured target values (longitude/latitude pairs designed for model-space) end up pointing in arbitrary directions in camera-space, which collapses the 3-point lighting setup into nearly-identical face shading. The result is the washed-out "flat" look that doesn't match a fresh File > New > Part.

---

> [!info]- Details & Notes
>
> **See also:** [[Software/SolidWorks/SolidWorks Templates\|SolidWorks Templates]], [[Software/SolidWorks/Solidworks\|Solidworks]], [[Software/SolidWorks/SolidWorks Macros/Symmetric Tolerance\|Symmetric Tolerance]], [[Software/SolidWorks/SolidWorks Macros/JSON Property Filler\|JSON Property Filler]]
