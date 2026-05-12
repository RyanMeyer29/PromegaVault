---
{"dg-publish":true,"permalink":"/definitions/solid-works-drawings/solid-works-drawing-standards/","tags":["Definitions"],"dg-note-properties":{"aliases":["Drawing Standards","Promega Drawing Standards"],"tags":["Definitions"],"source":"personal_notes","last_updated":"2026-04-30"}}
---


#Definitions

Promega's internal standards for [[Software/SolidWorks/Solidworks\|SolidWorks]] 2D engineering drawings. Compiled from Promega drawing guidelines and feedback from in-person reviews with [[People/Brian Osterbrink\|Brian]] and [[People/Ali Heinemann\|Ali]]. Use this note as a reference when creating or reviewing any drawing before ePDM check-in.

This note is the source of truth for the SolidWorks Drawing Checker skill. The skill reads this note at the start of every pre-review and applies its rules section by section. New rules captured during in-person reviews should be added here so the skill picks them up automatically on the next run.

---

## Review Order

When checking a drawing, apply rules in this order. Each section is independent, so a problem in one section should not stop the review of the next.

1. Template and sheet size
2. Title block
3. Notes section
4. Views
5. Dimensioning
6. Hole callouts
7. Multi-sheet specifics (if applicable)
8. Sheet metal specifics (if applicable)
9. Stock parts (if applicable)
10. Final check against common return-to-engineer errors

---

## 1. Templates

Use the correct Promega template based on units and part size.

| Template | Units | Sheet Size | When to Use |
| :--- | :--- | :--- | :--- |
| A - Inch | Inches | A (8.5 x 11") | Small or simple inch parts |
| B - Inch | Inches | B (11 x 17") | Standard inch parts (most common) |
| A - Metric | Millimeters | A (8.5 x 11") | Small or simple metric parts |
| B - Metric | Millimeters | B (11 x 17") | Standard metric parts |

Checklist:
- [ ] Correct units for the part (inch vs. metric)
- [ ] Sheet size is not cramped — if dimensions are squeezed in, move to B size
- [ ] Template matches the standard Promega template (not a generic SolidWorks default)

---

## 2. Title Block

All fields required unless noted. Description and material must be ALL CAPS.

| Field | Requirement |
| :--- | :--- |
| Equipment # | Filled in (e.g. 134634) |
| SAP Material # | Filled in (e.g. 1016437) |
| Drawing # | Matches SAP Material # exactly |
| Description | ALL CAPS (e.g. CHUCK, MIXER, STYLE A) |
| Material | Full material name in ALL CAPS (e.g. 316L STAINLESS STEEL, POLYCARBONATE, DELRIN) |
| Finish | Filled in (e.g. AS MACHINED, ANODIZED) |
| Drawn By | Engineer initials |
| Approved By | Reviewer initials, not blank |
| Date | MM/DD/YYYY format |
| Sheet Count | X OF Y, total accurate |
| Rev | Rev 1 or Rev A, not blank |
| Scale | NOT called out (scale notation is obsolete at Promega) |
| General Tolerance | .X ±.02   .XX ±.015   .XXX ±.005   ANGLES ±1° |

Checklist:
- [ ] Every required field is filled
- [ ] Description and material are ALL CAPS
- [ ] Drawing # matches SAP Material # exactly
- [ ] Approved By is not blank
- [ ] Sheet count X OF Y is accurate
- [ ] Rev is filled in (Rev 1 or Rev A minimum)
- [ ] Scale is NOT called out
- [ ] General tolerance block is present and correct

Multiple equipment numbers: if a part is used across multiple pieces of equipment, list all equipment numbers in the Notes section (top left of title block area), not in the Equipment # field.

---

## 3. Notes Section

The Notes section is required on every drawing.

Required notes (minimum):
- **Note 1:** LABEL PARTS WITH DWG NO. ENGRAVE OR LASER ETCH IN INDICATED POSITION
- **Note 3:** BREAK ALL SHARP EDGES

**Note 2** is reserved for additional callouts as the part requires. Common Note 2 content:
- Material-specific callouts (e.g. heat treat, surface treatment)
- Special process requirements (e.g. passivation, anodizing spec)
- Machining notes (e.g. all surfaces 32 microinch finish unless otherwise specified)

**Note 4 and beyond** for stock parts and other additions:
- Stock parts: STOCK PART — McMaster P/N XXXXXXXX (or other vendor)
- Multiple equipment numbers: list of equipment # if the part spans multiple pieces of equipment

Engraving location callout: add a callout directly on the part view (leader pointing to the face or location where the drawing number should be etched). This corresponds to Note 1.

Sharp edge handling: if tiny chamfer dimensions are present only to break sharp edges, remove them and let Note 3 cover it instead.

Checklist:
- [ ] Note 1 (engraving) is present
- [ ] Note 3 (break sharp edges) is present
- [ ] Engraving location callout is shown on a part view
- [ ] Stock parts have a Note specifying vendor part number
- [ ] No tiny chamfer dimensions used solely for sharp edge break (Note 3 covers it)
- [ ] If part spans multiple equipment, all equipment numbers are listed in the Notes section

---

## 4. Views

Checklist:
- [ ] Front view is the primary view and shows the most features
- [ ] Isometric is placed in upper right (reference only, not dimensioned)
- [ ] Every view shows unique information not visible in another view
- [ ] No blank or redundant views
- [ ] Top view directly above front view
- [ ] Right view directly right of front view
- [ ] When a bottom view is present, it is placed below the front view (not below the top view) — correct vertical order top to bottom on the page is: top view, front view, bottom view
- [ ] Section views labeled SECTION A-A with cutting plane line shown on parent view
- [ ] Detail views labeled DETAIL A, SCALE 2:1, with circle and letter on parent view
- [ ] Partial/relative views labeled PARTIAL VIEW — [FACE NAME]
- [ ] Crop view borders do not appear on the printed drawing (verify in File > Print Preview)

---

## 5. Dimensioning

### General Rules

Checklist:
- [ ] Every feature has a dimension (nothing implied or assumed)
- [ ] All dimensions originate from one datum corner
- [ ] All holes dimensioned from a single datum edge (no chain-dimensioning hole to hole)
- [ ] Hole callouts created with the SolidWorks Hole Callout tool (not Smart Dimension)
- [ ] Overall length, width, and height all explicitly called out
- [ ] No dimension requires math to use (all values directly readable)
- [ ] No duplicate dimensions
- [ ] No leader lines crossing each other (use detail views if needed)
- [ ] Dimensions placed outside the part boundary
- [ ] Chamfers in .XXX X 45° format
- [ ] Equal radii called out as R.XXX TYP, not on each corner separately
- [ ] Ordinate dimension chains do not extend to a total length that is already called out elsewhere — remove the duplicate end segment. If showing the total in a second location genuinely adds clarity (e.g. in a detail view), mark it as a reference dimension using the parenthesis oval style
- [ ] If a fillet is present only to break an edge (not a functional design feature) and it obscures a critical intersection point needed for dimensioning or machining, dimension to the virtual sharp instead — use the Find Intersection tool in SolidWorks to locate where the two theoretical unrounded surfaces meet, and snap the dimension to that point

### Diameter vs. Radius

Checklist:
- [ ] Diameters shown on rectangular (profile) views, not on circular/end views
- [ ] Radius dimensions replaced with diameter dimensions where the center point is not physically accessible on the real part

### Cylinder with a Flat (Set Screw Flat)

Checklist:
- [ ] Flat depth dimensioned from the bottom of the cylindrical surface
- [ ] Flat depth NOT dimensioned from the center axis (center is not measurable on the physical part)

### Tolerances

Checklist:
- [ ] Tolerances added to all diameters with fit or function requirements
- [ ] Unilateral tolerance format (e.g. +0.001 / -0.000) used for bearing surfaces and press fits
- [ ] General tolerance block in title block covers all other dimensions

### Bearing Surfaces

Checklist:
- [ ] Surface finish callout present on each bearing surface
- [ ] Tight tolerances (e.g. +0.001 / -0.000) on each bearing surface
- [ ] Finish symbol value confirmed with the machinist if uncertain

### Snap Ring Grooves

Checklist:
- [ ] Detail view shows the groove geometry
- [ ] Groove dimensioned on one side only in the detail view
- [ ] Shaft diameter confirmed against snap ring manufacturer data sheet
- [ ] Shaft diameter is consistent on both sides of the groove

### Tapered Features

Checklist:
- [ ] Opening diameter dimensioned
- [ ] Inside diameter dimensioned
- [ ] Angle dimensioned
- [ ] Tapered section length NOT dimensioned (it is not directly measurable)

### Chamfers on Shafts

When a shaft has a non-45° chamfer (e.g. 30/60°) that is proportionally small relative to the part diameter, it can be difficult or impossible to tell from the standard profile view which leg of the chamfer is the long one and which is the short one. In these cases, add a detail view at sufficient scale to make the chamfer geometry unambiguous.

A detail view is not required if the chamfer is large enough relative to the part that the long and short legs are clearly distinguishable in the standard view.

Checklist:
- [ ] Any non-45° chamfer that is small relative to part size has a detail view showing the geometry clearly
- [ ] Detail view is at sufficient scale that the long and short legs of the chamfer are unambiguous
- [ ] 45° chamfers or chamfers large enough to read clearly in the standard view do not require a detail view

### Repeated Features

Checklist:
- [ ] TYP callouts used for repeated identical dimensions (e.g. R0.06 TYP for equal fillets)
- [ ] Multiplier prefix used for hole patterns (e.g. 4X, 8X)

---

## 6. Hole Callouts

All hole callouts require a multiplier prefix (1X, 2X, 4X, etc.) even for single holes.

| Hole Type | Format | Example |
| :--- | :--- | :--- |
| Through hole (clearance) | NX Ø[dia] THRU ALL | 2X Ø0.201 THRU ALL |
| Blind hole | NX Ø[dia] ▽[depth] | 4X Ø0.197 ▽0.590 |
| Tapped through | NX [thread spec] THRU ALL | 4X M6x1.0 - 6H THRU ALL |
| Tapped blind | NX [thread spec] ▽[thread depth] Ø[drill dia] ▽[drill depth] | 4X M6x1.0 - 6H ▽0.470 Ø0.197 ▽0.590 |
| Counterbored | NX Ø[dia] THRU ALL ⌴ Ø[cbore dia] ▽[cbore depth] | 8X Ø6.600 THRU ALL ⌴ Ø14.550 ▽4.380 |
| Countersunk | NX Ø[dia] THRU ALL ∨ Ø[csink dia] X [angle]° | 4X Ø0.201 THRU ALL ∨ Ø0.375 X 82° |

Checklist:
- [ ] Every hole callout has a multiplier prefix (1X minimum)
- [ ] Format matches the table above for the hole type
- [ ] Created with SolidWorks Hole Callout tool, not Smart Dimension

---

## 7. Multi-Sheet Drawings

Checklist:
- [ ] Each sheet named by content (e.g. Outside Dimensions / Hole Positions / Flat Pattern)
- [ ] Cross-reference notes added on each sheet (e.g. SEE SHEET 2 FOR HOLE DIMENSIONS)
- [ ] No dimension duplicated across sheets
- [ ] All title blocks show correct X OF Y
- [ ] Curve-heavy parts split across separate sheets per axis (Vertical / Horizontal / Arc Centers)
- [ ] Dense dimension areas use Detail Views at 2:1 rather than overlapping leaders

SAP material number rule: the SAP Material number is always the parent drawing number. Sub-parts on multi-sheet drawings use letter suffixes on the drawing (e.g. 1016459A, 1016459B), but the SAP Material number stays the parent (1016459).

---

## 8. Sheet Metal

Checklist:
- [ ] Bend angle shown as interior angle (e.g. 45°, not 135°)
- [ ] Bend radius is greater than or equal to material thickness
- [ ] Bend note format: UP 45° R0.03 (direction + angle + radius, all present)
- [ ] Bend notes generated by SolidWorks tool (Show Sheet Metal Bend Notes checked in view properties)
- [ ] Either flat or formed view marked (REF), not both
- [ ] If part is cut from a flat blank, the formed view is (REF)
- [ ] If formed dimensions are critical, the flat pattern is (REF)
- [ ] Flat pattern on Sheet 2 with overall flat dimensions and bend lines shown
- [ ] Hole callout appears on the flat pattern sheet

---

## 9. Stock Parts

Two cases: unmodified stock and modified stock.

### Unmodified Stock

Checklist:
- [ ] All dimensions shown as reference only (parenthesis oval style)
- [ ] OD, total thickness, and ID shown at minimum
- [ ] No modification dimensions present
- [ ] Stock note added with vendor part number

### Modified Stock

Checklist:
- [ ] Stock dimensions shown as reference (parenthesis oval style)
- [ ] Modification dimensions fully dimensioned with tolerances
- [ ] Stock note added with vendor part number

---

## 10. Common Return-to-Engineer Errors

Final pass before submission. If any of these are true, fix before sending for review.

| Error | Fix |
| :--- | :--- |
| Rev field blank | Add Rev 1 or Rev A |
| Scale called out | Remove entirely |
| Description not ALL CAPS | Fix in title block |
| Approved By blank | Required before ePDM check-in |
| Notes section blank | Add Note 1 (engraving) and Note 3 (break sharp edges) at minimum |
| Drawing number does not match SAP number | Make identical |
| Overall dimension missing | Explicitly call out total L, W, and H |
| Holes chain-dimensioned | Dimension all holes from a single datum edge |
| Hole callout missing multiplier prefix | Add 1X, 2X, 4X, etc. |
| Diameter shown on circular view | Move to rectangular/profile view |
| Radius used where center is inaccessible | Replace with diameter |
| Flat measured from center axis | Measure from bottom of cylindrical surface |
| Bend angle shows obtuse angle | Change to interior angle |
| Bend radius less than material thickness | Make minimum equal to thickness |
| Neither flat nor formed view marked REF | One must be (REF) |
| Crossing leader lines | Use detail views or rearrange dimensions |
| Partial or relative view has no label | Add PARTIAL VIEW — [FACE NAME] |
| Crop view border visible on print | Check File > Print Preview and fix |
| Stock part with no stock note | Add Note with vendor part number |
| Tiny chamfer dims present for sharp edge break only | Remove and cover with Note 3 |
| Non-45° chamfer on shaft with no detail view | Add detail view at sufficient scale — long and short legs must be unambiguous |
| Bottom view placed below top view instead of below front view | Move below front view — correct order top to bottom is: top view, front view, bottom view |

---

> [!info]- Details & Notes
>
> **Sources:** Promega internal drawing guidelines; in-person drawing reviews with [[People/Brian Osterbrink\|Brian]] and [[People/Ali Heinemann\|Ali]]. This note is updated iteratively after each in-person review — new rules captured during reviews are added here so the SolidWorks Drawing Checker skill applies them on subsequent runs.
>
> **See also:** [[Software/SolidWorks/Solidworks\|SolidWorks]], [[Software/EPDM\|ePDM]], [[People/Brian Osterbrink\|Brian Osterbrink]], [[People/Ali Heinemann\|Ali Heinemann]]
>
> **In-person reviews informing this note:**
> - [[My Projects/Mixer Chuck/Mixer Chuck Drawing Review 1\|Mixer Chuck Drawing Review 1]] — 2026-04-21 (Brian)
> - Bubble sensor mount drawing review — 2026-04-27 (Brian): virtual sharp on tapered angles, projection order with bottom view, ordinate dimension duplicates
> - Mixer chuck shaft drawing review — 2026-04-30 (Brian): detail view required for non-45° chamfers on shafts when proportionally small
