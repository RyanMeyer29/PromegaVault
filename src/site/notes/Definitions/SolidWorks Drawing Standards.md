---
{"dg-publish":true,"permalink":"/definitions/solid-works-drawing-standards/","tags":["Definitions"],"dg-note-properties":{"aliases":["Drawing Standards","Promega Drawing Standards"],"tags":["Definitions"],"source":"personal_notes","last_updated":"2026-04-23"}}
---


#Definitions

Promega's internal standards for [[Software/Solidworks\|SolidWorks]] 2D engineering drawings. Compiled from Promega drawing guidelines and feedback from [[People/Brian Osterbrink\|Brian]] during Mixer Chuck drawing review (2026-04-21). Use this note as a reference when creating or reviewing any drawing before ePDM check-in.

---

## Templates

Use the correct Promega template based on units and part size.

| Template | Units | Sheet Size | When to Use |
| :--- | :--- | :--- | :--- |
| A - Inch | Inches | A (8.5 x 11") | Small or simple inch parts |
| B - Inch | Inches | B (11 x 17") | Standard inch parts — most common |
| A - Metric | Millimeters | A (8.5 x 11") | Small or simple metric parts |
| B - Metric | Millimeters | B (11 x 17") | Standard metric parts |

If the drawing feels cramped on A size, move to B. Do not squeeze dimensions to fit.

---

## Title Block

All fields are required unless noted. Description and material must be ALL CAPS.

| Field | Requirement |
| :--- | :--- |
| Equipment # | Must be filled in (e.g. 134634) |
| SAP Material # | Must be filled in (e.g. 1016437) |
| Drawing # | Must match SAP Material # exactly |
| Description | ALL CAPS (e.g. CHUCK, MIXER, STYLE A) |
| Material | Full material name in ALL CAPS (e.g. 316L STAINLESS STEEL, POLYCARBONATE, DELRIN) |
| Finish | Required (e.g. AS MACHINED, ANODIZED) |
| Drawn By | Engineer initials |
| Approved By | Reviewer initials — must not be blank |
| Date | MM/DD/YYYY format |
| Sheet Count | X OF Y — verify total is accurate |
| Rev | Rev 1 or Rev A — never blank |
| Scale | Must NOT be called out — scale notation is obsolete at Promega |
| General Tolerance | .X ±.02   .XX ±.015   .XXX ±.005   ANGLES ±1° |

Multiple equipment numbers: if a part is used across multiple pieces of equipment, list all equipment numbers in the Notes section (top left of title block area), not in the Equipment # field.

---

## Notes Section

The Notes section is required on every drawing. Minimum content:

Note 1: LABEL PARTS WITH DWG NO. ENGRAVE OR LASER ETCH IN INDICATED POSITION
Note 2: (add as needed for material callouts, special processes, etc.)
Note 3: BREAK ALL SHARP EDGES

Add an engraving location callout directly on the part view (leader pointing to the face or location where the drawing number should be etched). This corresponds to Note 1.

If tiny chamfer dimensions are present only to break sharp edges, remove them and let Note 3 cover it instead.

Stock parts: add a note specifying the vendor part number (e.g. Note 4: STOCK PART — McMaster P/N XXXXXXXX).

---

## Views

- Front view is the primary view and should show the most features
- Isometric placed in upper right — reference only, not dimensioned
- Every included view must show unique information not visible in another view — remove blank or redundant views
- Views must be properly aligned (top view directly above front, right view directly right)
- Section views: labeled SECTION A-A, cutting plane line shown on parent view
- Detail views: labeled DETAIL A, SCALE 2:1 with a circle and letter on the parent view
- Partial/relative views: labeled PARTIAL VIEW — [FACE NAME]
- Crop view borders must not appear on the printed drawing — check File > Print Preview before submitting

---

## Dimensioning

### General Rules

- Every feature must have a dimension — nothing implied or assumed
- All dimensions from one datum corner — do not mix datum origins mid-drawing
- All holes dimensioned from a single datum edge — do not chain-dimension hole to hole
- Use the SolidWorks Hole Callout tool for all hole callouts — not Smart Dimension
- Overall length, width, and height must all be explicitly called out
- No dimension should require math to use — all values directly readable
- No duplicate dimensions
- Leader lines must not cross each other — use detail views if needed
- Dimensions placed outside the part boundary — do not clutter the interior
- Chamfers: .XXX X 45° format
- Radii: R.XXX TYP when all equal (not called out on each corner separately)

### Diameter vs. Radius

- Show diameters on rectangular (profile) views where possible — not on circular/end views
- Replace radius dimensions with diameter dimensions where the center point is not physically accessible on the real part

### Cylinder with a Flat (Set Screw Flat)

Dimension the flat depth from the bottom of the cylindrical surface, not from the center axis. The center is not measurable on the physical part.

### Tolerances

Add tolerances to all diameters that have fit or function requirements. Use +0.001 / -0.000 style (unilateral) for bearing surfaces and press fits. General tolerance block covers everything else.

### Bearing Surfaces

Add a surface finish callout and tight tolerances to any bearing surface. Confirm finish symbol and tolerance values with the machinist if unsure.

### Snap Ring Grooves

Add a detail view showing the groove geometry — dimension one side of the groove only in the detail view. Confirm correct shaft diameter from the snap ring manufacturer data sheet before finalizing. Check for shaft diameter consistency on either side of the groove.

### Tapered Features

Dimension: opening diameter, inside diameter, and angle. Do not dimension the tapered section length — it is not directly measurable.

### Repeated Features

Use TYP callouts to avoid repeating identical dimensions. Example: R0.06 TYP for equal fillets, or 4X for hole patterns.

---

## Hole Callout Formats

All hole callouts require a multiplier prefix (2X, 4X, etc.) even for single holes (1X).

| Hole Type | Format | Example |
| :--- | :--- | :--- |
| Through hole (clearance) | NX Ø[dia] THRU ALL | 2X Ø0.201 THRU ALL |
| Blind hole | NX Ø[dia] ▽[depth] | 4X Ø0.197 ▽0.590 |
| Tapped through | NX [thread spec] THRU ALL | 4X M6x1.0 - 6H THRU ALL |
| Tapped blind | NX [thread spec] ▽[thread depth] Ø[drill dia] ▽[drill depth] | 4X M6x1.0 - 6H ▽0.470 Ø0.197 ▽0.590 |
| Counterbored | NX Ø[dia] THRU ALL ⌴ Ø[cbore dia] ▽[cbore depth] | 8X Ø6.600 THRU ALL ⌴ Ø14.550 ▽4.380 |
| Countersunk | NX Ø[dia] THRU ALL ∨ Ø[csink dia] X [angle]° | 4X Ø0.201 THRU ALL ∨ Ø0.375 X 82° |

---

## Multi-Sheet Drawings

- Name each sheet by its content (e.g. Outside Dimensions / Hole Positions / Flat Pattern)
- Add cross-reference notes on each sheet (e.g. SEE SHEET 2 FOR HOLE DIMENSIONS)
- No dimension duplicated across sheets
- All title blocks show correct X OF Y
- Curve-heavy parts: separate sheets per axis (Vertical / Horizontal / Arc Centers)
- Dense dimension areas: use Detail Views at 2:1 rather than squeezing overlapping leaders

SAP material number note: the SAP Material number is always the parent drawing number. Sub-parts on multi-sheet drawings use letter suffixes on the drawing (e.g. 1016459A, 1016459B) but the SAP Material number stays as the parent (1016459).

---

## Sheet Metal

- Bend angle shown as interior angle (e.g. 45°, not 135°)
- Bend radius must be greater than or equal to material thickness
- Bend note format: UP 45° R0.03 (direction + angle + radius, all present)
- Bend notes generated by SolidWorks tool (Show Sheet Metal Bend Notes checked in view properties)
- Either flat or formed view marked (REF) — not both
- If cut from flat blank: formed view is (REF)
- If formed dimensions are critical: flat pattern is (REF)
- Flat pattern on Sheet 2 with overall flat dimensions and bend lines shown
- Hole callout must appear on the flat pattern sheet

---

## Stock Parts

If a part is purchased stock (unmodified or modified):

Unmodified stock: all dimensions shown as reference only (parenthesis oval style). Show OD, total thickness, and ID as a minimum. No modification dimensions. Add stock note with vendor part number.

Modified stock: show stock dimensions as reference (parenthesis oval). Show modification dimensions as fully dimensioned with tolerances. Add stock note with vendor part number.

---

## Common Return-to-Engineer Errors

| Error | Fix |
| :--- | :--- |
| Rev field blank | Must have Rev 1 or Rev A |
| Scale called out | Remove entirely |
| Description not ALL CAPS | Fix in title block |
| Approved By blank | Required before ePDM check-in |
| Notes section blank | Add Note 1 (engraving) and Note 3 (break sharp edges) at minimum |
| Drawing number does not match SAP number | Must be identical |
| Overall dimension missing | Explicitly call out total L, W, and H |
| Holes chain-dimensioned | Dimension all holes from single datum edge |
| Hole callout missing multiplier prefix | Add 1X, 2X, 4X, etc. |
| Diameter shown on circular view | Move to rectangular/profile view |
| Radius used where center is inaccessible | Replace with diameter |
| Flat measured from center axis | Measure from bottom of cylindrical surface |
| Bend angle shows obtuse angle | Change to interior angle |
| Bend radius less than material thickness | Minimum equals thickness |
| Neither flat nor formed view marked REF | One must be (REF) |
| Crossing leader lines | Use detail views or rearrange dimensions |
| Partial or relative view has no label | Add PARTIAL VIEW — [FACE NAME] |
| Crop view border visible on print | Check File > Print Preview and fix |
| Stock part with no stock note | Add Note with vendor part number |
| Tiny chamfer dims present for sharp edge break only | Remove and cover with Note 3 |

---

> [!info]- Details & Notes
>
> **Sources:** Promega internal drawing guidelines; [[People/Brian Osterbrink\|Brian]] drawing review session, 2026-04-21
>
> **See also:** [[Software/Solidworks\|SolidWorks]], [[Software/EPDM\|ePDM]], [[My Projects/Mixer Chuck Drawing Review 1\|Mixer Chuck Drawing Review 1]], [[People/Brian Osterbrink\|Brian Osterbrink]]
