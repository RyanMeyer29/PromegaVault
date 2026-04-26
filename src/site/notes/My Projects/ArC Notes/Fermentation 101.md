---
{"dg-publish":true,"permalink":"/my-projects/ar-c-notes/fermentation-101/","tags":["My-Projects"],"dg-note-properties":{"tags":["My-Projects"],"source":"personal_notes","last_updated":"2025-01-01"}}
---


#My-Projects

Fermentation 101 was an introductory walkthrough of the [[My Projects/ArC Notes/Fermentation\|Fermentation]] process at Promega, given to me by [[People/Misha Dyskin\|Misha]] in the [[Buildings/Arnold\|Arnold Center]]. It covered the full order of operations from [[My Projects/ArC Notes/Fermentation Media\|media]] prep and sterilization through [[My Projects/ArC Notes/Biomass\|biomass]] growth, [[My Projects/ArC Notes/Induction\|induction]], and harvest — as well as the control systems ([[Software/Batch\|Batch]], operating procedures, unit procedures) used to run and sequence fermentation recipes. This note is a high-level summary; more detailed nodes branch off for individual concepts.

## The Purpose of Fermentation

The goal of [[My Projects/ArC Notes/Fermentation\|Fermentation]] is to grow one specific organism under controlled conditions. You need to monitor and tune several variables: [[My Projects/ArC Notes/pH\|pH]] (set to the organism's optimal range), [[My Projects/ArC Notes/Dissolved Oxygen\|dissolved oxygen]], [[My Projects/ArC Notes/Agitator\|agitation]] (to distribute oxygen evenly), and various [[My Projects/ArC Notes/Fermentation Media\|media]] and feed components. Once the organism has grown to the target amount, the product is harvested.

Products can be expressed either inside the cell or outside the cell. Most of Promega's products are expressed inside the cells, but some are expressed externally. After harvest, [[My Projects/ArC Notes/Cell Paste\|cell paste]] or [[My Projects/ArC Notes/Supernatant\|supernatant]] is either frozen on-site (sometimes for up to a year) or shipped to downstream facilities. One downstream facility is [[Buildings/RFC\|RFC]], located out east off the Beltline — I likely won't go there. Another is an internal "supernatural batch" building. Roughly 3–4 batches produced here feed into 1 batch at [[Buildings/RFC\|RFC]].

One major product example: F884 (produced here) becomes E140 after protein purification — this is [[My Projects/ArC Notes/Luciferase\|Luciferase]], which feeds into a large number of Promega products.

## General Order of Operations

1. Prepare [[My Projects/ArC Notes/Fermentation Media\|media]] and load into the tank
2. Sterilize — [[My Projects/ArC Notes/Agitator\|agitator]] seal, exhaust line, then the full vessel ([[My Projects/ArC Notes/Sterilize in Place\|SIP]] at 121°C for 15–30 min)
3. Cool vessel to growth conditions
4. Adjust [[My Projects/ArC Notes/pH\|pH]], set [[My Projects/ArC Notes/Dissolved Oxygen\|dissolved oxygen]] control strategy
5. [[My Projects/ArC Notes/Inoculation\|Inoculate]] — introduce bacteria into the [[My Projects/ArC Notes/Fermenters\|fermenter]] in a sterile way
6. Monitor and allow [[My Projects/ArC Notes/Biomass\|biomass]] to grow
7. [[My Projects/ArC Notes/Induction\|Induction]] (if required) — change conditions once enough organism is present to trigger protein expression
8. Sterilize harvest lines
9. Transfer out to [[My Projects/ArC Notes/Centrifuge\|centrifuges]] using air pressure; pumps at the centrifuges control flow rate, which determines separation efficiency
10. Freeze or ship the [[My Projects/ArC Notes/Cell Paste\|cell paste]] / [[My Projects/ArC Notes/Supernatant\|supernatant]]

## Sterilization Detail

Sterilization is done in phases, in order:

- Agitator seal [[My Projects/ArC Notes/Sterilize in Place\|SIP]] — the mechanical seal on the [[My Projects/ArC Notes/Agitator\|agitator]] is the most vulnerable sterile boundary and is sterilized first
- Exhaust [[My Projects/ArC Notes/Sterilize in Place\|SIP]] — the exhaust system at Promega connects back to a single shared tank, which creates unique challenges; the line must be sterilized before vessel sterilization
- Vessel [[My Projects/ArC Notes/Sterilize in Place\|SIP]] — every addition line going into the vessel must be sterilized; the entire vessel is brought to 121°C and held for 15–30 minutes, then cooled in a controlled manner. This is complex and involves manual hand valves.

The concept of a "sterile boundary" is important — you're establishing a defined zone that is fully sterile, with every path crossing into that zone also sterilized.

## Multi-Vessel Recipes

Some products require multiple vessels. The example discussed was FAFSAP, which uses P4/P5 (30 L), P1/P2 (300 L), and P3/P6 (3000 L), taking roughly 3 days start to finish. Certain [[My Projects/ArC Notes/Fermentation Media\|media]] components will caramelize if sterilized together, so they're sterilized in separate vessels and then transferred in together. The process involves sterilizing each vessel, growing [[My Projects/ArC Notes/Biomass\|biomass]] in the smaller ones, sterilizing the transfer lines between them, and then transferring everything into the large harvest vessel before transferring out to the [[My Projects/ArC Notes/Centrifuge\|centrifuges]].

## Control System Overview

[[My Projects/ArC Notes/Fermentation\|Fermentation]] is controlled and sequenced through a layered system in [[Software/Batch\|Batch]]:

- Phases — the atomic building blocks (e.g. seal [[My Projects/ArC Notes/Sterilize in Place\|SIP]], exhaust SIP, vessel SIP, [[My Projects/ArC Notes/Biomass\|biomass]], [[My Projects/ArC Notes/Induction\|induction]], transfer out). Each phase has parameters (temperature, [[My Projects/ArC Notes/Agitator\|agitation]] speed, pressure, etc.).
- Operating Procedures (OPs) — control and sequence phases directly; this is the link between the process control system and [[Software/Batch\|Batch]]
- Transitions (TS) — operator prompts between steps; you must confirm each transition to advance
- Unit Procedures — what recipes are actually built from; they sequence operating procedures together
- [[Software/Batch\|Batch]] — the top-level recipe system; captures parameter standards so products running repeatedly don't need to be reconfigured each run. Recipes can include parallel branches (e.g. simultaneously growing [[My Projects/ArC Notes/Biomass\|biomass]] while sterilizing addition lines from other vessels).

The [[Definitions/HMI\|HMI]] is what operators use to interact with the system. [[EWS\|EWS]] (Engineering Workstations) are the remote desktop servers used for engineering access.

## Phases List (in typical order)

- Media In
- Seal [[My Projects/ArC Notes/Sterilize in Place\|SIP]]
- Exhaust [[My Projects/ArC Notes/Sterilize in Place\|SIP]]
- Vessel [[My Projects/ArC Notes/Sterilize in Place\|SIP]]
- [[My Projects/ArC Notes/Biomass\|Biomass]]
- [[My Projects/ArC Notes/Induction\|Induction]]
- Transfer In (from another vessel)
- Transfer Out [[My Projects/ArC Notes/Sterilize in Place\|SIP]]
- Transfer Out

> [!info]- Details & Notes
>
> **Encountered in:** This note is itself a project/learning note — the session with [[People/Misha Dyskin\|Misha]] on fermentation basics, held in the [[Buildings/Arnold\|Arnold Center]].
>
> **See also:** [[My Projects/ArC Notes/Fermentation\|Fermentation]], [[Buildings/Arnold\|Arnold]], [[My Projects/ArC Notes/Fermenters\|Fermenters]], [[My Projects/ArC Notes/Sterilize in Place\|Sterilize in Place]], [[My Projects/ArC Notes/Centrifuge\|Centrifuge]], [[My Projects/ArC Notes/Luciferase\|Luciferase]], [[Software/Batch\|Batch]], [[EWS\|EWS]], [[Definitions/HMI\|HMI]], [[Buildings/RFC\|RFC]], [[My Projects/ArC Notes/Inoculation\|Inoculation]], [[My Projects/ArC Notes/Biomass\|Biomass]], [[My Projects/ArC Notes/Induction\|Induction]], [[My Projects/ArC Notes/Cell Paste\|Cell Paste]], [[My Projects/ArC Notes/Supernatant\|Supernatant]], [[My Projects/ArC Notes/Dissolved Oxygen\|Dissolved Oxygen]], [[My Projects/ArC Notes/pH\|pH]], [[My Projects/ArC Notes/Agitator\|Agitator]], [[My Projects/ArC Notes/Fermentation Media\|Fermentation Media]]
