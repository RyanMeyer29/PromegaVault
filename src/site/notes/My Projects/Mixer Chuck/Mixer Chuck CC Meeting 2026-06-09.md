---
{"dg-publish":true,"permalink":"/my-projects/mixer-chuck/mixer-chuck-cc-meeting-2026-06-09/","tags":["My-Projects"],"dg-note-properties":{"tags":["My-Projects"],"source":"personal_notes","last_updated":"2026-06-25"}}
---


#My-Projects

<mark class="hltr-orange">Highlighting format example</mark>

Meeting prep and live capture note for the IVD CC kickoff meeting on 2026-06-09. Contacts: [[People/Ted Lenoch\|Ted Lenoch]] and [[People/Garrett Tschanz\|Garrett Tschanz]]. Also attended by [[People/Mark Koeff\|Mark Koeff]] (IVD Bulk Production). This CC covers the mixer chuck hardware modification on 5 IVD units. Ryan is the Change Champion.

---

## Questions to Ask

### Scope & Structure

- [ ] Can all 5 IVD units go on one CC, or does each SAP equipment number need its own separate CC?

> Answer:  One CC for all 5, just separate details

- [ ] Is the equipment currently qualified? (Affects what testing and validation work is required)

> Answer:   Kim doesnt need to be doing anything as long as we dont touch the calibration sensors - CONFIMR With METROLOGY

---

### Validation & Testing

- [ ] Who is the validation person to loop in on this CC?

> Answer: Claire can help for evaluators and approvers

- [ ] What testing actions are expected or required for a hardware modification like this? Is a full validation study needed or is an engineering study sufficient?

> Answer: Basic testing - Check if it is slipping or if it is securely holding the chuck
> 	Test out tools
> 	Test that the chuck is properly guarded - could be EHS
> 	I can o initial testing, have scientist help out to do more official testing

SWAP ONE AT A TIME (for now, could change)

---

### SOPs & Documents

- [ ] Are there any existing SOPs that govern the mixer chuck specifically? (These would need to go in [[Definitions/Quality/CC Sections/Impacted Documentation\|Impacted Documentation]])

> Answer:  Might be worth while to add instructions. SOP21008 Update section 2 to reflect new chucks

- [ ] Are there any other documents — P&IDs, maintenance procedures, training records — that would be impacted and need to be listed?

> Answer: MP reference the SOP, possibly not but posibly  TRN0324 for training

---

### Timeline & Downtime

- [ ] Are there any production schedule constraints or maintenance windows that should inform the CC due date? (Shop request #1903 target completion is 07/29/26 — parts won't exist until then)

> Answer: I can schedule as needed, we do one at a time. Decide how much time I need

- [ ] What is a realistic due date from their end?

> Answer:

---

### ETQ Setup

- [ ] What change type should be selected? (Ali indicated hardware modification — confirm this is correct)

> Answer: Hardware Modification (confirmed 2026-06-17)

- [ ] Which building/location should be listed? (Likely Feynman — confirm)

> Answer: Feynman Center (confirmed 2026-06-17)

- [ ] Who should be assigned as evaluators?

> Answer: TBD — Claire will help identify

---

## Context for Reference

**Units in scope:**

| Equipment # | Description | Location | Chuck Style |
| --- | --- | --- | --- |
| 113417 | GMP Resin Mixer, Lightnin XSS1P33 | MAD-GMP-2210 Small Compounding #1 | Style C |
| 113418 | GMP Resin Mixer, Lightnin XSS1P33 | MAD-GMP-2215 Small Compounding #2 | Style C |
| 117266 | GMP Resin Mixer, Lightnin XSS1P33 | MAD-GMP-2232 Compound Resin RM #3 | Style C |
| 120019 | GMP Resin Mixer, Lightnin XSS1P33 | MAD-GMP-2215 Small Compounding #2 | Style C |
| 127950 | GMP Resin Mixer, Lightnin XSS5P33 | MAD-GMP-2224 Large Compounding #1 | Style C (assumed) |

NEXT STEPS:
~~Initialize etq CC~~ — CC11570 initialized 2026-06-17. ~~Draft attachments~~ — Implementation Actions and Testing Actions complete. Meeting with Claire and Ali: 2026-06-25 2:00 PM Feynman-2450.

---

## CC Document Review Meeting 2026-06-25

Attendees: Ryan, [[People/Claire Moll\|Claire]], [[People/Ali Heinemann\|Ali]]
Location: Feynman-2450 (Teams link available)
Time: 2:00–2:30 PM

### Agenda
- Review Implementation Actions and Testing Actions drafts
- Identify evaluators and approvers for CC11570
- Decide evaluations to check in ETQ
- Set CC due date

### Open Questions to Resolve

- [ ] Which evaluations to check: Training, Documents/Records, Material Inventory, Equipment, Implementation and Testing Action, PSM and EHS already likely. Confirm: Contamination Controls, Material/Equipment Safety, Validation, Design Records, Purchasing
- [ ] Evaluator and approver names
- [ ] CC due date (parts not available until 07/29/26; Ali guidance: set later than internal target)
- [ ] Whether any maintenance procedures referencing SOP21008 need to be listed in Implementation Actions
- [ ] LOTO: confirm whether required during installation
- [ ] "Return unit to service" placement: should testing be explicitly gated before return to service
- [ ] "Complete Testing Actions" wording: units done one at a time, needs to reflect sequencing

### Notes

> [capture meeting notes here]

Plan for high torque to take a little longer out of service



**Key SAP part numbers:**
- Chuck, Mixer, Style C — SAP 1016439
- Stop, Mixer Chuck — SAP 1016455
- Collet, Mixer Chuck — SAP 1016456
- Collet Cap, Mixer Chuck — SAP 1016457
- Tool, Spanner, Mixer Chuck — SAP 1016458
- Chuck Tool, Mixer — SAP 1016459

**Shop timeline:** Request #1903 scheduled 2026-05-28, target completion 07/29/26.

**Ali's guidance from 5/27 1:1:**
- Engineering study language is mainly for reverting to old designs — likely not applicable here, but confirm
- SOPs that need updating go in Documents and Records
- No need to touch evaluations per Ali
- Set due date later than actual internal target to avoid escalation emails
- Include as many related documents as possible

> [!info]- Details & Notes
>
> **Encountered in:** [[My Projects/Mixer Chuck/Mixer Chuck\|Mixer Chuck]]
>
> **See also:** [[Definitions/Quality/Change Control\|Change Control]], [[Definitions/Quality/CC Sections/Brief Description\|Brief Description]], [[Definitions/Quality/CC Sections/Reason for Change\|Reason for Change]], [[Definitions/Quality/CC Sections/Justification for Change\|Justification for Change]], [[Definitions/Quality/CC Sections/Implementation Actions\|Implementation Actions]], [[Definitions/Quality/CC Sections/Testing Actions\|Testing Actions]], [[Definitions/Quality/CC Sections/Impacted Documentation\|Impacted Documentation]], [[People/Ted Lenoch\|Ted Lenoch]], [[People/Garrett Tschanz\|Garrett Tschanz]]
