---
{"dg-publish":true,"permalink":"/other/metrology-meeting-2026-04-22/","tags":["Other"],"dg-note-properties":{"tags":["Other"],"source":"personal_notes","last_updated":"2026-04-23"}}
---


#Other

Meeting notes for Metrology meeting on 2026-04-22 regarding the [[My Projects/Calibration Probe Fixture\|Calibration Probe Fixture]] project. Attendees include [[People/Kimberly Steinhauer\|Kimberly]], [[People/Matt Wahl\|Matt]], and [[People/David Velazquez\|David]].

## Outcomes (from 2026-04-22)

- Junction cables (connect probe to instrument) are rated to 90°C. One cable is needed per bath.
- Kimberly refers to smaller baths as "baby baths" — these go to 220°C. Possibly 2 coming to Feynman; count not confirmed.
- Full range calibration cycle runs 14–20 times per year.
- The bath lab is open access — can run the bath independently to take the lip temperature measurement. Need to find a temperature gun in the facilities shop first.

---

## Pre-meeting prep

### Main blocker — resolve this first

### Why no metal, and is that rule flexible?

Is it thermal conductivity affecting bath stability? Chemical compatibility with silicone oil or ethanol? Corrosion? Probably a combination, but need to understand the weighting before committing to polymer for the hot bath.

Follow-up angle: if thermal conductivity is the concern, ask whether a polymer gasket or insulating interface between a metal structure and the bath wall would address it. Not proposing a specific design yet — just want to know if the door is open before closing off the material option entirely.

### If metal is off the table at 280°C — what is their reaction to Macor?

Macor (glass-mica ceramic) is the next candidate if PEEK cannot handle the hot bath. Rated to ~1470°F, available on McMaster, but expensive (~$650/sheet) and limited stock sizes. Worth flagging so they understand the tradeoff.

Current position: PEEK universal is the preferred direction for cold and mid-range baths. The only real question mark is the 280°C bath (Heat Source 4, 5014 medium). Not measuring lip temp, so need to either rule PEEK in from their experience or pick an alternate material for that one bath.

---

## Design decisions — need their input

- One universal fixture or two? Preference is universal, but if metal is only viable for the hot bath, that naturally splits. Ask what they want to work with day-to-day.
- Does the 280°C bath need to accommodate all probe types, or just the 5622-32? The 5622-32 is the only probe rated to 280°C — if that is the only probe they would run in Heat Source 4, the hot fixture can be much simpler.
- Confirm which probe models are actually in scope: 5606, 5622-32, 5622-05, 5622-10, 5623B. The 5 mm probes (5622-05?) are being phased out — confirm if still in scope or if the fixture can be designed around them.

---

## Things to collect from them

- Where to find probe spec sheets or dimensional drawings online (Fluke/Hart product pages, datasheets). Want a pointer, not for them to measure.
- Any existing documentation on bath lip and opening dimensions (maintenance records, equipment sheets) for the 4 Feynman baths.
- Is the CMC backup bath actually in scope? If it has a different lip profile, it changes the fixture design or requires adapters.

---

## Context to offer them

Current material thinking: no metal was the direction, but revisiting it for the hot bath. For everything else, PEEK universal is the leading candidate — chemically resistant to silicone oil and ethanol, machinable, dimensionally stable, rated to ~250°C continuous. Materials already ruled out and why: Delrin (max ~90-120°C), PTFE (creep/deformation), Torlon (max 260°C, does not reach 280°C), Vespel (not findable through standard suppliers), PPS/Ryton (max ~220-240°C), Buna-N aramid gasket material (not structural, lower temp limit does not cover -80°C).

Timeline: targeting May 2026, June acceptable. No CAD started yet — this conversation is what unblocks that.

> [!info]- Details & Notes
>
> **Status:** Meeting complete. Outcomes documented above.
>
> **See also:** [[My Projects/Calibration Probe Fixture\|Calibration Probe Fixture]], [[Definitions/Metrology\|Metrology]], [[People/Kimberly Steinhauer\|Kimberly Steinhauer]], [[People/Matt Wahl\|Matt Wahl]], [[People/David Velazquez\|David Velazquez]]
