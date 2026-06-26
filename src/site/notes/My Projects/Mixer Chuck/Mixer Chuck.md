---
{"dg-publish":true,"permalink":"/my-projects/mixer-chuck/mixer-chuck/","tags":["My-Projects","active"],"dg-note-properties":{"aliases":["Mixer Chuck","Mixer Chukc"],"tags":["My-Projects","active"],"source":"personal_notes","last_updated":"2026-06-25"}}
---

#My-Projects

**Related Areas:** [[Lines/MA2\|MA2]], [[Buildings/Lamarr\|Lamarr]], [[Definitions/Equipment/Lightnin Mixer\|Lightnin Mixer]]
**Drawing review notes:** [[My Projects/Mixer Chuck/Mixer Chuck Drawing Review 1\|Mixer Chuck Drawing Review 1]]
**Historical notes:** [[My Projects/Mixer Chuck/Mixer Chuck Notes Archive\|Mixer Chuck Notes Archive]]
**CC notes:** [[My Projects/Mixer Chuck/Mixer Chuck CC Meeting 2026-06-09\|Mixer Chuck CC Meeting 2026-06-09]]
**Part notes:** [[My Projects/Mixer Chuck/Mixer Chuck Parts/Chuck, Mixer, Style A\|Chuck, Mixer, Style A]] — [[My Projects/Mixer Chuck/Mixer Chuck Parts/Chuck, Mixer, Style B\|Chuck, Mixer, Style B]] — [[My Projects/Mixer Chuck/Mixer Chuck Parts/Chuck, Mixer, Style C\|Chuck, Mixer, Style C]] — [[My Projects/Mixer Chuck/Mixer Chuck Parts/Stop, Mixer Chuck\|Stop, Mixer Chuck]] — [[My Projects/Mixer Chuck/Mixer Chuck Parts/Collet Cap, Mixer Chuck\|Collet Cap, Mixer Chuck]] — [[My Projects/Mixer Chuck/Mixer Chuck Parts/Tool, Spanner, Mixer Chuck\|Tool, Spanner, Mixer Chuck]] — [[My Projects/Mixer Chuck/Mixer Chuck Parts/Chuck Tool, Mixer\|Chuck Tool, Mixer]]

---

## 📋 Project Overview

There are 11 total mixers in scope across BTC (5x X5P33), RDC (1x XSS1P33), and IVD (4x XSS1P33, 1x XSS5P33). The EV5L25M (102978, BTC) was removed from scope on 2026-04-29 after it was confirmed to have been added based on misinformation. 

The goal is to redesign the mixer chuck system. [[People/Travis Beyer\|Travis Beyer]]'s collet-style redesign uses the same approach CNC machines use to hold tooling. It can hold multiple shaft sizes, uses parts sourced from [[Fabrication/McMaster-Carr\|McMaster-Carr]], and has no internal water exposure.

Chuck styles are now confirmed for all in-scope models. X5P33 (all BTC units) = Style B, confirmed by [[People/Jacob Holze\|Jake]] via disassembly of 102943. XSS1P33 (all IVD and RDC units) = Style C, confirmed by disassembly of 113417 with [[People/Alex Rabbach\|Alex]] on 2026-04-20. XSS5P33 (127950, IVD) = Style C assumed — same motor and drive mount as XSS1P33, gear reduction prevented full inspection. Treating as Style C going forward; if wrong, will address when it comes up.

There are no in-service mixers using Style A. [[People/Jacob Holze\|Jake]] has requested one Style A chuck be ordered anyway as a standby, in case units in storage require it.

[[Definitions/Quality/Change Control\|CCs]] are confirmed as required for the IVD mixers. [[People/Ted Lenoch\|Ted Lenoch]] and [[People/Garrett Tschanz\|Garrett]] are the main contacts for organizing CCs and associated downtime. Reach out to them early before installation begins. BTC mixers do not require a CC — confirmed by [[People/Diego Lamela\|Diego]] on 2026-05-28, as they are not part of a GMP-regulated process.

**Timeline:** All drawings are approved by [[People/Brian Osterbrink\|Brian]]. Shop request was submitted 2026-05-11 and was clarified with [[People/Kent Toepfer\|Kent]], [[People/Travis Beyer\|Travis]], and [[People/Amanda Maly\|Amanda]] at the 2026-05-18 office hours meeting (see [[My Projects/Mixer Chuck/Mixer Chuck Notes Archive\|Mixer Chuck Notes Archive]]). Spares quantity confirmed (1 per style, 3 extra assemblies total, confirmed 2026-05-05). Machine shop request #1903 was scheduled 2026-05-28 with target completion 07/29/26.

---

## ✅ My Action Items (Ryan)

### Phase 1 — Drawings (in progress)

- [x] Fix all drawing files to move equipment numbers into the Notes section of the title block
- [x] Get drawings approved by [[People/Brian Osterbrink\|Brian]]
- [ ] Add inspection dimensions (circle/oval markers) to all critical dimensions across all 8 drawings — bearing surfaces, lengths, depths of different diameters, and groove dimensions
- [x] Change chuck tool handle diameter from 1.5" to 1.0" on SAP 1016459 per [[People/Ted Lenoch\|Ted]] / IVD feedback
- [ ] Once approved, submit for [[Software/EPDM\|ePDM]] rename/move (Phase 2)

#### Drawing Notes Section Checklist

- [x] Chuck, Mixer, Style A (SAP 1016437)
- [x] Chuck, Mixer, Style B (SAP 1016438)
- [x] Chuck, Mixer, Style C (SAP 1016439)
- [x] Stop, Mixer Chuck, Stainless Steel (SAP 1016455)
- [x] Collet, Mixer Chuck, Stainless Steel (SAP 1016456)
- [x] Collet Cap, Mixer Chuck, Stainless Steel (SAP 1016457)
- [x] Tool, Spanner, Mixer Chuck, Stainless Steel (SAP 1016458)
- [x] Chuck Tool, Mixer, Stainless/Delrin (SAP 1016459)

### Phase 2 — ePDM (after approval)

- [x] Rename each file to its SAP part number
- [x] Move each file to the correct [[Software/EPDM\|ePDM]] folder (keep [[Software/SolidWorks/Solidworks\|Solidworks]] references intact)

#### ePDM Rename and Move Process

Do everything through [[Software/EPDM\|ePDM]], not Windows Explorer. Renaming or moving through Explorer breaks [[Software/SolidWorks/Solidworks\|Solidworks]] references.

1. Check out all affected files in [[Software/EPDM\|ePDM]] first — parts, assemblies, and drawings together in one batch. Files must be checked out before they can be renamed or moved.
2. Right-click the file in [[Software/EPDM\|ePDM]] and use Rename to change the filename to the SAP part number.
3. After renaming, right-click and use Move to put it in the correct folder.
4. [[Software/EPDM\|ePDM]] will prompt to update references — confirm yes on all of them.
5. Check everything back in once all renames and moves are complete.

Process files in this order: parts first, then assemblies, then drawings. This follows the reference chain so each update propagates correctly before the next file type looks for it.

### Phase 3 — Shop Request

- [x] Confirm spares quantity — 1 spare per style, 3 extra assemblies total (confirmed 2026-05-05)
- [x] Submit shop request to [[People/Travis Beyer\|Travis]] (submitted 2026-05-11)
- [x] Send [[People/Amanda Maly\|Amanda]] the vendor links for the [[Maxx Tooling Collet Cap\|Maxx Tooling Collet Cap]] and [[My Projects/Mixer Chuck/Mixer Chuck Parts/Parlec ER32 Collet\|Parlec ER32 Collet]] (18 of each)
- [x] Update [[People/Diego Lamela\|Diego]] when [[People/Travis Beyer\|Travis]] enters the timeline — shop scheduled 2026-05-28, Diego notified

Style A: order at least 1 as standby per [[People/Jacob Holze\|Jake]] — no in-service units currently use it but there may be units in storage.
Style B: all 5 BTC X5P33 units.
Style C: all 5 IVD XSS1P33 units + 1 IVD XSS5P33 (assumed) + 1 RDC XSS1P33.

### Phase 4 — Parts Process (after parts arrive)

- [ ] Complete [[Definitions/Quality/CoC\|CoCs]] for all parts
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
- [x] Get SAP numbers for each mixer (IVD: [[People/Garrett Tschanz\|Garrett]]; BTC: [[People/Sean Doering\|Sean]])
- [x] Talk to [[People/Nikki Masterson\|Nikki]] — parts process Excel file obtained
- [x] Confirm chuck style for X5P33 — Style B (confirmed by Jake via disassembly of 102943)
- [x] Confirm chuck style for XSS1P33 — Style C (confirmed by disassembly of 113417 with Alex, 2026-04-20)
- [x] Remove EV5L25M (102978) from scope — confirmed misinformation, removed 2026-04-29

---

## 🔧 Background & Design Context

### Problem with Old Design

The original chuck allowed impellers to fall out during mixing. A key system redesign between the impeller and chuck was attempted, but caused metal shavings and round-out issues over time.

### Current Design (Travis's Collet-Style)

[[People/Travis Beyer\|Travis Beyer]] redesigned the chuck to match the collet style used by CNC machines for holding tooling. Travis has 3 different options modeled — Style A, B, and C — corresponding to the 3 different motor mount configurations the manufacturer uses.

Advantages: holds multiple shaft sizes, easy to source replacement parts from [[Fabrication/McMaster-Carr\|McMaster-Carr]], sealed with no water internally.

### SAP & Drawings

[[People/Aaron Vergiels\|Aaron Vergiels]] originally obtained the list of mixer equipment. [[People/Travis Beyer\|Travis Beyer]] designed the 3 chuck styles and built the SolidWorks models. SAP part numbers 1016437–1016439 and 1016455–1016459 are assigned. See drawing review note for correction checklist: [[My Projects/Mixer Chuck/Mixer Chuck Drawing Review 1\|Mixer Chuck Drawing Review 1]].

The collet (SAP 1016456) is an unmodified stock part — no drawing is required. See [[My Projects/Mixer Chuck/Mixer Chuck Parts/Parlec ER32 Collet\|Parlec ER32 Collet]] for part info and sourcing.

---

## 🔩 Parts & SAP Numbers by Equipment

> Drawing # = SAP Material # (per title block convention).
> Order quantities TBD pending spares confirmation with Claire.
> Stop qty is doubled since there are 2 per assembly. Spanner Tool qty confirmed to match Chuck Tool.

### Mixers in Scope

#### BTC

| Equipment # | Equipment - Desc. | Functional Loc. | Func. Loc. - Desc.  | Chuck Style |
| ----------- | ----------------- | --------------- | ------------------- | ----------- |
| 102956      | Mixer, X5P33      | MAD-BTC-G153    | MagaZorb Production | Style B     |
| 112142      | Mixer, X5P33      | MAD-BTC-G151C   | Bay 3               | Style B     |
| 122278      | Mixer, X5P33      | MAD-BTC-G130    | Hallway             | Style B     |
| 122277      | Mixer, X5P33      | MAD-BTC-G130    | Hallway             | Style B     |
| 102943      | Mixer, X5P33      | MAD-BTC-G152    | Tank Cleaning       | Style B (confirmed — disassembled with Jake) |

#### RDC

| Equipment # | Equipment - Desc. | Functional Loc. | Func. Loc. - Desc.      | Chuck Style |
| ----------- | ----------------- | --------------- | ----------------------- | ----------- |
| 102883      | Mixer, XSS1P33    | MAD-RDC-204     | Large Scale Formulation | Style C (assumed — same model as XSS1P33 IVD units) |

#### IVD

| Equipment # | Equipment - Desc.                 | Functional Loc. | Func. Loc. - Desc.   | Chuck Style |
| ----------- | --------------------------------- | --------------- | -------------------- | ----------- |
| 113417      | GMP Resin Mixer, Lightnin XSS1P33 | MAD-GMP-2210    | Small Compounding #1 | Style C (confirmed — inspected 2026-04-20) |
| 113418      | GMP Resin Mixer, Lightnin XSS1P33 | MAD-GMP-2215    | Small Compounding #2 | Style C (confirmed by model match) |
| 117266      | GMP Resin Mixer, Lightnin XSS1P33 | MAD-GMP-2232    | Compound Resin RM #3 | Style C (confirmed by model match) |
| 127950      | GMP Resin Mixer, Lightnin XSS5P33 | MAD-GMP-2224    | Large Compounding #1 | Style C (assumed — same motor/drive mount as XSS1P33) |
| 120019      | GMP Resin Mixer, Lightnin XSS1P33 | MAD-GMP-2215    | Small Compounding #2 | Style C (confirmed by model match) |

### Chuck Bodies by Equipment

| Equipment # | Area | Chuck Style                        | SAP Material # |
| :---------- | :--- | :--------------------------------- | :------------- |
| 102956      | BTC  | Style B                            | 1016438        |
| 112142      | BTC  | Style B                            | 1016438        |
| 122278      | BTC  | Style B                            | 1016438        |
| 122277      | BTC  | Style B                            | 1016438        |
| 102943      | BTC  | Style B (confirmed)                | 1016438        |
| 102883      | RDC  | Style C (assumed)                  | 1016439        |
| 113417      | IVD  | Style C (confirmed)                | 1016439        |
| 113418      | IVD  | Style C (confirmed by model match) | 1016439        |
| 117266      | IVD  | Style C (confirmed by model match) | 1016439        |
| 127950      | IVD  | Style C (assumed)                  | 1016439        |
| 120019      | IVD  | Style C (confirmed by model match) | 1016439        |

### All Parts — SAP Reference

| SAP Material # | Description                                 | Order Qty                         | Notes                                                                                                                      |
| :------------- | :------------------------------------------ | :-------------------------------- | :------------------------------------------------------------------------------------------------------------------------- |
| 1016437        | Chuck, Mixer, Style A                       | TBD (at least 1 standby per Jake) | No in-service units; standby stock only                                                                                    |
| 1016438        | Chuck, Mixer, Style B                       | TBD                               | 5x BTC X5P33 units                                                                                                         |
| 1016439        | Chuck, Mixer, Style C                       | TBD                               | 6x IVD + 1x RDC; XSS5P33 assumed                                                                                           |
| 1016455        | Stop, Mixer Chuck, Stainless Steel          | TBD                               | 2 per chuck ordered (across all styles)                                                                                    |
| 1016456        | Collet, Mixer Chuck, Stainless Steel        | 18                                | Ordered by [[People/Amanda Maly\|Amanda]] directly from vendor                                                                     |
| 1016457        | Collet Cap, Mixer Chuck, Stainless Steel    | 18                                | Ordered by [[People/Amanda Maly\|Amanda]] directly from vendor                                                                     |
| 1016458        | Tool, Spanner, Mixer Chuck, Stainless Steel | TBD                               | 1 per chuck ordered (across all styles); plus TBD extras for Jake's partial assemblies                                     |
| 1016459        | Chuck Tool, Mixer, Stainless/Delrin         | TBD                               | 1 per chuck ordered (across all styles); plus TBD extras for Jake's partial assemblies                                     |

---

## 📝 Updates (2026-04-29)

Chuck style mapping fully confirmed for all in-scope models. [[People/Jacob Holze\|Jake]] confirmed via message that equipment 102943 is an X5P33 and is Style B. This means all 5 BTC X5P33 units are Style B. [[People/Alex Rabbach\|Alex]] and Ryan took apart a Feynman IVD mixer and found it to be Style C. The XSS5P33 (127950) is assumed Style C — same motor and drive mount as the XSS1P33, but a gear reduction prevented full inspection without additional work (cleaning and re-greasing). Treating as Style C going forward.

The EV5L25M (102978) has been removed from scope. It was on the list due to misinformation and does not belong. Historical notes including the EV5L25M are preserved in [[My Projects/Mixer Chuck/Mixer Chuck Notes Archive\|Mixer Chuck Notes Archive]].

No in-service mixers use Style A. Jake wants one ordered as a standby in case units in storage require it.

Drawings are currently being edited per Brian's review notes. Once Brian approves, the shop request will be submitted. Spares quantity has not been confirmed with [[People/Claire Moll\|Claire]] — needs follow-up.

## 📝 Updates (2026-06-25)

CC document review meeting scheduled today with [[People/Claire Moll\|Claire]] and [[People/Ali Heinemann\|Ali]] (Feynman-2450, 2:00–2:30 PM). Implementation Actions and Testing Actions drafts are prepared and ready to review. Evaluations section in ETQ still to be decided — bringing the following open questions into the meeting:

- Which evaluations to check: Contamination Controls and Material/Equipment Safety are likely yes; Validation, Design Records, and Purchasing need Claire's input
- Evaluator and approver names (Claire is helping identify)
- CC due date (parts not available until 07/29/26; target something in September/October per Ali's guidance)

## 📝 Updates (2026-06-17)

CC11570 initialized in ETQ on 2026-06-17. Claire asked via Teams to have the three draft attachments ready before a meeting end of next week. Metrology confirmed no action needed (calibration sensors will not be disturbed during installation). ETQ initialization fields used:

Brief Description: Replace mixer chuck assemblies on 5 IVD Lightnin mixers in Feynman with collet-style chuck system.

Reason for Change: This change is necessary because the existing mixer chuck design uses a set screw that has loosened during mixing operations, introducing metal shavings into the product and creating a safety hazard as impellers can drop out of the mixer while spinning.

Additional Description filed in ETQ covering all 5 unit equipment numbers, functional locations, and new part SAP numbers (1016439, 1016455–1016459). Change type: Hardware Modification. Building: Feynman Center.

## 📝 Updates (2026-06-15)

IVD CC kickoff meeting sent 2026-06-04 to [[People/Claire Moll\|Claire Moll]], [[People/Ted Lenoch\|Ted Lenoch]], and [[People/Jacob Holze\|Jake]] (cc: [[People/Ali Heinemann\|Ali Heinemann]], [[People/Garrett Tschanz\|Garrett]]; bcc: Feynman-2450). Scope: 5 IVD mixers. Topics: number of CCs required, mixer downtime coordination, SOP updates, and new training.

CC kickoff meeting held 2026-06-09 with [[People/Ted Lenoch\|Ted Lenoch]] and [[People/Garrett Tschanz\|Garrett]]. Key decisions and answers from that meeting (full notes: [[My Projects/Mixer Chuck/Mixer Chuck CC Meeting 2026-06-09\|Mixer Chuck CC Meeting 2026-06-09]]):

All 5 IVD units can go on one CC with separate details per unit. No Metrology action is needed as long as the calibration sensors are not disturbed — confirm with Metrology before installation. [[People/Claire Moll\|Claire]] will help with evaluators and approvers. Plan is to swap one unit at a time (may change). Testing approach: confirm the chuck is not slipping, test the tools, check that the chuck is properly guarded (may loop in [[Definitions/EHS\|EHS]]); Ryan does the initial testing, then a scientist assists for the more official testing pass. SOP21008 section 2 needs to be updated to reflect the new chucks; TRN0324 may need a training update. Next step: initialize the ETQ CC.

### Phase 5 — IVD Change Control

- [x] Prepare draft attachments for Claire meeting: Implementation Actions and Testing Actions drafted and ready to review (Impacted Documentation removed per Ali — SOP/TRN update steps moved into Implementation Actions Post Change). Meeting: 2026-06-25 Feynman-2450 2:00 PM with Claire and Ali
- [x] Initialize ETQ CC for IVD mixer chuck installation (all 5 units on one CC, separate details) — CC11570 initialized 2026-06-17
- [x] Confirm with Metrology: calibration sensors not disturbed during installation — confirmed, no Metrology action needed
- [ ] Work with [[People/Claire Moll\|Claire]] to identify evaluators and approvers
- [ ] Identify and list all impacted documentation: SOP21008 (section 2 update confirmed), TRN0324 (training, likely impacted)
- [ ] Determine testing actions: chuck grip/slip test, tool function test, guarding check (possible [[Definitions/EHS\|EHS]] involvement)
- [ ] Coordinate scientist for official testing pass
- [ ] Set CC due date — allow buffer beyond internal target to avoid escalation emails
- [ ] Coordinate installation downtime with [[People/Ted Lenoch\|Ted Lenoch]] and [[People/Garrett Tschanz\|Garrett]] — one unit at a time, schedule as needed
