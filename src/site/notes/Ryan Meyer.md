---
{"dg-publish":true,"permalink":"/ryan-meyer/","tags":["People","gardenEntry"],"dg-note-properties":{"aliases":["Ryan","ZZZ"],"tags":["People","gardenEntry"]}}
---

Hosted at https://ryanmeyer-vault.netlify.app

Mechanical Engineering Co-op working under [[People/Ali Heinemann\|Ali]] in [[Definitions/Operations\|Operations]] located in [[Buildings/Feynman\|Feynman]]

## TO DO

| Task                                                                     | Related Project               | Person                     | Notes                                                                                              |
| :----------------------------------------------------------------------- | :---------------------------- | :------------------------- | :------------------------------------------------------------------------------------------------- |
| Schedule design review and confirm PEEK with bath lip temp measurement   | [[My Projects/Calibration Probe Fixture\|Calibration Probe Fixture]] | [[People/David Velazquez\|David]] | Due June. Bath lip temp at 280°C operation needed to confirm PEEK universal suitability            |
| Fix 96 well bracket model and recut                                      | [[My Projects/96 Well Bracket\|96 Well Bracket]]           | [[People/Zack Wermeling\|Zack]]   | Bad original measurements, new ones taken; Z-axis clearance issue for metal tabs also needs fixing |
| Make model for finishing panel                                           | [[Unknown/Pauls Finishing Panel\|Pauls Finishing Panel]]     | [[People/Paul Doll\|Paul]]        | Measurements taken, model not started yet                                                          |
| Redesign models with rabbet joint, update drawings, machine and test fit | [[My Projects/Gel Electrophoresis Tray\|Gel Electrophoresis Tray]]  |                            | Rabbet joint will make epoxy cleaner and stronger — update [[Software/SolidWorks/Solidworks\|Solidworks]] models first             |
| Determine next steps for MA3 Pusher after successful reprint             | [[My Projects/MA3 Pusher Redesign\|MA3 Pusher Redesign]]       |                            | Model fixed, reprinted, fit well — moving forward in process                                       |
| Get part number for filter adapter                                       | [[My Projects/Filter Connection\|Filter Connection]]         |                            |                                                                                                    |
| Remodel lyo clear cover in SolidWorks sheet metal mode                   | [[My Projects/Lyo Clear Cover\|Lyo Clear Cover]]           | [[People/Ali Heinemann\|Ali]]     | 3/8" stock, no top holes, all other dimensions per existing drawing                                |
| Update SolidWorks templates                                              | [[Software/SolidWorks/SolidWorks Templates\|SolidWorks Templates]]      |                            | 3D part templates and drawing templates                                                            |

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

1. [[My Projects/Calibration Probe Fixture\|Calibration Probe Fixture]] (**DUE JUNE**)
	STATUS: Schedule design review with Metrology. Material direction is PEEK universal, pending bath lip temperature measurement at 280°C operation to confirm suitability.
2. [[My Projects/96 Well Bracket\|96 Well Bracket]]
	STATUS: Test fit failed — bad measurements and Z-axis clearance issue with metal tabs. New measurements taken, model needs fixing, recut on Zund and retest with Zack.
3. [[Unknown/Pauls Finishing Panel\|Paul's Finishing Panel]]
	STATUS: Measurements taken, need to make a model.
4. [[My Projects/Gel Electrophoresis Tray\|Gel Electrophoresis Tray]]
	STATUS: Redesign models with rabbet joint, update drawings, machine and test fit.

### Medium Priority

[[My Projects/Lyo Clear Cover\|Lyo Clear Cover]]
	STATUS: Remodel in SolidWorks sheet metal mode. 3/8" acrylic stock (changing from original 8 mm metric). No holes on top per Paul. Drawing exists with current dimensions.

### Low Priority

[[My Projects/MA3 Pusher Redesign\|MA3 Pusher Redesign]]
	STATUS: Model fixed, reprinted, fit well — determine next steps.

[[Software/SolidWorks/SolidWorks Templates\|SolidWorks Templates]]
	STATUS: Update part and drawing templates when time allows.

### Waiting on something

[[My Projects/Mixer Chuck/Mixer Chuck\|Mixer Chuck]]
	STATUS: Shop request submitted 2026-05-11. Waiting on fabrication, then receive, assemble, and deliver.

[[My Projects/Dip Tube Baffle/Dip Tube Baffle Assembly\|Dip Tube Baffle Assembly]]
	STATUS: Drawings delivered to Philip. Waiting on next steps from him.

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
