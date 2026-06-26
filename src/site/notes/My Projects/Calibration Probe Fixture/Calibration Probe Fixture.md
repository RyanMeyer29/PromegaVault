---
{"dg-publish":true,"permalink":"/my-projects/calibration-probe-fixture/calibration-probe-fixture/","tags":["My-Projects","active"],"dg-note-properties":{"aliases":["Metrology fixture"],"tags":["My-Projects","active"],"source":"personal_notes","last_updated":"2026-06-15"}}
---


#My-Projects

## Action Items

- [x] Make report on fixture plan for Metrology meeting Wed Apr 22 — solid plan for cold fixtures, ideas for hot fixture (flagged in 1:1, 2026-04-16)
- [x] Reach out to Metrology about a metal lid for the fixture (flagged in 1:1, 2026-04-10)
- [ ] Explore rubber gasket and rubber case options for the sensor (flagged in 1:1, 2026-04-10)
- [x] Research fixture materials compatible with -80°C to 260°C, silicone oil, and ethanol (consider machinability, temp range, chemical resistance)
- [x] Get probe make/model info from Metrology, then look up dimensions online — gospel list is in [[My Projects/Calibration Probe Fixture/Technical Specs/Bath and Probe Spec\|Bath and Probe Spec]]; SAP-to-model mapping captured below
- [x] Measure probe dimensions in person — all 5 measured (5628-12-S measured 2026-05-28, dimensions match datasheet)
- [x] Measure bath lip and opening dimensions in person — 1 bath measured and modeled so far
- [x] Measure temperature at the bath lip / just above fluid surface when 280°C bath is running — superseded; metal confirmed as material direction at 2026-04-22 meeting, lip temp measurement no longer needed to unblock design
- [x] Follow up with [[People/Ali Heinemann\|Ali]] re: metrology lip temp check (flagged in 1:1, 2026-04-03) — resolved; metal direction confirmed
- [ ] Start SolidWorks drawings for fixture
- [ ] Get part numbers (SAP) for fixture parts
- [ ] Move files to ePDM once drawings are underway

**Priority (as of 2026-04-10): #2 of active projects**

---

## Open Questions

- **Two-jig design vs universal fixture.** Original instinct was a two-jig approach (separate hot and cold fixtures); the 2026-04-22 meeting pivoted to one universal metal fixture. Reverting to two jigs is gaining momentum because the 6331 (280°C) bath is different enough from the others that a dedicated hot jig may simplify everything else. The hot jig would be 5622-32-only and could be much simpler (one or two slots, no lower tube carrier needed since the 5606 isn't on this bath). This is a design call I'll make as I model — not a meeting decision.
- **Vent holes are allowed.** [[People/David Velazquez\|David]] confirmed a sealed lid is only useful for getting the bath to temperature faster, not for accuracy or operation. Vent holes are fine on all jigs and especially relevant for the hot jig if vapor handling is a concern. Possible downstream implication: if hot vapor isn't trapped under the lid, PEEK bushings may be more viable at 280°C than the materials research assumed — worth testing/measuring before committing.
- **5622-05 / 5622-10 fixture treatment.** [[My Projects/Calibration Probe Fixture/Technical Specs/Bath and Probe Spec\|Bath and Probe Spec]] groups them as one entry. [[People/David Velazquez\|David]] said designing around the 5622-10 dimensions will accommodate both. Open question whether to use a single 1.0 mm bushing (slop on the 0.5 mm probe), swappable bushings in one slot, or two separate slots.
- **7380 bath scope.** Confirmed out of scope at 2026-06-10 Metrology meeting (see [[Other/Metrology Meeting 2026-06-10\|Metrology Meeting 2026-06-10]]). Design assumption of shared lip profile holds.
- **CMC backup bath scope.** Confirmed out of scope at 2026-06-10 Metrology meeting (see [[Other/Metrology Meeting 2026-06-10\|Metrology Meeting 2026-06-10]]).
- **Site access / delivery timing.** Fume hood in Metrology is being replaced: existing hood removed 2026-07-22, new hood installed 2026-08-10. Factor this into delivery and installation scheduling.
- **Baby baths.** Count, model numbers, and lip dimensions still unconfirmed.

---

## Material Considerations

Decision as of 2026-04-22 meeting: universal metal fixture. This supersedes the earlier all-polymer direction. Frame material confirmed as 316L stainless steel.

### Archived — prior polymer direction (superseded 2026-04-22)

The original direction was all-polymer, with PEEK as the leading candidate. The reasoning was that metal conducts heat from the bath interior to the outside environment via internal convection, which would affect bath stability, and that a low-conductivity polymer solved this inherently. PEEK universal was the leading candidate pending a bath lip temperature measurement at 280°C to confirm it stayed within PEEK's service range (~250°C continuous).

If PEEK had been ruled out at the high-temp bath, the next candidates were Macor (glass-mica ceramic, rated to ~1470°F, available on McMaster, ~$650/sheet, limited stock sizes) and PBI (Celazole).

Materials evaluated and ruled out during polymer phase:
- Delrin/Acetal — max service temp ~90–120°C, cannot handle high-temp baths
- PTFE — creeps and deforms under load, not dimensionally stable enough for controlled insertion depth
- Torlon (PAI) — rated to 500°F (260°C), does not cover the 280°C bath
- Vespel — rated for the full range but not findable through standard suppliers
- PPS/Ryton — max ~220–240°C, does not reach 280°C
- Buna-N aramid gasket material — gasket material, not structural; lower temp limit of -40°F does not cover -80°C bath

---

The Calibration Probe Fixture is a fabrication project to design and build a fixture (or set of fixtures) that holds temperature probes at consistent, controlled depths inside 1.5 ml reaction tubes during calibration in oil baths. The goal is to bring in-house capabilities for temperature standards calibrations that previously required external resources. The project is led by the Metrology department in [[Buildings/Feynman\|Feynman]], with [[People/Kimberly Steinhauer\|Kimberly]] as supervisor and [[People/Matt Wahl\|Matt]] and [[People/David Velazquez\|David]] as the primary contacts. [[People/Ali Heinemann\|Ali]] is also involved.

The baths used for calibration are oil baths covering a temperature range of -80 to 260°C. There are 4 baths total, all located in Feynman Metrology, and all share the same lip profile. A large bath from [[Buildings/Chappelle Manufacturing Center\|CMC]] is also available as a backup. The baths use silicone oil, with isopropyl alcohol used for wiping; one bath uses 90% ethanol and one bath is cold-only (no heating capability). The high-temp portable bath holds approximately 1 gallon; the large baths hold approximately 5 gallons each. A -90°C dry block unit also exists but is out of scope for this project — it does not require a fixture.

There are 5 probe types in scope per the [Bath and Probe Spec]]: 5606 ([[5606_5607_Probe.pdf](/img/user/My%20Projects/Calibration%20Probe%20Fixture/Technical%20Specs/Bath%20and%20Probe%20Spec.md)), 5622-10 (which also covers the 5622-05 functionally; [5622_Probe_Technical_Data.pdf](/img/user/My%20Projects/Calibration%20Probe%20Fixture/Technical%20Specs/5622_Probe_Technical_Data.pdf)), 5622-32 ([5622_Probe_Technical_Data.pdf](/img/user/My%20Projects/Calibration%20Probe%20Fixture/Technical%20Specs/5622_Probe_Technical_Data.pdf)), 5628-12-S ([5626_5628_Probe.pdf](/img/user/My%20Projects/Calibration%20Probe%20Fixture/Technical%20Specs/5626_5628_Probe.pdf)), and 5623B ([5623B_Probe.pdf](/img/user/My%20Projects/Calibration%20Probe%20Fixture/Technical%20Specs/5623B_Probe.pdf)). See [[My Projects/Calibration Probe Fixture/Probe Summary\|Probe Summary]] for the consolidated table with SAP numbers and dimensions. All probes go into 1.5 ml reaction tubes.

The 5606 is the probe that dangles, per [[People/David Velazquez\|David]] (Teams, 2026-04-02). The fixture's lower tube carrier exists primarily to solve the 5606 dangling problem. Only the 5622-32 goes to 280°C, per [[People/David Velazquez\|David]] (Teams, 2026-04-01); the other probes do not need to survive the high-temp bath.

The fixture needs to hold probes at their correct heights and control insertion depth consistently across all probe types. The ideal solution is a universal fixture, or at most 2 fixtures (one universal, one for small probes with a guide insert). Either 1 or 2 materials is acceptable — one for hot, one for cold, or one material for both ranges. A possible scope reversal to a two-jig design is under consideration — see Open Questions. I took pictures of the existing jig for reference.

### SAP to Model Mapping

| Model | SAP Number |
|---|---|
| 5606 | 131256 |
| 5622-10 | 133504 |
| 5622-32 | 129004 |
| 5623B | 117460 |
| 5628-12-S | 135173 |

The target timeline is May 2026, with June acceptable if needed. As of the 2026-04-22 meeting, the fixture approach is confirmed as one universal metal fixture. Open decisions remaining include specific metal alloy selection and whether the fixture/lid will be fabricated or purchased. The 7380 bath and CMC backup bath are confirmed out of scope as of the 2026-06-10 meeting.

A draft SOP exists for the calibration and verification procedure these probes go through. See [[My Projects/Calibration Probe Fixture/Technical Specs/Fluke In-House SOP\|Fluke In-House SOP]] (live SharePoint Word doc, originally titled "Fluke Draft," draft rev 52, now "Fluke In-House 3.0"). The procedure covers the Fluke 1523 reference thermometer (the instrument being calibrated), the 1586A Super-DAQ module (used with the SPRT during configuration), and TPW module 9210 (the Triple Point of Water bath unit). The probe models in scope per the SOP are 5606, 5622-32, 5622-05, 5622-10, and 5623B; the 5628-12-S is in the [[My Projects/Calibration Probe Fixture/Technical Specs/Bath and Probe Spec\|Bath and Probe Spec]] and may or may not be in the SOP — verify against the live document. Software used includes TableWare (for generating ITS-90 coefficients) and IO ToolKit (for uploading coefficients to the 1523).

> [!info]- Details & Notes
>
> **Probe types:** 5 probes in scope per [[My Projects/Calibration Probe Fixture/Technical Specs/Bath and Probe Spec\|Bath and Probe Spec]]. See [[My Projects/Calibration Probe Fixture/Probe Summary\|Probe Summary]] for the consolidated table.
>
> **Bath details:** 4 baths confirmed in Feynman Metrology; all share the same lip per kickoff meeting. The 7380 bath is confirmed out of scope (2026-06-10 meeting). The CMC backup bath is confirmed out of scope (2026-06-10 meeting). [[People/Kimberly Steinhauer\|Kimberly]] also refers to smaller baths as "baby baths" — possibly 2 coming to Feynman, count unconfirmed. Baby baths go to 220°C.
>
> **Bath models (from SOP):** Heat Source 1: 7381-26 (ethanol medium, covers -80°C and -38°C); Heat Source 2/3: 7341-16 (5010 medium, covers -38°C to 80°C); Heat Source 4: 6331-156 (5014 medium, covers 157°C and 280°C). 7380 confirmed out of scope (2026-06-10).
>
> **Probe models in scope:** 5606, 5622-10 (covers 5622-05 functionally), 5622-32, 5628-12-S, 5623B. The 5628-12-S was missing from earlier project notes; surfaced from the [[My Projects/Calibration Probe Fixture/Technical Specs/Bath and Probe Spec\|Bath and Probe Spec]] on 2026-05-15.
>
> **Junction cable:** Connects probe to computer/instrument; rated to 90°C. One cable per bath required.
>
> **Calibration/verification frequency:** Verification every 6 months; full calibration every 12 months; calibration satisfies verification when they coincide. Full range cycle runs 14-20 times per year.
>
> **Software tools:** TableWare (generates ITS-90 coefficients from calibration data); IO ToolKit (uploads coefficients to the Fluke 1523 via serial connection)
>
> **Temperature range in scope:** -80°C to 280°C (oil bath range); -90°C dry block exists but is out of scope
>
> **Fixture approach:** Universal metal fixture confirmed at 2026-04-22 meeting; possible reversal to two-jig design under consideration (see Open Questions).
>
> **Unknowns:** Fixture/lid may be purchased rather than fabricated; spanner tool and collet design TBD; number and location of baby baths unconfirmed.
>
> **Probe summary:** [[My Projects/Calibration Probe Fixture/Probe Summary\|Probe Summary]]
>
> **Live shared documents:** [[My Projects/Calibration Probe Fixture/Technical Specs/Bath and Probe Spec\|Bath and Probe Spec]] (SharePoint Excel), [[My Projects/Calibration Probe Fixture/Technical Specs/Fluke In-House SOP\|Fluke In-House SOP]] (SharePoint Word doc)
>
> **Probe manuals (PDFs in Technical Specs/):** [5606_5607_Probe.pdf](/img/user/My%20Projects/Calibration%20Probe%20Fixture/Technical%20Specs/5606_5607_Probe.pdf), [5622_Probe_Technical_Data.pdf](/img/user/My%20Projects/Calibration%20Probe%20Fixture/Technical%20Specs/5622_Probe_Technical_Data.pdf), [5623B_Probe.pdf](/img/user/My%20Projects/Calibration%20Probe%20Fixture/Technical%20Specs/5623B_Probe.pdf), [5626_5628_Probe.pdf](/img/user/My%20Projects/Calibration%20Probe%20Fixture/Technical%20Specs/5626_5628_Probe.pdf)
>
> **Materials research:** [[My Projects/Calibration Probe Fixture/Calibration Probe Fixture - Materials Research 2026-05-12\|Calibration Probe Fixture - Materials Research 2026-05-12]] — alloy down-select, insulation barrier comparison, three design paths
>
> **Meeting notes:** [[Other/Metrology Meeting 2026-04-22\|Metrology Meeting 2026-04-22]], [[Other/Metrology Meeting 2026-06-10\|Metrology Meeting 2026-06-10]]
>
> **Encountered in:** Intern Project Kickoff meeting, 2026-03-31
>
> **See also:** [[My Projects/Calibration Probe Fixture/Probe Summary\|Probe Summary]], [[My Projects/Calibration Probe Fixture/Technical Specs/Bath and Probe Spec\|Bath and Probe Spec]], [[My Projects/Calibration Probe Fixture/Technical Specs/Fluke In-House SOP\|Fluke In-House SOP]], [[My Projects/Calibration Probe Fixture/Calibration Probe Fixture - Materials Research 2026-05-12\|Calibration Probe Fixture - Materials Research 2026-05-12]], [[People/Kimberly Steinhauer\|Kimberly Steinhauer]], [[People/Matt Wahl\|Matt Wahl]], [[People/David Velazquez\|David Velazquez]], [[People/Ali Heinemann\|Ali Heinemann]], [[Buildings/Feynman\|Feynman]], [[Buildings/Chappelle Manufacturing Center\|Chappelle Manufacturing Center]], [[Definitions/Metrology\|Metrology]], [[Definitions/Resistance Temperature Detector\|Resistance Temperature Detector]], [[Definitions/Materials/316L Stainless Steel\|316L Stainless Steel]], [[Definitions/Materials/PEEK\|PEEK]]
