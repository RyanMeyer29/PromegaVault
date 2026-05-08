---
{"dg-publish":true,"permalink":"/ryan-meyer/","tags":["People","gardenEntry"],"dg-note-properties":{"aliases":["Ryan","ZZZ"],"tags":["People","gardenEntry"]}}
---

Hosted at https://ryanmeyer-vault.netlify.app

Mechanical Engineering Co-op working under [[People/Ali Heinemann\|Ali]] in [[Definitions/Operations\|Operations]] located in [[Buildings/Feynman\|Feynman]]

## TO DO

| Task                                                                     | Related Project              | Person                                            | Notes                                                                                              |
| :----------------------------------------------------------------------- | :--------------------------- | :------------------------------------------------ | :------------------------------------------------------------------------------------------------- |
| Complete drawing updates per Philip's email                              | [[My Projects/Dip Tube Baffle Assembly\|Dip Tube Baffle Assembly]] | [[People/Philip McKeefry\|Philip]]                       | Target: 2026-05-08 — footer, tolerances, file naming, split baffle assembly drawing                |
| Finish drawings edits per Brian's review, get approval                   | [[My Projects/Mixer Chuck\|Mixer Chuck]]              | [[People/Brian Osterbrink\|Brian]]                       | Brian reviewed, edits in progress — approval needed before ePDM rename/move and shop request       |
| Confirm spares quantity with Claire, then submit shop request            | [[My Projects/Mixer Chuck\|Mixer Chuck]]              | [[People/Claire Moll\|Claire]], [[People/Travis Beyer\|Travis]] | Chuck styles fully confirmed — only blocker is spares qty from Claire                              |
| Finish SolidWorks drawings for Brian's parts                             | [[My Projects/Bubble Sensor Tray\|Bubble Sensor Tray]]       | [[People/Brian Osterbrink\|Brian]]                       | One done, one remaining (simple backing plate)                                                     |
| Fix 96 well bracket model and recut                                      | [[My Projects/96 Well Bracket\|96 Well Bracket]]          | [[People/Zack Wermeling\|Zack]]                          | Bad original measurements, new ones taken; Z-axis clearance issue for metal tabs also needs fixing |
| Make model for finishing panel                                           | [[Unknown/Pauls Finishing Panel\|Pauls Finishing Panel]]    | [[People/Paul Doll\|Paul]]                               | Measurements taken, model not started yet                                                          |
| Redesign models with rabbet joint, update drawings, machine and test fit | [[My Projects/Gel Electrophoresis Tray\|Gel Electrophoresis Tray]] |                                                   | Rabbet joint will make epoxy cleaner and stronger — update [[Software/SolidWorks/Solidworks\|Solidworks]] models first             |
| Determine next steps for MA3 Pusher after successful reprint             | [[My Projects/MA3 Pusher Redesign\|MA3 Pusher Redesign]]      |                                                   | Model fixed, reprinted, fit well — moving forward in process                                       |
| Get part number for filter adapter                                       | [[My Projects/Filter Connection\|Filter Connection]]        |                                                   |                                                                                                    |
| Get bottle alignment CoC and drawings                                    | [[My Projects/Label Arm\|Label Arm]]                |                                                   | Waiting on Paul — low priority for him, will be a while                                            |
| Update SolidWorks templates                                              | [[Software/SolidWorks/SolidWorks Templates\|SolidWorks Templates]]     |                                                   | 3D part templates and drawing templates                                                            |
| Fix Claude usage                                                         | [[Software/Anthropic Claude\|Anthropic Claude]]         |                                                   |                                                                                                    |

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

1. [[My Projects/Dip Tube Baffle Assembly\|Dip Tube Baffle Assembly]] (**DUE 2026-05-08**)
	STATUS: Drawing updates required per Philip's April email — footer SAP fields (TBD, Nikki creating numbers), tolerances/units on pickup rod and split baffle, file naming blocked on new SAP numbers, split baffle assembly drawing needs recreating with Promega template.
2. [[My Projects/Mixer Chuck\|Mixer Chuck]] (**TIMELINE IS HIGH PRIORITY**)
	STATUS: Chuck styles fully confirmed — X5P33 (BTC) = Style B, XSS1P33 = Style C, XSS5P33 = Style C (assumed). EV5L25M removed from scope. Drawings with Brian for approval. Spares qty needs follow-up with Claire before shop request can be submitted.
3. [[My Projects/96 Well Bracket\|96 Well Bracket]]
	STATUS: Test fit failed — bad measurements and Z-axis clearance issue with metal tabs. New measurements taken, model needs fixing, recut on Zund and retest with Zack
4. [[Unknown/Pauls Finishing Panel\|Paul's Finishing Panel]]
	STATUS: Measurements taken, need to make a model
5. [[My Projects/Gel Electrophoresis Tray\|Gel Electrophoresis Tray]]
	STATUS: Redesign models with rabbet joint, update drawings, machine and test fit

### Low Priority

[[My Projects/MA3 Pusher Redesign\|MA3 Pusher Redesign]]
	STATUS: Model fixed, reprinted, fit well — determine next steps

[[My Projects/Label Arm\|Label Arm]]
	STATUS: Waiting on Paul — low priority for him, will be a while
		- Do drawings and parts process

### Waiting on something

[[My Projects/Calibration Probe Fixture\|Metrology fixture]]
	STATUS: Meeting with Metrology Wed Apr 22 — prep in progress

[[My Projects/Mixer Chuck\|Mixer Chuck]] (shop request)
	STATUS: Waiting on Brian drawing approval and Claire spares qty confirmation

[[My Projects/Filter Connection\|Filter Connection]]
	STATUS: Machined part expected mid-June

### Future

### Finished
[[My Projects/Chair Piece\|Chair Piece]]
[[My Projects/KPA Cutting Boards\|KPA Cutting Boards]]
[[My Projects/Septa Mat Excel\|Septa Mat Excel]]
[[My Projects/Falling Vial Bin\|Falling Vial Bin]]
[[My Projects/MicroVu Jig\|MicroVu Jig]]



## Subsection Hub
- [[Software/Software\|Software]]
