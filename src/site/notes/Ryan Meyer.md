---
{"dg-publish":true,"permalink":"/ryan-meyer/","tags":["People","gardenEntry"],"dg-note-properties":{"aliases":["Ryan","ZZZ"],"tags":["People","gardenEntry"]}}
---

Hosted at https://ryanmeyer-vault.netlify.app

Mechanical Engineering Co-op working under [[People/Ali Heinemann\|Ali]] in [[Definitions/Operations\|Operations]] located in [[Buildings/Feynman\|Feynman]]

## TO DO

| Task                                                                     | Related Project               | Person                     | Notes                                                                                                         |
| :----------------------------------------------------------------------- | :---------------------------- | :------------------------- | :------------------------------------------------------------------------------------------------------------ |
| Update mixer drawings with the critical dimension                        | [[My Projects/Mixer Chuck/Mixer Chuck\|Mixer Chuck]]  |                            |                                                                                                               |
| Prepare 3 CC draft attachments for Claire meeting (by end of next week)  | [[My Projects/Mixer Chuck/Mixer Chuck\|Mixer Chuck]]  | [[People/Claire Moll\|Claire]]    | Impacted documentation, implementation actions, and testing actions — drafts are fine                        |
| Start CPF drawings, get part numbers, move files to ePDM                 | [[My Projects/Calibration Probe Fixture/Calibration Probe Fixture\|Calibration Probe Fixture]] | [[People/David Velazquez\|David]] | Design review done. Two-jig vs universal still a design call to make while modeling                           |
| Fix 96 well bracket model and recut                                      | [[My Projects/96 Well Bracket\|96 Well Bracket]]           | [[People/Zack Wermeling\|Zack]]   | Bad original measurements, new ones taken; Z-axis clearance issue for metal tabs also needs fixing            |
| Make model for finishing panel                                           | [[Unknown/Pauls Finishing Panel\|Pauls Finishing Panel]]     | [[People/Paul Doll\|Paul]]        | Measurements taken, model not started yet                                                                     |
| Redesign models with rabbet joint, update drawings, machine and test fit | [[My Projects/Gel Electrophoresis Tray\|Gel Electrophoresis Tray]]  |                            | Rabbet joint will make epoxy cleaner and stronger — update [[Software/SolidWorks/Solidworks\|Solidworks]] models first                        |
| Determine next steps for MA3 Pusher after successful reprint             | [[My Projects/MA3 Pusher Redesign\|MA3 Pusher Redesign]]       |                            | Model fixed, reprinted, fit well — moving forward in process                                                  |
| Get part number for filter adapter                                       | [[My Projects/Filter Connection\|Filter Connection]]         |                            |                                                                                                               |
| Update SolidWorks templates                                              | [[Software/SolidWorks/SolidWorks Templates\|SolidWorks Templates]]      |                            | 3D part templates and drawing templates                                                                       |
| Add clearance to bushings                                                | [[My Projects/Calibration Probe Fixture/Calibration Probe Fixture\|Calibration Probe Fixture]] |                            |                                                                                                               |
| Write bend instructions, recut and rebend Lyo Clear Cover                | [[My Projects/Lyo Clear Cover\|Lyo Clear Cover]]           | [[People/Paul Doll\|Paul]]        | PC confirmed as material. Write step-by-step notebook instructions before next fabrication attempt            |
| Follow up with Diego re: speed knob RPM visit at BTC G151C              | [[My Projects/Mixer Chuck/102978 Speed Knob Issue\|102978 Speed Knob Issue]]   | [[People/Diego Lamela\|Diego]]    | Tachometer confirmed available from Ted. Schedule visit, inspect knob, measure RPM                            |

## Projects 
### Base List

```base
views:
  - type: table
    name: Table
    filters:
      or:
        - file.hasTag("My-Projects")
    order:
      - file.name
      - file.backlinks
      - file.folder
      - tags
    sort:
      - property: file.mtime
        direction: DESC
    columnSize:
      file.name: 244
      file.backlinks: 575

```


### High Priority

1. [[My Projects/Calibration Probe Fixture/Calibration Probe Fixture\|Calibration Probe Fixture]] (**DUE JUNE**)
	STATUS: Design review done. Material confirmed as 316L stainless, frame + PEEK bushings. Two-jig vs universal still a design call to make while modeling. Next steps: start drawings, get part numbers, move to ePDM.
2. [[My Projects/96 Well Bracket\|96 Well Bracket]]
	STATUS: Test fit failed — bad measurements and Z-axis clearance issue with metal tabs. New measurements taken, model needs fixing, recut on Zund and retest with Zack.
3. [[Unknown/Pauls Finishing Panel\|Paul's Finishing Panel]]
	STATUS: Measurements taken, need to make a model.
4. [[My Projects/Gel Electrophoresis Tray\|Gel Electrophoresis Tray]]
	STATUS: Redesign models with rabbet joint, update drawings, machine and test fit.

### Medium Priority

[[My Projects/Lyo Clear Cover\|Lyo Clear Cover]]
	STATUS: PC confirmed as material. Two attempts done — acrylic snapped, PC worked but had bowing. Next: write step-by-step bend instructions in notebook before recut.

### Low Priority

[[My Projects/MA3 Pusher Redesign\|MA3 Pusher Redesign]]
	STATUS: Model fixed, reprinted, fit well — determine next steps.

[[Software/SolidWorks/SolidWorks Templates\|SolidWorks Templates]]
	STATUS: Update part and drawing templates when time allows.

### Waiting on something

[[My Projects/Mixer Chuck/Mixer Chuck\|Mixer Chuck]]
	STATUS: Fabrication in progress at Lamarr, shop target 07/29/26. CC prep running in parallel — need 3 draft attachments for Claire by end of next week (impacted documentation, implementation actions, testing actions).

[[My Projects/Dip Tube Baffle/Dip Tube Baffle Assembly\|Dip Tube Baffle Assembly]]
	STATUS: Drawings complete. Waiting on Philip for new SAP numbers for the barb piece and assembly — Nikki working on getting them assigned.

[[My Projects/Label Arm\|Label Arm]]
	STATUS: Waiting on Paul indefinitely. Bottle alignment CoC and drawings still needed when Paul provides them.

[[My Projects/Filter Connection\|Filter Connection]]
	STATUS: Machined part expected mid-June.

Bluebeam access
	STATUS: Waiting on IT.

### Future

### Finished
[[My Projects/Chair Piece\|Chair Piece]]
[[My Projects/KPA Cutting Boards\|KPA Cutting Boards]]
[[My Projects/Septa Mat Excel\|Septa Mat Excel]]
[[My Projects/Falling Vial Bin\|Falling Vial Bin]]
[[My Projects/MicroVu Jig\|MicroVu Jig]]
[[My Projects/Flipper Tray Blocker\|Flipper Tray Blocker]]



## Subsection Hub
- [[Software/Software\|Software]]
