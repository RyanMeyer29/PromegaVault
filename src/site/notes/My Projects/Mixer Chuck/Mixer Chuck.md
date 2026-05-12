---
{"dg-publish":true,"permalink":"/my-projects/mixer-chuck/mixer-chuck/","tags":["My-Projects","active"],"dg-note-properties":{"aliases":["Mixer Chuck","Mixer Chukc"],"tags":["My-Projects","active"],"source":"personal_notes","last_updated":"2026-05-06"}}
---

#My-Projects

**Related Areas:** [[Lines/MA2\|MA2]], [[Buildings/Lamarr\|Lamarr]]
**Drawing review notes:** [[My Projects/Mixer Chuck/Mixer Chuck Drawing Review 1\|Mixer Chuck Drawing Review 1]]
**Historical notes:** [[My Projects/Mixer Chuck/Mixer Chuck Notes Archive\|Mixer Chuck Notes Archive]]
**Part notes:** [[My Projects/Mixer Chuck/Mixer Chuck Parts/Chuck, Mixer, Style A\|Chuck, Mixer, Style A]] — [[My Projects/Mixer Chuck/Mixer Chuck Parts/Chuck, Mixer, Style B\|Chuck, Mixer, Style B]] — [[My Projects/Mixer Chuck/Mixer Chuck Parts/Chuck, Mixer, Style C\|Chuck, Mixer, Style C]] — [[My Projects/Mixer Chuck/Mixer Chuck Parts/Stop, Mixer Chuck\|Stop, Mixer Chuck]] — [[My Projects/Mixer Chuck/Mixer Chuck Parts/Collet Cap, Mixer Chuck\|Collet Cap, Mixer Chuck]] — [[My Projects/Mixer Chuck/Mixer Chuck Parts/Tool, Spanner, Mixer Chuck\|Tool, Spanner, Mixer Chuck]] — [[My Projects/Mixer Chuck/Mixer Chuck Parts/Chuck Tool, Mixer\|Chuck Tool, Mixer]]

---

## 📋 Project Overview

There are 11 total mixers in scope across BTC (5x X5P33), RDC (1x XSS1P33), and IVD (4x XSS1P33, 1x XSS5P33). The EV5L25M (102978, BTC) was removed from scope on 2026-04-29 after it was confirmed to have been added based on misinformation. 

The goal is to redesign the mixer chuck system. [[People/Travis Beyer\|Travis Beyer]]'s collet-style redesign uses the same approach CNC machines use to hold tooling. It can hold multiple shaft sizes, uses parts sourced from [[Fabrication/McMaster-Carr\|McMaster-Carr]], and has no internal water exposure.

Chuck styles are now confirmed for all in-scope models. X5P33 (all BTC units) = Style B, confirmed by [[People/Jacob Holze\|Jake]] via disassembly of 102943. XSS1P33 (all IVD and RDC units) = Style C, confirmed by disassembly of 113417 with [[People/Alex Rabbach\|Alex]] on 2026-04-20. XSS5P33 (127950, IVD) = Style C assumed — same motor and drive mount as XSS1P33, gear reduction prevented full inspection. Treating as Style C going forward; if wrong, will address when it comes up.

There are no in-service mixers using Style A. [[People/Jacob Holze\|Jake]] has requested one Style A chuck be ordered anyway as a standby, in case units in storage require it.

[[Definitions/Quality/Change Control\|CCs]] are confirmed as required for the IVD mixers. [[People/Ted Lenoch\|Ted Lenoch]] and [[People/Garrett Tschanz\|Garrett]] are the main contacts for organizing CCs and associated downtime. Reach out to them early before installation begins.

**Timeline:** Last drawing is being finalized — one part remodeled based on new info from [[People/Travis Beyer\|Travis]] (as of 2026-05-06). [[People/Brian Osterbrink\|Brian]] approval to be requested at morning coffee 2026-05-07. Once approved, submit shop request to [[People/Travis Beyer\|Travis]]. Spares quantity confirmed (1 per style, 3 extra assemblies total, confirmed 2026-05-05).

---

## ✅ My Action Items (Ryan)

### Phase 1 — Drawings (in progress)

- [x] Fix all drawing files to move equipment numbers into the Notes section of the title block
- [ ] Get drawings approved by [[People/Brian Osterbrink\|Brian]] (review done, edits in progress)
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
- [ ] Move each file to the correct [[Software/EPDM\|ePDM]] folder (keep [[Software/SolidWorks/Solidworks\|Solidworks]] references intact)

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
- [ ] Submit shop request to [[People/Travis Beyer\|Travis]] once drawings are approved

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

The collet (SAP 1016456) is an unmodified stock part — no drawing is required. See [[Definitions/Parlec ER32 Collet\|Parlec ER32 Collet]] for part info and sourcing.

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
| 1016456        | Collet, Mixer Chuck, Stainless Steel        | TBD                               | 1 per chuck ordered (across all styles); plus TBD extras for Jake's partial assemblies (chuck bodies only, no accessories) |
| 1016457        | Collet Cap, Mixer Chuck, Stainless Steel    | TBD                               | 1 per chuck ordered (across all styles); plus TBD extras for Jake's partial assemblies                                     |
| 1016458        | Tool, Spanner, Mixer Chuck, Stainless Steel | TBD                               | 1 per chuck ordered (across all styles); plus TBD extras for Jake's partial assemblies                                     |
| 1016459        | Chuck Tool, Mixer, Stainless/Delrin         | TBD                               | 1 per chuck ordered (across all styles); plus TBD extras for Jake's partial assemblies                                     |

---

## 📝 Updates (2026-04-29)

Chuck style mapping fully confirmed for all in-scope models. [[People/Jacob Holze\|Jake]] confirmed via message that equipment 102943 is an X5P33 and is Style B. This means all 5 BTC X5P33 units are Style B. [[People/Alex Rabbach\|Alex]] and Ryan took apart a Feynman IVD mixer and found it to be Style C. The XSS5P33 (127950) is assumed Style C — same motor and drive mount as the XSS1P33, but a gear reduction prevented full inspection without additional work (cleaning and re-greasing). Treating as Style C going forward.

The EV5L25M (102978) has been removed from scope. It was on the list due to misinformation and does not belong. Historical notes including the EV5L25M are preserved in [[My Projects/Mixer Chuck/Mixer Chuck Notes Archive\|Mixer Chuck Notes Archive]].

No in-service mixers use Style A. Jake wants one ordered as a standby in case units in storage require it.

Drawings are currently being edited per Brian's review notes. Once Brian approves, the shop request will be submitted. Spares quantity has not been confirmed with [[People/Claire Moll\|Claire]] — needs follow-up.
