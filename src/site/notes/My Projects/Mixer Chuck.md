---
{"dg-publish":true,"permalink":"/my-projects/mixer-chuck/","tags":["My-Projects"],"dg-note-properties":{"aliases":["Mixer Chukc"],"tags":["My-Projects"],"last_updated":"2026-04-21"}}
---

#My-Projects

**Related Areas:** [[Lines/MA2\|MA2]], [[Buildings/Lamarr\|Lamarr]]
**Drawing review notes:** [[My Projects/Mixer Chuck Drawing Review 1\|Mixer Chuck Drawing Review 1]]

---

## 📋 Project Overview

There are 12 total mixers across BTC (5x X5P33, 1x EV5L25M), RDC (1x XSS1P33), and IVD (4x XSS1P33, 1x XSS5P33). The goal of this project is to redesign the mixer chuck system. The current collet-style redesign (done by [[People/Travis Beyer\|Travis Beyer]]) uses a collet-style chuck — the same approach CNC machines use to hold tooling. This design can hold multiple shaft sizes, uses parts easily sourced from [[Fabrication/McMaster-Carr\|McMaster-Carr]], and has no internal water exposure.

[[Definitions/Change Control\|CCs]] are confirmed as required for the IVD mixers. [[People/Ted Lenoch\|Ted Lenoch]] and [[People/Garrett Tschanz\|Garrett]] are the main contacts for organizing CCs and associated downtime. Reach out to them early before installation begins.

**Timeline:** Shop request pending chuck style confirmation with [[People/Jacob Holze\|Jake]]. Parts process and installation to follow.

---

## ✅ My Action Items (Ryan)

### Phase 1 — Drawings (do first)

- [ ] Fix all drawing files to move equipment numbers into the Notes section of the title block (top left) — currently in a separate area
- [ ] Get drawings approved by [[People/Ali Heinemann\|Ali]] or [[People/Brian Osterbrink\|Brian]] before moving files

#### Drawing Notes Section Checklist

For each drawing below, open in [[Software/Solidworks\|Solidworks]] and move the equipment numbers into the Notes section in the title block (top left).

- [x] Chuck, Mixer, Style A (SAP 1016437)
- [x] Chuck, Mixer, Style B (SAP 1016438)
- [x] Chuck, Mixer, Style C (SAP 1016439)
- [x] Stop, Mixer Chuck, Stainless Steel (SAP 1016455)
- [x] Collet, Mixer Chuck, Stainless Steel (SAP 1016456)
- [x] Collet Cap, Mixer Chuck, Stainless Steel (SAP 1016457)
- [x] Tool, Spanner, Mixer Chuck, Stainless Steel (SAP 1016458)
- [x] Chuck Tool, Mixer, Stainless/Delrin (SAP 1016459)

### Phase 2 — ePDM (after approval)

- [ ] Rename each file to its SAP part number
- [ ] Move each file to the correct [[Software/EPDM\|ePDM]] folder (keep [[Software/Solidworks\|Solidworks]] references intact)

#### ePDM Rename and Move Process

Do everything through [[Software/EPDM\|ePDM]], not Windows Explorer. Renaming or moving through Explorer breaks [[Software/Solidworks\|Solidworks]] references.

1. Check out all affected files in [[Software/EPDM\|ePDM]] first — parts, assemblies, and drawings together in one batch. Files must be checked out before they can be renamed or moved.
2. Right-click the file in [[Software/EPDM\|ePDM]] and use Rename to change the filename to the SAP part number.
3. After renaming, right-click and use Move to put it in the correct folder.
4. [[Software/EPDM\|ePDM]] will prompt to update references — confirm yes on all of them.
5. Check everything back in once all renames and moves are complete.

Process files in this order: parts first, then assemblies, then drawings. This follows the reference chain so each update propagates correctly before the next file type looks for it.

### Phase 3 — Shop Request (waiting on Jake/Claire)

- [ ] Complete disassembly with [[People/Jacob Holze\|Jake]] to confirm X5P33 chuck style and re-inspect EV5L25M
- [ ] Confirm which mixers Jake is removing from scope (changes quantities significantly)
- [ ] Loop in [[People/Claire Moll\|Claire]] once chuck styles are confirmed
- [ ] Receive final numbers and submit shop request to [[People/Travis Beyer\|Travis]]

Working order quantity is 18 (6 per style) plus 2 extra hardware sets for Jake's incomplete assemblies. IVD mixers confirmed as Style C. X5P33 BTC and EV5L25M still unknown — see Updates (2026-04-21) for full disassembly context. Jake is back Wed 2026-04-23, disassembly date TBD.

### Phase 4 — Parts Process (after parts arrive)

- [ ] Complete [[Definitions/CoC\|CoCs]] for all parts
- [ ] Submit CoCs to [[Software/EPDM\|ePDM]]
- [ ] Hand off parts to relevant production areas (process TBD)

### Completed

- [x] Confirm we have accurate models for all mixers
- [x] Determine if chuck needs to be different per mixer
- [x] Confirm 3 tools are accounted for every mixer: counter-rotation tool, chuck tightener, and chuck itself
- [x] Create 2D drawings for all parts
- [x] Confirm drawings are accurate and complete
- [x] Get SAP part numbers created (1016437–1016439, 1016455–1016459)
- [x] Submit additional parts order via Parts Order Form — approved 2026-03-25, SLOC 6072 (Feynman)
- [x] Contact [[Definitions/EHS\|EHS]] re: purchase part for spares
- [x] Get SAP numbers for each mixer (IVD: [[People/Garrett Tschanz\|Garrett]]; BTC: [[Sean During\|Sean]])
- [x] Talk to [[People/Nikki Masterson\|Nikki]] — parts process Excel file obtained

---

## 🔧 Background & Design Context

### Problem with Old Design

The original chuck allowed impellers to fall out during mixing. A key system redesign between the impeller and chuck was attempted, but caused metal shavings and round-out issues over time.

### Current Design (Travis's Collet-Style)

[[People/Travis Beyer\|Travis Beyer]] redesigned the chuck to match the collet style used by CNC machines for holding tooling. Travis has 3 different options modeled.

**Advantages:**

- Holds multiple shaft sizes
- Easy to source replacement parts from [[Fabrication/McMaster-Carr\|McMaster-Carr]]
- Sealed — no water internally

### Motor Mount Note

Mixers differ in how the motor mounts to the gear box. The manufacturer ships them in 3 different configurations — this needs to be accounted for in the chuck design.

### SAP & Drawings

[[People/Aaron Vergiels\|Aaron Vergiels]] originally obtained the list of mixer equipment. [[People/Travis Beyer\|Travis Beyer]] designed the 3 chuck styles and built the SolidWorks models — he was given dimensions by someone else and cannot match styles to mixers without physical inspection. SAP part numbers 1016437–1016439 and 1016455–1016459 are assigned. See drawing review note for drawing correction checklist: [[My Projects/Mixer Chuck Drawing Review 1\|Mixer Chuck Drawing Review 1]].

---

## 📝 Updates (2026-03-30)

BTC urgent safety issue resolved — [[People/Travis Beyer\|Travis Beyer]] delivered a replacement chuck (Style B) to [[Buildings/BTC\|BTC]] last week per [[People/Jacob Holze\|Jacob]]. [[People/Kent Toepfer\|Kent]] had flagged this as an open safety issue and was tracking status.

---

## 📝 Meeting Notes (2026-03-17)

Schedule a design review meeting with [[People/Kent Toepfer\|Kent]] (he is out next week — plan around his availability). Talk to [[People/Nikki Masterson\|Nikki]] to get her parts process Excel file.

SAP numbers are needed for each mixer. Contacts by area:
- [[People/Garrett Tschanz\|Garrett]] — mixers with [[Definitions/In Vitro Dispensing\|IVD]]
- [[People/Sean Doering\|Sean]] — mixers at [[Buildings/BTC\|BTC]]

### Action Items
- [x] Schedule design review meeting with [[People/Kent Toepfer\|Kent]]
- [x] Talk to [[People/Nikki Masterson\|Nikki]] — get parts process Excel file
- [x] Talk with [[People/Sean Doering\|Sean]] regarding [[Software/SAP\|SAP]] numbers for [[Buildings/BTC\|BTC]] mixers
- [x] Get SAP numbers for each mixer (coordinate with [[People/Garrett Tschanz\|Garrett]] for [[Definitions/In Vitro Dispensing\|IVD]] mixers, [[People/Sean Doering\|Sean]] for [[Buildings/BTC\|BTC]] mixers)


## 🔩 Parts & SAP Numbers by Equipment

> Drawing # = SAP Material # (per title block convention). Only diverges if a part has multiple drawings/sheets.
> Chuck Style per equipment number TBD — to be confirmed and filled in.
> Order quantities are based on 18 assemblies (6 per style, guaranteeing coverage across all 3 mixer models) plus 2 extra hardware sets for Jake's incomplete assemblies at his desk. Jake's assemblies already have chuck bodies, so no extra chucks are ordered. Stop qty is doubled since there are 2 per assembly. Spanner Tool qty confirmed to match Chuck Tool.

#### Mixers list:

##### Table
###### BTC

| Equipment # | Equipment - Desc. | Functional Loc.  | Func. Loc. - Desc.  | Created On     | Created By | BOM Component | BOM Comp. Desc.                          | Quantity  |
| ----------- | ----------------- | ---------------- | ------------------- | -------------- | ---------- | ------------- | ---------------------------------------- | --------- |
| 102956      | Mixer, X5P33      | MAD-BTC-G153     | MagaZorb Production | 01/16/2015     | SKASTE     | 1003831       | Drive Shaft Hardware Kit (Lightnin Mixr) | 1         |
| 112142      | Mixer, X5P33      | MAD-BTC-G151C    | Bay 3               | 05/05/2020     | GMCCAULE   | 1010478       | Impellor, 10", A-100                     | 1.000     |
| 122278      | Mixer, X5P33      | MAD-BTC-G130     | Hallway             | 01/19/2021     | GMCCAULE   | 1010478       | Impellor, 10", A-100                     | 1.000     |
| 122277      | Mixer, X5P33      | MAD-BTC-G130     | Hallway             | 01/19/2021     | GMCCAULE   | 1010478       | Impellor, 10", A-100                     | 1.000     |
| ==102943==  | ==Mixer, X5P33==  | ==MAD-BTC-G152== | ==Tank Cleaning==   | ==04/16/2014== | ==SKASTE== | ==1011007==   | ==Set Screw (Lamarr)==                   | ==5.000== |
| 102978      | Mixer, EV5L25M    | MAD-BTC-G151C    | Bay 3               | 03/07/2018     | GMCCAULE   | 1008762       | Ball Bearing, Mtd, 2 Bolt Flange, NFL205 | 1.000     |
|             |                   |                  |                     |                |            |               |                                          |           |
###### RDC
| Equipment # | Equipment - Desc.  | Functional Loc.  | Func. Loc. - Desc.       | Created On  | Created By | BOM Component | BOM Comp. Desc.   | Quantity |
| ----------- | ------------------ | ---------------- | ------------------------ | ----------- | ---------- | ------------- | ----------------- | -------- |
| 102883      | Mixer, XSS1P33     | MAD-RDC-204      | Large Scale Formulation  | 10/11/2017  | GMCCAULE   | 1008931       | Mixer, SS, 1:1    | 1        |
###### IVD
| Equipment # | Equipment - Desc.                 | Functional Loc. | Func. Loc. - Desc.   | Created On | Created By | BOM Component | BOM Comp. Desc. | Quantity                                 |       |
| ----------- | --------------------------------- | --------------- | -------------------- | ---------- | ---------- | ------------- | --------------- | ---------------------------------------- | ----- |
| 113417      | GMP Resin Mixer, Lightnin XSS1P33 | MAD-GMP-2210    | Small Compounding #1 | 07/30/2020 | GMCCAULE   | 500000005448  | 1003831         | Drive Shaft Hardware Kit (Lightnin Mixr) | 1.000 |
| 113418      | GMP Resin Mixer, Lightnin XSS1P33 | MAD-GMP-2215    | Small Compounding #2 | 07/30/2020 | GMCCAULE   | 500000005448  | 1003831         | Drive Shaft Hardware Kit (Lightnin Mixr) | 1.000 |
| 117266      | GMP Resin Mixer, Lightnin XSS1P33 | MAD-GMP-2232    | Compound Resin RM #3 | 11/26/2018 | GMCCAULE   | 500000005448  | 1003831         | Drive Shaft Hardware Kit (Lightnin Mixr) | 1.000 |
| 127950      | GMP Resin Mixer, Lightnin XSS5P33 | MAD-GMP-2224    | Large Compounding #1 | 07/12/2022 | GMCCAULE   | 500000005448  | 1003831         | Drive Shaft Hardware Kit (Lightnin Mixr) | 1.000 |
| 120019      | GMP Resin Mixer, Lightnin XSS1P33 | MAD-GMP-2215    | Small Compounding #2 | 07/30/2020 | GMCCAULE   | 500000005448  | 1003831         | Drive Shaft Hardware Kit (Lightnin Mixr) | 1.000 |

---

### Chuck Bodies by Equipment

| Equipment # | Area            | Chuck Style | SAP Material #              |
| :---------- | :-------------- | :---------- | :-------------------------- |
| 102956      | BTC             | Unknown — needs Jake (sun gear, can't access alone) | 1016437 / 1016438 / 1016439 |
| 112142      | BTC             | Unknown — needs Jake (sun gear, can't access alone) | 1016437 / 1016438 / 1016439 |
| 122278      | BTC             | Unknown — needs Jake (sun gear, can't access alone) | 1016437 / 1016438 / 1016439 |
| 122277      | BTC             | Unknown — needs Jake (sun gear, can't access alone) | 1016437 / 1016438 / 1016439 |
| 102943      | BTC             | Unknown — needs Jake (sun gear, can't access alone) | 1016437 / 1016438 / 1016439 |
| 102978      | BTC             | Likely Style C (unconfirmed — needs re-inspection with Jake) | 1016437 / 1016438 / 1016439 |
| 102883      | [[Buildings/Arnold\|RDC]] | Style C (assumed — same model as XSS1P33 IVD units) | 1016437 / 1016438 / 1016439 |
| 113417      | IVD             | Style C (confirmed — Lovejoy/spider coupling, inspected 2026-04-20) | 1016439 |
| 113418      | IVD             | Style C (confirmed by model match) | 1016439 |
| 117266      | IVD             | Style C (confirmed by model match) | 1016439 |
| 127950      | IVD             | Likely Style C (unconfirmed — XSS5P33, assumed same as XSS1P33) | 1016437 / 1016438 / 1016439 |
| 120019      | IVD             | Style C (confirmed by model match) | 1016439 |

### All Parts — SAP Reference

| SAP Material # | Description | Order Qty | BOM Equipment # | BOM Qty |
| :------------- | :---------- | :-------- | :-------------- | :------ |
| 1016437        | Chuck, Mixer, Style A | — | 102956, 112142, 122278, 122277, 102943, 102978, 102883, 113417, 113418, 117266, 127950, 120019 | 1 |
| 1016438        | Chuck, Mixer, Style B | — | 102956, 112142, 122278, 122277, 102943, 102978, 102883, 113417, 113418, 117266, 127950, 120019 | 1 |
| 1016439        | Chuck, Mixer, Style C | — | 102956, 112142, 122278, 122277, 102943, 102978, 102883, 113417, 113418, 117266, 127950, 120019 | 1 |
| 1016455        | Stop, Mixer Chuck, Stainless Steel | 40 | 102956, 112142, 122278, 122277, 102943, 102978, 102883, 113417, 113418, 117266, 127950, 120019 | 2 |
| 1016456        | Collet, Mixer Chuck, Stainless Steel | 20 | 102956, 112142, 122278, 122277, 102943, 102978, 102883, 113417, 113418, 117266, 127950, 120019 | 1 |
| 1016457        | Collet Cap, Mixer Chuck, Stainless Steel | 20 | 102956, 112142, 122278, 122277, 102943, 102978, 102883, 113417, 113418, 117266, 127950, 120019 | 1 |
| 1016458        | Tool, Spanner, Mixer Chuck, Stainless Steel | 20 | 102956, 112142, 122278, 122277, 102943, 102978, 102883, 113417, 113418, 117266, 127950, 120019 | 1 |
| 1016459        | Chuck Tool, Mixer, Stainless/Delrin | 20 | 102956, 112142, 122278, 122277, 102943, 102978, 102883, 113417, 113418, 117266, 127950, 120019 | 1 |

---

## 📝 Updates (2026-04-21)

Chuck style mapping is now partially confirmed following disassembly sessions on 2026-04-20 with [[People/Alex Rabbach\|Alex]] (IVD) and independently at BTC.

XSS1P33 (inspected 113417 with Alex) — uses a Lovejoy/spider coupling (jaw coupling with rubber damper between two star-shaped halves). The internal shaft has a large central hole with one flat side for a set screw. This matches Style C. All other XSS1P33 units (113418, 117266, 120019, 102883) are assumed Style C by model match. XSS5P33 (127950) is assumed Style C by intuition — not directly confirmed.

EV5L25M / Vektor V1P25M (102978) — SAP lists this as EV5L25M but the physical label reads Lightnin Vektor V1P25M. Possible the unit was replaced and SAP was never updated, or the naming convention differs. This is an open issue that needs investigation. Internally it has a different geometry than the models (slots and a set screw tab), but Travis and Ryan believe it may share the same form factor as Style C. Needs re-inspection with Jake to confirm.

X5P33 BTC mixers (102956, 112142, 122278, 122277, 102943) — attempted inspection on one unit in G152 alone. These use a planetary sun gear reduction and the chuck is not accessible without going deeper into disassembly. Not a one-person job and requires familiarity with gear systems. Needs Jake.

Travis confirmed he was given dimensions by someone else when he built the models and cannot match styles to mixers without physical inspection.

[[People/Jacob Holze\|Jake]] is back Wednesday 2026-04-23. Disassembly of remaining mixers (X5P33 and EV5L25M re-inspection) to be scheduled with Jake, possibly with [[People/Alex Rabbach\|Alex]] as well. No confirmed date yet.

Background on how this session happened: Jake had a car accident on Friday 2026-04-18 and was out Monday/Tuesday. He recommended reaching out to [[People/Nikki Masterson\|Nikki]] and [[People/Alex Rabbach\|Alex]]. Alex helped with the IVD session; Sean Doering directed access to the BTC units (split across G153, G152, G151B — all available, height not set to anything specific).

## 📝 Updates (2026-04-16)

CCs are confirmed as required for the IVD mixers. [[People/Garrett Tschanz\|Garrett]] and [[People/Ted Lenoch\|Ted]] are the main contacts when CCs are initiated — reach out to them early to get ahead of that process.

For the chuck style to mixer model mapping, only 2 mixers need to be disassembled and visually inspected (one each of two different models). The third model is covered by process of elimination.

Pending items discussed:
- Get ahead on SOPs for chuck installation and use — these need to exist before parts arrive and installation begins
- Reach out to [[People/Garrett Tschanz\|Garrett]] and [[People/Ted Lenoch\|Ted]] (CC on IVD mixers) to initiate CC process
- Talk to [[People/Travis Beyer\|Travis]] in person — he is bad at responding digitally; need to ask how he built the SolidWorks models for the chucks
- Discuss two-mixer idea with [[People/Jacob Holze\|Jake]] — disassemble one each of two models, use process of elimination to confirm the third

