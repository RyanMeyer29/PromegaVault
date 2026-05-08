---
{"dg-publish":true,"permalink":"/my-projects/calibration-probe-fixture/","tags":["My-Projects","active"],"dg-note-properties":{"aliases":["Metrology fixture"],"tags":["My-Projects","active"],"source":"personal_notes","last_updated":"2026-04-23"}}
---


#My-Projects

## Action Items

- [ ] Make report on fixture plan for Metrology meeting Wed Apr 22 — solid plan for cold fixtures, ideas for hot fixture (flagged in 1:1, 2026-04-16)
- [ ] Reach out to Metrology about a metal lid for the fixture (flagged in 1:1, 2026-04-10)
- [ ] Explore rubber gasket and rubber case options for the sensor (flagged in 1:1, 2026-04-10)
- [x] Research fixture materials compatible with -80°C to 260°C, silicone oil, and ethanol (consider machinability, temp range, chemical resistance)
- [ ] Get probe make/model info from Metrology, then look up dimensions online
- [ ] Measure probe dimensions in person
- [ ] Measure bath lip and opening dimensions in person
- [ ] Measure temperature at the bath lip / just above fluid surface when 280°C bath is running — needed to confirm PEEK universal is viable. Bath is open access, can run it independently. Need to find a temperature gun in the facilities shop first.
- [ ] Follow up with [[People/Ali Heinemann\|Ali]] re: metrology lip temp check (flagged in 1:1, 2026-04-03)

**Priority (as of 2026-04-10): #2 of active projects**

---

## Material Considerations

No metal — metal conducts heat from the bath interior to the outside environment via internal convection, which would affect bath stability. All-polymer is the right solution since low bulk thermal conductivity solves this inherently rather than requiring insulation workarounds.

Current direction is PEEK universal — pending confirmation that the bath lip temperature at 280°C operation stays within PEEK's service range. The fixture is non-submerged; it sits at or near the bath lip and does not contact the bath fluid directly. The 5606 is the probe that dangles deepest and may need a guide that extends further into the bath, but even that is likely not fully submerged. The 5622-32 (0.13" dia x 8" long, per David Velazquez) is the only probe that goes to 280°C — it is long and slender enough that it likely does not require a submerged guide. If the lip temperature measurement confirms exposure well below PEEK's continuous rating (~250°C), PEEK as a single universal material is the right call and the two-material split is unnecessary.

If the lip temperature measurement rules out PEEK at the high-temp bath, the next candidate for a high-temp fixture would be Macor (glass-mica ceramic, available on McMaster, rated to 1470°F) — though stock sizes are limited (max ~6"x12") and cost is high (~$650/sheet). PBI (Celazole) is another option worth sourcing if Macor proves impractical.

Materials evaluated and ruled out:
- Delrin/Acetal — max service temp ~90–120°C, cannot handle high-temp baths
- PTFE — creeps and deforms under load, not dimensionally stable enough for controlled insertion depth
- Torlon (PAI) — rated to 500°F (260°C), does not cover the 280°C bath
- Vespel — rated for the full range but not findable through standard suppliers
- PPS/Ryton — max ~220–240°C, does not reach 280°C
- Buna-N aramid gasket material — gasket material, not structural; lower temp limit of -40°F does not cover -80°C bath

---

The Calibration Probe Fixture is a fabrication project to design and build a fixture (or set of fixtures) that holds temperature probes at consistent, controlled depths inside 1.5 ml reaction tubes during calibration in oil baths. The goal is to bring in-house capabilities for temperature standards calibrations that previously required external resources. The project is led by the Metrology department in [[Buildings/Feynman\|Feynman]], with [[People/Kimberly Steinhauer\|Kimberly]] as supervisor and [[People/Matt Wahl\|Matt]] and [[People/David Velazquez\|David]] as the primary contacts. [[People/Ali Heinemann\|Ali]] is also involved.

The baths used for calibration are oil baths covering a temperature range of -80 to 260°C. There are 4 baths total, all located in Feynman Metrology, and all share the same lip profile. A large bath from [[Buildings/Chappelle Manufacturing Center\|CMC]] is also available as a backup. The baths use silicone oil, with isopropyl alcohol used for wiping; one bath uses 90% ethanol and one bath is cold-only (no heating capability). The high-temp portable bath holds approximately 1 gallon; the large baths hold approximately 5 gallons each. A -90°C dry block unit also exists but is out of scope for this project — it does not require a fixture.

There are 5 probe types that need to be accommodated. The two smallest probes are 10 mm and 5 mm; 5 mm probes are being phased out. All probes go into 1.5 ml reaction tubes. The primary challenge with small probes is that they dangle and can swing around inside the tube without a guide. The fixture needs to hold probes at their correct heights and control insertion depth consistently across all probe types. The ideal solution is a universal fixture, or at most 2 fixtures (one universal, one for small probes with a guide insert). Either 1 or 2 materials is acceptable — one for hot, one for cold, or one material for both ranges. I took pictures of the existing jig for reference.

The target timeline is May 2026, with June acceptable if needed. Open decisions remaining include whether to use one material or two for hot/cold ranges, whether to go with a universal fixture or a 2-fixture approach with inserts for small probes, and whether the fixture/lid will be fabricated or purchased. It also needs to be confirmed whether the CMC bath will be needed.

A draft SOP exists for the calibration and verification procedure these probes go through (titled "Fluke Draft," draft rev 52). The procedure covers the Fluke 1523 reference thermometer (the instrument being calibrated), the 1586A Super-DAQ module (used with the SPRT during configuration), and TPW module 9210 (the Triple Point of Water bath unit). The probe models in scope for calibration are the 5606, 5622-32, 5622-05, 5622-10, and 5623B. Software used includes TableWare (for generating ITS-90 coefficients) and IO ToolKit (for uploading coefficients to the 1523).

> [!info]- Details & Notes
>
> **Probe types:** 5 probe types total; 10 mm and 5 mm are the current smallest; 5 mm probes being phased out
>
> **Bath details:** 4 baths in Feynman Metrology, all same lip; silicone oil; one 90% ethanol bath; one cold-only bath; large backup bath from CMC. Kimberly also refers to smaller baths as "baby baths" — possibly 2 coming to Feynman, count unconfirmed. Baby baths go to 220°C.
>
> **Bath models (from SOP):** Heat Source 1: 7381-26 (ethanol medium, covers -80°C and -38°C); Heat Source 2/3: 7341-16 (5010 medium, covers -38°C to 80°C); Heat Source 4: 6331-156 (5014 medium, covers 157°C and 280°C)
>
> **Probe models confirmed in SOP:** 5606, 5622-32, 5622-05, 5622-10, 5623B
>
> **Junction cable:** Connects probe to computer/instrument; rated to 90°C. One cable per bath required.
>
> **Calibration/verification frequency:** Verification every 6 months; full calibration every 12 months; calibration satisfies verification when they coincide. Full range cycle runs 14-20 times per year.
>
> **Software tools:** TableWare (generates ITS-90 coefficients from calibration data); IO ToolKit (uploads coefficients to the Fluke 1523 via serial connection)
>
> **Temperature range in scope:** -80°C to 260°C (oil bath range); -90°C dry block exists but is out of scope
>
> **Fixture approach:** Universal fixture preferred; max 2 fixtures; different inserts per probe type acceptable
>
> **Unknowns:** Material selection not yet decided; fixture/lid may be purchased rather than fabricated; spanner tool and collet design TBD; number and location of baby baths unconfirmed
>
> **Meeting notes:** [[Other/Metrology Meeting 2026-04-22\|Metrology Meeting 2026-04-22]]
>
> **Encountered in:** Intern Project Kickoff meeting, 2026-03-31
>
> **See also:** [[People/Kimberly Steinhauer\|Kimberly Steinhauer]], [[People/Matt Wahl\|Matt Wahl]], [[People/David Velazquez\|David Velazquez]], [[People/Ali Heinemann\|Ali Heinemann]], [[Buildings/Feynman\|Feynman]], [[Buildings/Chappelle Manufacturing Center\|Chappelle Manufacturing Center]], [[Definitions/Metrology\|Metrology]], [[Definitions/Resistance Temperature Detector\|Resistance Temperature Detector]]
