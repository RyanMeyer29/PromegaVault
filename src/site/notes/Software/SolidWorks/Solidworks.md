---
{"dg-publish":true,"permalink":"/software/solid-works/solidworks/","tags":["Software"],"dg-note-properties":{"tags":["Software"],"aliases":["SW","SolidWorks"],"source":"personal_notes","last_updated":"2026-05-15"}}
---


#Software

SolidWorks is the primary CAD program used at Promega for mechanical design, 2D engineering drawings, and assembly modeling. Current install is **SolidWorks Premium 2022 SP5.0** running on Windows 11. Models and drawings are version-controlled in [[Software/EPDM\|ePDM]] (Engineering Product Data Management), and parts created here flow downstream into shop requests, [[Definitions/Quality/CoC\|CoC]] forms, and eventually production deployment via the [[Definitions/Parts Process/Parts Process\|Parts Process]].

Most day-to-day work falls into a few buckets: building or modifying 3D part and assembly models, producing 2D drawings for fabrication, filling out custom file properties so they propagate into title blocks, and pushing approved files through ePDM for shop or production handoff.

---

## File Types

Part, assembly, and drawing files have both working file types and template counterparts. Template files load automatically on File > New and carry default settings (units, custom properties, sheet format, lighting, planes).

| Working File | Extension | Template | Template Extension |
| :--- | :--- | :--- | :--- |
| Part | .SLDPRT | Part Template | .PRTDOT |
| Assembly | .SLDASM | Assembly Template | .ASMDOT |
| Drawing | .SLDDRW | Drawing Template | .DRWDOT |
| Sheet Format | (embedded) | Sheet Format | .SLDDRT |
| Macro | .SWP | (n/a) | (n/a) |

Promega has 6 active template files: Part, Part_Inch, Part_Metric, Assembly, Assembly_Inch, Assembly_Metric. See [[Software/SolidWorks/SolidWorks Templates\|SolidWorks Templates]] for the current state of template configuration.

---

## How SolidWorks Fits Into the Promega Workflow

The chain from a new part idea to a deployed part:

1. **Model and drawing** are created in SolidWorks. Title block fields pull from custom file properties (SAP#, Equipment#, Description, Material, Finish, DesignedBy, etc.) — fill these out using the [[Software/SolidWorks/SolidWorks Macros/JSON Property Filler\|JSON Property Filler]] macro for new parts, or manually in the file properties dialog.
2. **Drawing review** with [[People/Brian Osterbrink\|Brian]] or [[People/Ali Heinemann\|Ali]] before ePDM check-in. Follow [[Definitions/SolidWorks Drawings/SolidWorks Drawing Standards\|SolidWorks Drawing Standards]] when preparing.
3. **Check into [[Software/EPDM\|ePDM]]** once approved. Drawing # in the title block must match the SAP Material #. See ePDM note for data card conventions.
4. **Submit a [[Definitions/Shop Request\|Shop Request]]** to [[People/Travis Beyer\|Travis]] for parts requiring fabrication, or order via the [[Definitions/Parts Process/Parts Process\|Parts Order Form]] for purchased parts.
5. **Complete a [[Definitions/Quality/CoC\|CoC]]** for new parts once they arrive and pass dimensional inspection. Upload to ePDM in the same folder as the drawing.

Important rule: when renaming or moving files, always do it through ePDM right-click menus, never through Windows Explorer. Renaming or moving via Explorer breaks SolidWorks reference links between parts, assemblies, and drawings.

---

## Add-Ins and Modules

Enabled add-ins live under Tools > Add-Ins. Not all are loaded by default — Premium licenses include everything but you usually only turn on what you need to avoid slow startup.

**Confirmed in use at Promega:**
- **Sheet Metal** — base flange, edge flange, miter flange, hem, jog, fold/unfold. Notes/projects: [[Software/SolidWorks/Solidworks Sheet Metal\|Solidworks Sheet Metal]], [[My Projects/Lyo Clear Cover\|Lyo Clear Cover]], [[My Projects/Falling Vial Bin\|Falling Vial Bin]].

**Likely available but not yet confirmed (let me know which to keep):**
- **Weldments** — for tube/structural frames using standard cross-section profiles
- **Toolbox** — standard hardware library (screws, washers, bearings); useful for assemblies
- **SolidWorks Simulation** — FEA stress analysis on parts and assemblies
- **SolidWorks Flow Simulation** — CFD; mentioned as a future tool for the [[My Projects/Calibration Probe Fixture/Calibration Probe Fixture\|Calibration Probe Fixture]] thermal model but not yet used
- **PhotoView 360** — photorealistic rendering (Premium only)
- **SolidWorks Costing** — manufacturing cost estimation
- **CircuitWorks** — ECAD/MCAD interop, almost certainly not needed
- **Routing** — piping, tubing, cable harness layout; could be relevant for [[My Projects/Dip Tube Baffle/Dip Tube Baffle Assembly\|Dip Tube Baffle Assembly]] style work
- **SolidWorks Inspection** — auto-balloons drawings and generates inspection reports

---

## Drawing Work

The internal standard for 2D drawings lives at [[Definitions/SolidWorks Drawings/SolidWorks Drawing Standards\|SolidWorks Drawing Standards]]. That note is the source of truth for the SolidWorks Drawing Checker skill, which does a pre-review pass before sending drawings to Brian or Ali.

For deeper GD&T questions, the parsed ASME Y14.5-2018 standard is in the vault at `Definitions/SolidWorks Drawings/ASME Y14.5-2018/Parsed/`. Sections are split by topic so you can grep for what you need without opening the full PDF.

Quick reference for the most common drawing rules at Promega:
- Drawing # always matches SAP Material #
- Description and material are ALL CAPS
- Notes section is required on every drawing (engraving callout, sharp edge note)
- Multi-sheet drawings use letter suffixes for sub-parts (e.g. 1016459A, 1016459B) but the SAP Material # stays the parent (1016459)
- Hole callouts use the Hole Callout tool, never Smart Dimension
- Approved By cannot be blank before ePDM check-in

---

## Macros

VBA macros live in `Software/SolidWorks/SolidWorks Macros/`. Install by opening the VBA editor (Tools > Macro > Edit), pasting the code, and saving as .swp. Assign keyboard shortcuts via Tools > Customize > Keyboard, category Macros.

Current macros:
- [[Software/SolidWorks/SolidWorks Macros/JSON Property Filler\|JSON Property Filler]] — reads a JSON file and fills custom file properties in bulk. Run on a new part or assembly to populate SAP#, Equipment#, Description, etc. without manually opening the properties dialog.
- [[Software/SolidWorks/SolidWorks Macros/Symmetric Tolerance\|Symmetric Tolerance]] — applies a symmetric tolerance to a selected dimension on a drawing. Reads document units and converts automatically.
- [[Software/SolidWorks/SolidWorks Macros/Default Lighting Setter\|Default Lighting Setter]] — sets the 4 default lights on a part or assembly template to a captured default preset. Built to fix the [[Software/SolidWorks/SolidWorks Templates\|Promega template]] lighting after it had drifted to a flat, washed-out configuration. Key learning: `IModelDoc2.LockLightToModel` is the only reliable way to programmatically check the Lock-to-Model box in SW 2022.

When building a new macro, the SolidWorks **macro recorder** (Tools > Macro > Record) is by far the most reliable way to find the correct API signatures for your install. Forum examples often use deprecated method versions or wrong parameter counts; the recorder always produces what your specific build accepts.

---

## Templates

Template work is tracked in [[Software/SolidWorks/SolidWorks Templates\|SolidWorks Templates]]. Goal is to have all 6 part/assembly templates plus drawing templates configured so new files don't need cleanup. Current status: lighting fixed via macro, custom properties and reference plane visibility still in progress.

---

## Common Gotchas

These are things that have actually bitten me or are worth knowing in advance.

**Renaming and moving files** — always go through ePDM right-click menus, never Windows Explorer. Explorer renames break the reference graph between parts, assemblies, and drawings. ePDM rename/move propagates references correctly. Process files in this order: parts → assemblies → drawings, all checked out together in one batch.

**Multi-sheet drawings and SAP numbers** — drawing # uses letter suffixes for sub-parts (e.g. 1016459A for handle, 1016459B for head) but the SAP Material # stays the parent number (1016459). The letter suffix is a drawing-side convention, not a SAP-side one.

**Lighting on templates** — the property array setter for lights does not reach the renderer's lock-to-model state in SW 2022. Use `IModelDoc2.LockLightToModel(index, bLock)` if scripting this. Full writeup in [[Software/SolidWorks/SolidWorks Macros/Default Lighting Setter\|Default Lighting Setter]].

**Light icons in different positions than the values suggest** — when "Lock to model" is unchecked, light positions are relative to the camera, not the model. Identical longitude/latitude can produce different physical positions if the lock state differs between two files.

**Macro recorder over forum examples** — when looking for the right API method, record the action manually before searching online. SolidWorks API method names change across versions (e.g. `EditDimensionProperties2` vs `EditDimensionProperties3`) and the recorder gives you the exact call your install supports.

**Custom property tabs** — data cards have two tabs: an @ icon tab (file-level properties) and a named configuration tab (Default for parts, Sheet1 for drawings). Fill out both to be safe. Title block linkage pulls from whichever tab the property is on.

**Find Intersection for virtual sharps** — for chamfered or filleted edges where the dimension should reference the unrounded corner, use the Find Intersection tool to snap to the theoretical sharp point. Don't try to dimension to the rounded edge.

**RealView Graphics** — if your machine can't run RealView (older GPU, integrated graphics), shading and reflections will look flat regardless of light settings. This affects how appearances render but not the underlying file.

---

## Keyboard Shortcuts and Workflow Tips

Standard SolidWorks shortcuts that are worth committing to muscle memory:

| Action | Shortcut |
| :--- | :--- |
| Sketch | S (shortcut bar) or pick from CommandManager |
| Rebuild | Ctrl+B |
| Force rebuild (more thorough) | Ctrl+Q |
| Save | Ctrl+S |
| Save all | Ctrl+Shift+S |
| New | Ctrl+N |
| Open | Ctrl+O |
| Zoom to fit | F |
| Zoom to area | G |
| Rotate view | Middle mouse drag |
| Pan view | Ctrl + middle mouse drag |
| Roll view | Alt + middle mouse drag |
| Normal to face | Click face, then Ctrl+8 |
| Isometric | Ctrl+7 |
| Front | Ctrl+1 |
| Back | Ctrl+2 |
| Left | Ctrl+3 |
| Right | Ctrl+4 |
| Top | Ctrl+5 |
| Bottom | Ctrl+6 |
| Selection filter | F5 |
| Hide/show planes | View > Hide/Show > Planes |
| Toggle origin visibility | View > Hide/Show > Origins |
| Measure | Tools > Evaluate > Measure |

Workflow tips:

- **Use the S key shortcut bar** rather than the ribbon when sketching. Pops up wherever your cursor is, faster than reaching for the CommandManager.
- **Roll-up dimensions** — Smart Dimension can dimension between a line and a circle's center, a line and an arc's midpoint, etc. Hover and watch the snap preview before clicking.
- **Equation-driven dimensions** — for parametric models, drive dimensions with named equations (Tools > Equations). Makes it easy to update related dimensions in one place.
- **Configurations for variants** — if a part has multiple sizes or finishes, use configurations rather than separate files. Custom properties can be configuration-specific.
- **Pack and Go** — File > Pack and Go bundles a file and all its references into a single folder or ZIP. Useful for sending models to vendors or sharing outside ePDM.
- **Reference geometry first** — for complex sketches, lay down reference planes, axes, and points before sketching. Makes the sketch fully defined more easily and the model more robust to changes.
- **Black sketch entities = fully defined** — if any sketch entity is blue, it's under-defined and will move unexpectedly when other dimensions change. Aim for all-black sketches before exiting.
- **Save versions before risky edits** — for complex assemblies or critical drawings, do a Save As with a version suffix before making structural changes. Easier than fighting the undo stack.

> [!info]- Details & Notes
>
> **Version:** SolidWorks Premium 2022 SP5.0
>
> **License:** Promega standard install
>
> **Unknowns:** Confirmed list of enabled add-ins beyond Sheet Metal — let me know which to keep and which to remove from the list above.
>
> **See also:** [[Software/SolidWorks/Solidworks Sheet Metal\|Solidworks Sheet Metal]], [[Software/SolidWorks/SolidWorks Templates\|SolidWorks Templates]], [[Definitions/SolidWorks Drawings/SolidWorks Drawing Standards\|SolidWorks Drawing Standards]], [[Software/EPDM\|EPDM]], [[Definitions/Shop Request\|Shop Request]], [[Definitions/Parts Process/Parts Process\|Parts Process]], [[Definitions/Quality/CoC\|CoC]], [[Software/SolidWorks/SolidWorks Macros/JSON Property Filler\|JSON Property Filler]], [[Software/SolidWorks/SolidWorks Macros/Symmetric Tolerance\|Symmetric Tolerance]], [[Software/SolidWorks/SolidWorks Macros/Default Lighting Setter\|Default Lighting Setter]]
