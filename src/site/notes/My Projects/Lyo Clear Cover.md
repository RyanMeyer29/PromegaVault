---
{"dg-publish":true,"permalink":"/my-projects/lyo-clear-cover/","tags":["My-Projects"],"dg-note-properties":{"aliases":["Lyo Cover"],"tags":["My-Projects"],"source":"personal_notes","last_updated":"2026-06-15"}}
---


#My-Projects

## Status

Two fabrication attempts so far. First attempt used cast acrylic stock — material snapped during bending. Identified the original cover as polycarbonate (not acrylic) based on edge tint, scratch test, and flex behavior. Second attempt used polycarbonate stock and generally worked, but the finished piece has bowing from imprecise bends. Before making a third attempt, the plan is to write out step-by-step bend instructions in a notebook first to make the process more controlled and repeatable. Lower priority for now.

## Action Items

- Write out step-by-step bend instructions in notebook before next fabrication attempt
- Cut new polycarbonate sheet to correct dimensions
- Bend carefully per written instructions
- Re-measure an unbent piece with calipers to confirm stock thickness before cutting
- Update SolidWorks model and drawing if dimensions changed
- Get part number and submit through normal parts process
- Submit shop request for fabrication if needed

---

A clear protective cover for the lyophilizer downstairs in [[Buildings/Feynman\|Feynman]], the one that feeds into the finishing room where [[Unknown/Pauls Finishing Panel\|Paul's finishing panel]] work happens. The cover sits over the bottle entry area to keep operators from reaching into the machine while bottles are moving in.

The original cover was made by a European vendor out of 8 mm metric stock. Material was assumed to be acrylic but is now suspected to be polycarbonate based on the evidence described below. The new version will be made from ~~3/8" (9.525 mm) acrylic~~ imperial stock since that's what is available in-house, material TBD pending confirmation. All other dimensions stay the same.

The original had a grid of holes through the top panel. Nobody (Ali, Paul, or otherwise) knows what the holes were for. The new version omits them entirely. Paul specifically asked for the top to be solid so it can be used as a shelf without contaminating what is underneath it.

---

## Material Investigation

Original was assumed to be acrylic based on verbal handoff, but no documentation confirms this. Evidence collected during the failed forming attempt and follow-up comparison:

- Original cover has a mild blue edge tint visible on cut edges and bend regions. Cast acrylic is typically water-clear with no edge tint. Polycarbonate shows a blue/yellow gradient on edges. The blue is consistent with PC, not acrylic.
- Original cover feels mechanically tough rather than ceramic-brittle. Has some perceptible flex when handled (though full thickness makes definitive flex testing difficult). Acrylic at 9 mm thickness should feel rigid with no flex before brittle failure. This leans PC.
- Scratch test: scraping the original with a screwdriver felt "like scratching wood" (softer, marking the surface rather than scraping). The newly-purchased cast acrylic stock under the same screwdriver felt "like scratching glass" (harder, scraping sound). This is consistent with PC being softer than acrylic on the Rockwell M scale (PC ~M70, acrylic ~M85-M105).
- The original survived European fabrication into a bent shape, which is much easier to achieve with PC than with thick acrylic on standard equipment.

Conflicting information online about whether PC or acrylic is appropriate for this application has been noted. PC has its own failure modes (notch sensitivity, sharp internal corners as crack initiators) and is not bulletproof, but is generally more forgiving for hand-formed bends than acrylic at this thickness.

Definitive test pending: acetone drop on a hidden spot of the original. Acrylic crazes/clouds immediately, PC is unaffected.

---

## Forming Attempt (failed)

First fabrication attempt used cast acrylic stock at approximately 0.345" thickness. The file sent to the shop included bend lines as light engravings in the DXF for reference, but the shop machined a slot at the bend line instead of engraving. The slot turned out to be on the inside (compression) side of the bend with approximately 0.135" of material remaining at the slot bottom (about 39% of original stock thickness, within typical guidance for kerf-bending acrylic).

Forming setup was a heat gun (held on a moderate setting, worked back and forth along the bend line for 60+ seconds) followed by clamping in a finger brake. The bend reached approximately 30-45 degrees of the 90 degree target before the material cracked and snapped off at the bend line.

Hypothesized contributing factors:

- Finger brake unable to fully clamp the thick acrylic. Jaws designed for sheet metal don't lock down on plastic of this thickness, so the bend axis was loose and stress concentration unpredictable.
- Cold brake jaws conducting heat away from the thin slot region during the bend. With only 0.135" of material at the bend line, thermal mass was small and contact with room-temperature steel rapidly dropped the bend zone below acrylic's forming temperature (~320°F).
- Heat gun may not have brought the core of the material up to forming temperature uniformly through the full slot depth. Surface heating with a heat gun is harder to control than dedicated strip-heater equipment.
- Material may have been wrong choice entirely. If the original is polycarbonate, the new stock should be too, and PC behaves very differently under heat and bending forces.

---

## Forming Strategy (revised)

Skip the finger brake. Use a hand bend over a workbench-clamped form edge:

1. Clamp the panel to a workbench with the bend line just past the edge of a hardwood or aluminum bar of appropriate inside radius. The bar acts as the form edge.
2. Keep the slot on the inside (compression) side, slot facing up so it closes when the free end folds down.
3. Heat with two heat guns simultaneously, one above and one below the bend line, working back and forth across the full width of the bend for several minutes. The slot region heats faster than surrounding material.
4. Test softness by gently lifting the free end. When it droops under near-its-own-weight, it is at forming temperature.
5. With heat still applied, slowly and continuously fold the free end down over the form edge to 90 degrees. Hold at final angle for 30+ seconds while it cools below forming temperature.
6. Once material holds shape on its own, release.

This removes the cold-clamp problem and gives better control over bend rate and final angle.

Note: if material is confirmed as polycarbonate, the bending becomes significantly easier and may not require the slot or as much heat. PC at this thickness can cold-bend or warm-bend without the same brittle-failure risk as acrylic.

---

## Dimensions (from existing drawing)

| Dimension | Value |
| :--- | :--- |
| Overall length | 540 mm |
| Overall height | 186 mm |
| Bend radius (typ) | R15 |
| Stock thickness | TBD — original is 8 mm metric, new stock pending material decision (target 5/16" or 3/8" in imperial PC, or 11/32"/23/64" if acrylic) |
| Side wall cutout depth | 47 mm |
| Side wall cutout location | 70 to 320 mm |
| Bottle pass cutouts | 487.50 / 463 mm reference |

Cross-section is an inverted U with notched cutouts on each side wall to let bottles pass through underneath.

---

## Holes Discussion

The original had holes through the top. Considered reasons:

- Pressure equalization: ruled out, both ends open
- Visual / sensor access: ruled out, already clear and no sensors
- Cleaning access: ruled out, holes are too small for hands; both ends open already
- Tooling clearance: ruled out
- Sagging relief: ruled out, circular holes create stress concentrations rather than reduce stress
- Operator finger grips: ruled out
- Drainage during cleaning sprays: possible but not confirmed
- Legacy from earlier process: possible, nobody remembers
- Aesthetic / design choice: possible

Decision: omit per Ali. Paul confirmed solid top is preferred.

---

> [!info]- Details & Notes
>
> **Encountered in:** 1:1 with [[People/Ali Heinemann\|Ali]]
>
> **Source drawing:** `Lyo_Clear_Cover.pdf` (existing drawing with dimensions)
>
> **Open questions:**
> - Is the original cover material acrylic or polycarbonate? (Suspected PC pending confirmation.)
> - What is the true stock thickness of the original? (Measured 0.345" but the unbent original needs caliper verification.)
> - Will 6 mm PC be rigid enough if used as shelf surface, or is closer-to-original 8 mm equivalent needed?
>
> **See also:** [[Unknown/Pauls Finishing Panel\|Pauls Finishing Panel]], [[Buildings/Feynman\|Feynman]], [[Definitions/Equipment/Feynman Bottle Lyophilizer\|Feynman Bottle Lyophilizer]], [[People/Ali Heinemann\|Ali Heinemann]], [[People/Paul Doll\|Paul Doll]], [[My Projects/Flipper Tray Blocker\|Flipper Tray Blocker]] (another project for Paul's downstairs lyo area), [[Software/SolidWorks/Solidworks Sheet Metal\|Solidworks Sheet Metal]], [[People/Travis Beyer\|Travis Beyer]], [[Buildings/Lamarr\|Lamarr]]
