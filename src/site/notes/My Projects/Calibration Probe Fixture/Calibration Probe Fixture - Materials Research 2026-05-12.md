---
{"dg-publish":true,"permalink":"/my-projects/calibration-probe-fixture/calibration-probe-fixture-materials-research-2026-05-12/","tags":["My-Projects","reference"],"dg-note-properties":{"aliases":["Metrology Fixture Materials Research"],"tags":["My-Projects","reference"],"source":"personal_notes","last_updated":"2026-05-15"}}
---


#My-Projects

> [!warning] Document age and scope drift
> This research was written on 2026-05-12 based on the project scope known at that time. Since then, several pieces of information have surfaced that may invalidate or shift specific recommendations:
>
> - **5628-12-S in scope.** This probe (12 in long, 1/4 in diameter, rated 661 °C) was missing from the project notes when this research was done. The fixture footprint and slot count below assumed 5 probes; with the 5628-12-S it is 6 (or 5 if 5622-05/-10 share a slot).
> - **7380 bath possibly in scope.** The [[My Projects/Calibration Probe Fixture/Technical Specs/Bath and Probe Spec\|Bath and Probe Spec]] lists a 7380 bath with a 3 x 4 in opening using Halocarbon 0.8 Oil. If this is in scope, the "all baths share one opening" finding (Section 1) is wrong and the universal-fixture rationale needs revisiting.
> - **Two-jig design likely.** The two-jig approach (hot and cold separate) is gaining momentum as the design develops. The 6331 (280 °C) bath being so different from the others makes a dedicated hot jig look like the cleaner path. If that happens, the recommendation toward one universal lid is obsolete — the hot jig becomes a much simpler one- or two-slot design for the 5622-32 only, and the cold/mid jig drops the 280 °C constraint.
> - **Vent holes are permitted.** Per [[People/David Velazquez\|David]], a sealed lid is only for speeding up bath ramp time, not for accuracy. Vent holes are explicitly allowed on all jigs and especially relevant for the hot jig. This changes the thermal model: hot vapor isn't necessarily trapped against the underside of the lid or against PEEK bushings. The PEEK-vs-Macor decision for the 280 °C case may resolve in PEEK's favor with vent holes, but this should be confirmed by test or measurement before committing.
> - **5622-05 phase-out claim retracted.** Per [[People/David Velazquez\|David]], the 5622-05 is not being phased out. It is grouped with 5622-10 in the [[My Projects/Calibration Probe Fixture/Technical Specs/Bath and Probe Spec\|Bath and Probe Spec]] and the fixture should be designed around the 5622-10 dimensions to accommodate both.
> - **5606 is the dangling probe.** Per [[People/David Velazquez\|David]] (Teams, 2026-04-02). The lower tube carrier design is driven by this probe specifically.
>
> The underlying material science (alloy comparisons, thermal calcs, insulation properties) remains valid regardless of these scope shifts.

Materials and design research for the [[My Projects/Calibration Probe Fixture/Calibration Probe Fixture\|Calibration Probe Fixture]] project, prepared 2026-05-12 after the 2026-04-22 Metrology meeting pivoted the design from all-polymer to universal metal fixture. This document explores metal alloy options, insulation barrier options, Fluke bath and probe specifications, and presents three fully fleshed-out design paths with bills of materials and fabrication approaches.

---

## TL;DR

- Build the fixture body from 316L stainless steel (matching the bath wetted-parts material) with PEEK probe-contact bushings as a thermal/mechanical break, plus a small open-frame lower carrier that cradles the 1.5 ml reaction tubes concentric with each probe. This single combination covers the entire –80 °C to +280 °C workload, is fully compatible with silicone oil, 90% ethanol, and IPA, machines on the lathe/drill press/Zund/water-jet already available, and is the only path that needs no second insulation material across the full range. Titanium is the only "single-material no-bushing" alternative worth considering but it costs ~5–10× more and machines slowly.
- Drop elastomer insulation barriers as the primary thermal break. No single elastomer covers –80 °C to +280 °C: HNBR brittles around –35 to –40 °C, FKM (Viton) embrittles ~–20 °C (specialty low-T grades to –35 °C), and even FFKM (Kalrez 0040, the lowest-T perfluoroelastomer) only reaches –42 °C. Silicone rubber covers the temperature range but swells in silicone oil because the two materials are chemically the same family — a documented and well-known failure mode. Use elastomers only as secondary seals/O-rings outside the bath, not as the load-bearing thermal break submerged in fluid.
- Heat-loss math says the thermal-stability fear from the 2026-04-22 pivot is overstated. A reasonable 316L stainless lid (e.g., 6 mm thick, 120 × 172 mm) loses on the order of 10–50 W to ambient at the 280 °C extreme — well within the bath's heater authority (these baths reach 300 °C with multi-kW heaters). Bath uniformity (±0.005 to ±0.025 °C) is dominated by internal convection set by the controller and stir baffle, not by lid conduction. Confirming this empirically by measuring lip and fixture-top temperatures during the May/June build remains the right closeout step — including running the PEEK lip-temperature test that was deferred when the team pivoted to metal, since PEEK bushings are now part of the metal-path design.

---

## Key Findings

### 1. The three Fluke baths share an identical opening — design one fixture for all

All four "Deep-Well Compact Bath" siblings (7381, 7341, 6331, plus 6330 family) use the same 120 × 172 mm (4.7 × 6.8 in) rectangular access opening and the same 457 mm (18 in) tank depth, with 15.9 L (4.2 gal) working volume. Wetted parts are 304 stainless on the 7381, explicitly confirmed by Fluke. The 7341 and 6331 are from the same product family and almost certainly share that wetted-parts material, but this should be verified for the 6331 from its own user guide before assuming. A single fixture footprint will drop into all four Feynman Metrology baths interchangeably.

Ryan should still physically measure the lip-thickness/flange profile and the existing jig dimensions at [[Buildings/Feynman\|Feynman]] and [[Buildings/Chappelle Manufacturing Center\|CMC]], because the published spec only gives the opening — the surrounding flange/lid geometry is not in the datasheet and is what your fixture has to register against. For the CMC backup bath (a different/larger model), the lip profile is reported to potentially differ; do not assume parts interchange until measured. The forthcoming "baby baths" (count and model unconfirmed, going to 220 °C) need their lip dimensions and opening type confirmed before the fixture geometry is finalized — a scaled-down version of the same design philosophy is straightforward, but only if the openings are known.

### 2. The 280 °C requirement is driven by ONE probe (5622-32); ceiling is actually 300 °C

The Fluke 6331 bath is rated 35 °C to 300 °C and the 280 °C calibration point is well within its range; stability/uniformity at 300 °C are ±0.015 °C / ±0.020 °C (Fluke). Fixture materials must be comfortably good past 280 °C with margin, ideally to 300+ °C continuous. This is why Torlon PAI (260 °C) and PPS/Ryton (~220 °C) were correctly ruled out — they have no margin.

The 5622-32 is a 200 mm × 3.2 mm (8 in × 0.13 in) 316 stainless-sheathed PRT rated –200 °C to +350 °C (per Fluke 5622-series datasheet — the family rating; the 5622-32-specific page does not separately call out a different limit). Cable: PVC, 2 m long, 90 °C max. The cable rating is the binding constraint on how far above the bath surface the fixture must hold the probe handle / cable transition.

Other probes for the fixture (all confirmed from Fluke datasheets):

- 5606-50 "Full Immersion PRT": 50 mm × 3.1 mm (1/8 in) 316 stainless sheath, –200 to +160 °C, 8 ft enameled copper lead, fully immersible including the lead wire. This is the "dangles deepest" probe in your context. Above 160 °C is not allowed, so the fixture must accommodate the 5606 being skipped on the 6331 (157/280 °C) bath but used on the 7381 (–80 °C).
- 5622-05: 100 × 0.5 mm sheath, 316 SS, –200 to +350 °C (grouped with 5622-10 in [[My Projects/Calibration Probe Fixture/Technical Specs/Bath and Probe Spec\|Bath and Probe Spec]]; design around 5622-10 dimensions accommodates both)
- 5622-10: 100 × 1.0 mm sheath, 316 SS, –200 to +350 °C
- 5623B: 152 mm × 6.35 mm (6 in × ¼ in) Inconel 600 sheath, –100 to +156 °C, PTFE-insulated 22 AWG silver-plated copper leads. Like the 5606, not usable on the 6331 high-temp bath.

Immersion-depth rule of thumb (Fluke): 20 × probe diameter + sensor length. For the 5622-32 (3.2 mm dia, ~28 mm sensor): 20 × 3.2 + 28 ≈ 92 mm minimum below fluid surface. The 5606 is rated full-immersion. The 5623B needs ≥114 mm (4.5 in) to avoid stem effect (per its user guide). With a 457 mm tank depth, all probes have ample room.

### 3. Heat loss through a metal fixture is small relative to bath authority — verify, don't fear

Quick order-of-magnitude calc for a worst-case scenario (steady state, 6 mm thick × 120 × 172 mm fixture plate sitting on a 280 °C bath, ambient 22 °C):

- 1-D conduction through plate edge to ambient: Q ≈ kAΔT/L. For 316L (k ≈ 14.5 W/m·K) the plate itself is essentially isothermal end-to-end; the rate-limiting resistance is convection from the top of the plate to air (h ≈ 5–15 W/m²·K for natural convection). With plate top area ≈ 0.021 m² at ~250 °C surface and ΔT ≈ 230 °C, Q ≈ h·A·ΔT ≈ 10 × 0.021 × 230 ≈ 48 W worst case bare metal.
- For the same fixture in 6061 aluminum (k = 167 W/m·K, ~10× SS), conduction is even less limiting; loss is still ~50 W (air-side limited).
- For PEEK (k ≈ 0.25 W/m·K), top surface stays much cooler, but the fixture also loses heat down through the fixture body via convection from its underside, which is the same regardless of material if the bottom face contacts the fluid.

The 6331 bath reaches 300 °C with a quoted 250-minute heat-up from 35 °C, implying steady-state heater power on the order of several kW. A 50 W edge loss is in the noise. What matters for uniformity is whether the fixture disturbs the stir-flow pattern, not its conducted heat loss. Design the fixture to (a) sit on the lip rather than dunk a thick block deep into the working volume, (b) be open enough that fluid can still circulate around the probes, (c) keep submerged cross-section small, and (d) leave the original Fluke stir baffle and overflow drain clear.

### 4. Elastomer insulation barriers cannot span –80 °C to +280 °C; silicone is disqualified by silicone-oil swelling

- Standard NBR/Buna-N: ~–40 °C to +100 °C. Already ruled out — confirmed correct.
- HNBR (hydrogenated nitrile): typical –30 to +150 °C; low-ACN special grades reach ~–40 °C Tg per LANXESS Therban / Zeon Zetpol / Apple Rubber low-T HNBR data. Does not reach –80 °C. Also tops out around 150 °C, far below 280 °C.
- FKM / Viton: ~–20 to +230 °C standard, specialty low-T grades to –35 °C. Misses both ends.
- FFKM / Kalrez: standard –20 °C to +327 °C; Kalrez 0040 is the lowest-T grade at –42 °C. Still does not reach –80 °C. Excellent chemical resistance and reaches 280 °C, but cryogenic side fails.
- Silicone rubber (VMQ): –60 to +230 °C is the headline range, and specialty PVMQ grades reach –100 °C, which would actually cover the cold side. But silicone rubber swells in silicone oil because they are the same polymer family. This is a well-documented incompatibility — silicone oil is considered "good with most elastomers EXCEPT silicone rubber." Fluke's 5010 (in the 7341) and 5012/5014/5017 silicone oils are exactly the bath media used in three of your four baths. Disqualified.
- Fluorosilicone (FVMQ): developed specifically to solve the oil-swell problem of VMQ; –60 to +175 °C. Doesn't reach –80 °C and doesn't reach 280 °C.
- EPDM, Aflas: both fall short on the cold side (–40 to –50 °C lower limit) and one or both ends on the high side; not contenders.

Conclusion: there is no single elastomer that covers –80 to +280 °C in silicone-oil-compatible form. Any elastomer-based design needs two different elastomer parts (one set used at low temp, swapped out at high temp) — which violates "universal" fixture intent — or the elastomer must move out of the active thermal break role and serve only as a static seal/cushion outside the bath at near-ambient temperatures, where elastomer choice is unconstrained.

### 5. The right "insulation" path is a rigid polymer or ceramic bushing in a metal frame

Materials that do span –80 °C to +280 °C as rigid inserts:

- PEEK (unfilled): typical –65 °C to +250 °C continuous, short excursions to 260–280 °C; chemical inertness in silicone oil, ethanol, IPA all excellent. Was your team's leading polymer candidate. The PEEK lip-temperature test was never performed because the team pivoted to metal — that test should still be the first thing done in May. PEEK as a small bushing (not the whole structure) sees lower temperatures than PEEK as the whole lid (because the metal carrier conducts heat away from the bushing's outer surface), making the 280 °C question more comfortable than it was for the all-polymer concept.
- PCTFE (Kel-F): –240 °C to +200 °C. Reaches cryo easily but fails the 280 °C bath. Also expensive and creep-prone like PTFE.
- Polyimide (Vespel SP-1 or DuPont equivalents): –240 °C to +290 °C continuous, excellent insulator (k ≈ 0.35 W/m·K). Same sourcing problem your team already identified — McMaster does carry SP-1 round stock in limited sizes (e.g., McMaster 8537K family) and that should be re-checked specifically as bushing rod rather than as bar stock if Path A's PEEK fails.
- Macor (machinable glass-ceramic, Corning): stable to 800 °C continuous, k = 1.46 W/m·K (~10× lower than 316SS), CTE ≈ 9.3 × 10⁻⁶/K (matches metals well). Machines with standard carbide tooling. Caveat: thermal shock sensitivity — Corning explicitly warns against rapid heat-up/cool-down cycles, and your –80 → +280 °C workload involves repeated thermal cycling. Bushings should be kept thin (<5 mm wall) and gradually heated. Available from Corning, Final Advanced Materials, Precision Ceramics, and McMaster carries small Macor rod stock (McMaster 8489K family).
- Shapal Hi-M Soft: machinable aluminum-nitride composite, k ≈ 90 W/m·K (a thermal conductor, so the wrong choice if you want insulation — useful only if you specifically want geometric stability without insulation benefits).
- Alumina (Al₂O₃, 96–99%): k ≈ 25–30 W/m·K, –250 °C to ≥1500 °C, very chemically inert, more thermal-shock tolerant than Macor. Cannot be machined easily; buy as pre-formed bushings/tubes from Coorstek or McMaster (alumina tube McMaster 8746K family).

### 6. Metal alloy down-select — 316L is the right answer

Combining published thermal conductivity (W/m·K at ~25 °C), machinability, –80 °C toughness, chemical compatibility with all three fluids, and procurement realism:

| Alloy | k (W/m·K) | CTE (×10⁻⁶/K) | Service to –80 °C | Service to 300 °C | Machinability (1100=Al ref) | Cost ($/in³ ballpark, plate) | Silicone oil | Ethanol | IPA | Verdict |
|---|---|---|---|---|---|---|---|---|---|---|
| 316/316L SS | 14–16 | 16 | ✅ tough, austenitic FCC | ✅ continuous | ~45 (work-hardens; carbide tooling, slower feeds) | ~$3–5 | ✅ Excellent | ✅ Excellent (better than 304 for any chloride traces) | ✅ Excellent | Recommended primary |
| 304 SS | 16 | 17.2 | ✅ | ✅ | ~45 | ~$2–4 | ✅ | ✅ | ✅ | Acceptable; 316L preferred for ethanol pitting margin and probe-alloy match |
| Aluminum 6061-T6 | 167 | 23.6 | ✅ ductile at LN₂ | ⚠️ softens above ~200 °C; 300 °C is near solutionizing | ~360 (excellent) | ~$1–2 | ✅ | ⚠️ Generally OK at room T; can pit in wet ethanol at elevated T; anodize for safety | ✅ | Disqualified by 280–300 °C service & ethanol-corrosion risk |
| Titanium Gr 2 (CP) | 16–22 | 8.6 | ✅ ductile | ✅ to 425 °C | ~30 (slow, work-hardens; carbide+coolant) | ~$25–35 | ✅ Outstanding | ✅ | ✅ | Strong alternative; cost & machining time penalty |
| Titanium Gr 5 (6Al-4V) | 6.7–7.2 | 8.6 | ✅ | ✅ | ~22 (harder than Gr 2; fire-risk swarf) | ~$40–60 | ✅ | ✅ | ✅ | Best thermal-isolation metal; expensive and slow on a co-op lathe |
| Brass (C360) | ~115 | 20.5 | ✅ | ✅ | 100 (free-machining benchmark) | ~$5–8 | ✅ | ⚠️ Can tarnish/dezincify with ethanol over time | ✅ | Not recommended — high k undermines thermal-break intent; dezincification risk |
| Inconel 625/600 | 9.8–14 | 13 | ✅ | ✅ | ~15 (very slow, very hard) | ~$50–80 | ✅ | ✅ | ✅ | Overkill; same k as SS at 5–10× cost |
| Hastelloy C-276 | ~11 | 11–12 | ✅ | ✅ | ~15 | ~$70–100 | ✅ | ✅ | ✅ | Overkill |

(Note: the specific cost figures above are typical small-quantity plate-stock values from McMaster and industrial distributors and should be re-quoted at order time; they were not all individually web-verified in this session — see Caveats.)

Why 316L over 304: The 7381 ethanol bath at –80 °C has wetted parts in 304SS, which Fluke chose for it, so 304 is provably fine here. But 316L is only marginally more expensive in small quantities, and 316L has slightly better pitting/chloride resistance with any ethanol/IPA contamination over years of service. The probes themselves (5606, 5622-series) are 316 SST — using the same alloy avoids dissimilar-metal galvanic concerns at probe-fixture contact points.

Why not titanium: Titanium Gr 5 has the best thermal-isolation profile (k ≈ 7, vs 16 for stainless), but: (a) cost is 5–10× stainless; (b) machining on a typical co-op shop lathe is slow, requires sharp carbide, flood coolant, and creates fire-risk swarf; (c) the calculated thermal advantage is small in absolute terms because the bath's heater overcomes 50 W trivially. The juice is not worth the squeeze.

Why not aluminum: Two showstoppers. (1) 6061-T6 begins to lose properties significantly above 200 °C and the alloy's solutionizing temperature is around 530 °C — running it continuously at 280 °C will anneal the part and risk creep, especially under the weight of a fixture loaded with probes. (2) Aluminum-ethanol corrosion is a real concern: dry ethanol attacks unprotected aluminum, and the reaction can accelerate with temperature or moisture. While –80 °C ethanol service is benign, repeated wipe-down with IPA and any moisture creates corrosion conditions. Anodizing helps but isn't a typical co-op-shop process. Combined, 6061 is the wrong material for a universal fixture.

### 7. Existing Fluke OEM accessory landscape

Fluke sells the LIG (Liquid-in-Glass) Thermometer Calibration Kit as the standard accessory for the 6331/7341/7381 baths, consisting of a "fluid level adapter tube" that raises the meniscus to within 12 mm of the bath top surface, plus a "thermometer carousel" for up to ten LIG thermometers. That carousel design is the closest OEM analogue to what you're building, and reviewing it would directly inform your design. The 6332A/7342A (next-gen siblings) explicitly offer an "optional probe holding fixture" — Fluke confirms this product line uses fixtures of this style.

Action: contact Fluke Calibration sales to request a quote and dimensional drawing of the LIG carousel and the 6332A probe-holding-fixture accessory. Even if you don't buy them, the OEM design choices (carousel geometry, attachment to the access opening, probe registration features) are a free reference design. None of these OEM products as documented holds 1.5 ml reaction tubes — that part appears to be a Promega-specific need that requires custom fabrication regardless of what OEM accessory exists.

### 8. Design pattern literature — best practices and gaps

Established best-practice rules for liquid-bath probe holders (drawn from Fluke user-guide guidance and standard thermometry practice):

- Insertion depth ≥ 20 × probe diameter + sensor length (Fluke's published rule across multiple user guides; this minimizes stem-conduction error).
- All probes at the same depth in a multi-probe calibration to ensure they sit in the same isothermal stratum of the bath (Fluke 7381 user guide).
- Probe handles must not be submerged (Fluke 7341 user guide); above-bath cable transition temperature must respect cable jacket rating (90 °C for the 5622 PVC).
- A removable heat shield around probe handles is recommended in Fluke's own guidance for high-T calibration; this can be as simple as aluminum foil or as engineered as a machined collar.
- Slow ramp rates to protect both the probe and any ceramic fixture parts from thermal shock.
- Vapor-loss sealing — at 280 °C silicone oil mists and vaporizes; the access opening should be substantially covered to retain oil and reduce ambient odor and operator exposure. A solid (non-airtight) lid that bridges the opening with cutouts only where probes pass through is the standard solution. Your fixture is functionally this lid.
- Allow for thermal expansion of probes — over a 360 °C span a 200 mm stainless probe grows ~1.2 mm; the bushing-to-probe fit should be a clearance slip-fit, never a press fit, to permit free axial growth.

Explicit gaps: NIST Special Publications on thermometer calibration fixtures (e.g., SP 250 series), ASTM E77 / E563 / E644 standards for thermometer comparison testing, Isotech and Hart Scientific application notes on multi-probe fixtures, and any patent literature for calibration-bath probe holders. These should be a 30-minute literature pass before final design freeze — none is likely to overturn the recommendations above, but they may surface specific dimensional best-practices (e.g., minimum clearance between probes, depth-stop tolerances) worth incorporating.

---

## Details

### Bath specifications (confirmed from Fluke datasheets/manuals)

| Parameter | 7381 (Heat Source 1) | 7341 (Heat Source 2/3) | 6331 (Heat Source 4) |
|---|---|---|---|
| Temperature range | –80 to +110 °C | –45 to +150 °C | +35 to +300 °C |
| Promega service temps | –80, –38 °C | –38 to +80 °C | +157, +280 °C |
| Stability | ±0.005 to ±0.006 °C | ±0.005 °C | ±0.007 °C @ 100 °C → ±0.015 @ 300 °C |
| Uniformity | ±0.007 °C across range | ±0.007 °C | ±0.007 → ±0.020 °C |
| Access opening | 120 × 172 mm (4.7 × 6.8 in) | 120 × 172 mm | 120 × 172 mm |
| Tank depth | 457 mm (18 in) | 457 mm | 457 mm |
| Volume | 15.9 L | 15.9 L | 15.9 L |
| Wetted parts | 304 SS (Fluke-explicit) | 304 SS (presumed, same family) | 304 SS (presumed; verify) |
| Stabilization time | 15–20 min | 15–20 min | 15–20 min |
| Bath fluid (Fluke recommended) | Ethanol or oil 5012 | Oil 5010 | Oil 5012 (low) / 5017 (high) |

Action items for Ryan to physically verify at Feynman: (a) flange/lip thickness above the 120×172 mm aperture, (b) any retaining feature around the opening (recess for lid, etc.), (c) actual lip height above bench surface, (d) clearance for cable strain reliefs to rise above 90 °C "warm zone." For the CMC backup bath, the lip profile is reported to potentially differ — get measurements before designing CMC-compatible features. For the future baby baths, get model numbers as soon as they're identified so the lip dimensions can be cross-checked; the Path A design scales but only if openings are confirmed.

### Probe geometry summary (confirmed)

| Probe | Sheath Ø × L | Sheath material | Lead wire | Lead temp limit | Service temp | Used on bath(s) |
|---|---|---|---|---|---|---|
| 5606-50 | 3.1 mm × 50 mm | 316 SS | 0.2 mm enameled Cu, 2.4 m | –200 to +160 °C (full immersion) | –200 to +160 °C | 7381 only (cold) |
| 5622-05 (phasing out) | 0.5 mm × 100 mm | 316 SS | PVC, 2 m | 90 °C | –200 to +350 °C | All |
| 5622-10 | 1.0 mm × 100 mm | 316 SS | PVC, 2 m | 90 °C | –200 to +350 °C | All |
| 5622-32 | 3.2 mm × 200 mm | 316 SS | PVC, 2 m | 90 °C | –200 to +350 °C | All; only one used at 280 °C |
| 5623B-6 | 6.35 mm × 152 mm | Inconel 600 | PTFE, 22 AWG silver-plated Cu, 6.1 m | –100 to +156 °C | –100 to +156 °C | 7381, 7341 (not 6331) |

Design implications:

- Fixture has to hold 5 distinct sheath diameters (0.5 / 1.0 / 3.2 / 3.1 / 6.35 mm) at 5 different lengths (50 to 200 mm). Best solution: interchangeable PEEK bushings — a single metal frame with five (or six, for the 5606) drilled/counterbored receptacles, into which the user drops a labeled bushing matched to the probe in use. The bushing's bottom shoulder rests on the metal counterbore and sets the vertical reference; the probe's collar/handle rests on the bushing's top shoulder and sets the insertion depth. This makes insertion depth a function of bushing geometry rather than operator skill — a quality benefit on top of the universality.
- The 1.5 ml reaction tube (typical OD ~10.5–11 mm, height ~38 mm with hinged cap) is the medium between probe and bath fluid. Hold the tube in a lower carrier plate sitting ~60–80 mm below the main lid plate, with a 11 mm clearance hole that accepts the tube barrel and a small ledge or wire spring that retains the tube cap-up. The lower carrier mounts to the upper lid by 3–4 stainless rod standoffs (¼ in 316L rod, threaded both ends). This puts the reaction tube ~50–100 mm below the fluid surface — within the 92 mm minimum immersion for the 5622-32 and well beyond the 114 mm rule for the 5623B if the lower carrier is positioned at ~120–130 mm below the lip.
- Cable rise height: The 90 °C-rated PVC cables on the 5622 series must stay above the high-temp "warm zone" above the 280 °C oil surface. With the silicone-oil-vapor zone hot for several centimeters above the meniscus, plan the fixture so the cable transition exits ≥ 50–80 mm above the bath top surface. The 5606's enameled copper lead is rated to 160 °C and is less constrained. Build a simple "cable shelf" or cable-relief post welded or threaded to the lid plate.

### Insulation barrier comparison (revised, with cost & sourcing)

| Material | Form | Lower T (continuous) | Upper T (continuous) | k (W/m·K) | Silicone oil | Ethanol | IPA | Cost / availability | Notes |
|---|---|---|---|---|---|---|---|---|---|
| PEEK (unfilled) | Machined bushing | –65 °C | +250 °C (260 short) | 0.25 | ✅ | ✅ | ✅ | ~$40–60 per ½ in × 1 ft rod, McMaster 8504K72 | Preferred bushing material. Run the deferred lip-temp test on day 1. |
| PEEK (30% glass) | Bushing | –65 °C | +260 °C | 0.43 | ✅ | ✅ | ✅ | ~$60–90 per ½ in × 1 ft rod, McMaster | Backup if creep observed |
| Polyimide (Vespel SP-1) | Bushing | –240 °C | +290 °C | 0.35 | ✅ | ✅ | ✅ | $150–300 per ½ in × 6 in rod, McMaster 8537K family (limited sizes) | Best polymer, expensive, limited stock sizes |
| Macor | Bushing | –269 °C | +800 °C | 1.46 | ✅ | ✅ | ✅ | ~$80–150 per ½ in × 6 in rod, McMaster 8489K family | Excellent thermally; thermal-shock sensitive; machinable |
| Alumina 96% | Pre-formed bushing | –250 °C | >1500 °C | 25–30 | ✅ | ✅ | ✅ | $15–40 per pre-formed bushing, McMaster 8746K (tube) family, Coorstek | Buy pre-formed; not machinable in-house |
| Silicone rubber (VMQ) | O-ring/sleeve | –60 °C (PVMQ –100) | +230 °C | 0.2 | ❌ SWELLS | ✅ | ✅ | trivial cost | Disqualified for submerged use in silicone-oil baths |
| HNBR (low-ACN) | O-ring | –40 °C | +150 °C | 0.25 | ✅ | ✅ | ✅ | trivial | Doesn't reach –80 °C, doesn't reach 280 °C |
| FKM (Viton, low-T grade) | O-ring | –35 °C | +230 °C | 0.2 | ✅ | ✅ | ✅ | trivial | Doesn't reach –80 °C |
| FFKM (Kalrez 0040) | O-ring | –42 °C | +220 °C | 0.2 | ✅ | ✅ | ✅ | $$$$ (Kalrez is $20–80 per O-ring) | Standard FFKM up to 327 °C, but cold-end fails –80 °C |
| FFKM (Kalrez 7075) | O-ring | –20 °C | +327 °C | 0.2 | ✅ | ✅ | ✅ | $$$$ | High-T excellent; cold-end fails |
| Air-gap (geometric) | Annular gap | –273 °C | structurally limited | 0.025 | n/a | n/a | n/a | free | Best insulator if geometry permits |

Conclusion of insulation analysis: the question "what elastomer covers –80 to +280 °C in silicone oil?" has no good answer. The pragmatic path is PEEK or Macor bushings + an air-gap design within the metal fixture body. If a soft compliant cushion is also desired for vibration damping or probe-protection above the fluid line, an elastomer can be used there because conditions are mild (room temperature, no fluid contact); FKM or FFKM are robust during IPA wipe-down.

### Thermal-expansion check on probe insertion depth tolerance

Probe insertion depth must remain repeatable to support the "consistent, controlled depth" requirement. Differential thermal expansion of fixture and probe will shift effective depth slightly. Over a ΔT of 360 °C (–80 to +280 °C):

- 316L SS CTE ≈ 16 × 10⁻⁶/K. For a 100 mm holder, ΔL = 100 × 360 × 16e-6 = 0.58 mm.
- 6061 Al CTE ≈ 23.6 × 10⁻⁶/K → ΔL = 0.85 mm.
- Titanium Gr 5 CTE ≈ 8.6 × 10⁻⁶/K → ΔL = 0.31 mm.
- PEEK CTE ≈ 47 × 10⁻⁶/K → ΔL = 1.69 mm (this is one reason an all-PEEK fixture had a hidden problem).
- Macor CTE ≈ 9.3 × 10⁻⁶/K → ΔL = 0.33 mm.

Sub-millimeter shifts over 360 °C are tolerable for these calibrations because (a) the actual fixture geometry that sets insertion depth is the vertical distance from the bath lip to the bushing, which is in the 20–50 mm range, not 100 mm — so divide by ~2–5; (b) Fluke's own immersion guidance (20× diameter + sensor length) is itself a coarse rule with built-in margin. 316L with PEEK bushings has a CTE mismatch (16 vs 47) that wants the bushing to be free-floating in the bore (slip fit + retaining shoulder) rather than press-fit, otherwise the bushing will compress at cold and pop loose at hot. Design rule: bushing OD = bore ID minus 0.05–0.10 mm at room temperature.

---

## Three Fully Fleshed-Out Design Paths

### PATH A (RECOMMENDED): 316L Stainless Frame + PEEK Bushings + Open-Frame Lower Tube Carrier

Concept: A 6 mm thick 316L stainless steel "lid plate" sized to bridge the 120 × 172 mm opening with a small overhang to register on the bath flange. Six counterbored holes (one per probe type plus a spare/blank) accept drop-in PEEK bushings machined to match each probe's sheath diameter with a slip clearance and depth-setting shoulder. Below each bushing, an open-frame lower carrier plate (also 316L, ~3 mm) holds the 1.5 ml reaction tube concentric with the probe, sitting ~120 mm below the lid plate (~50 mm below the fluid surface). Lower carrier mounts to the lid via 3–4 stainless rod standoffs. The lid plate has cutouts (oval slots or open windows) between probe slots so fluid circulation from the stir baffle is not impeded. Cable strain relief is integral — a raised "shelf" (machined post or welded standoff) ~60 mm above the lid plate holds each cable transition, keeping the PVC cable above the 90 °C zone.

Bill of Materials (one fixture set):

| Item | Description | Qty | Source | Est. unit cost | Subtotal |
|---|---|---|---|---|---|
| 316L SS plate, 6 mm × 6 × 8 in | Lid body | 1 | McMaster 8983K family or Promega Parts Order Form (ERSA) | $35 | $35 |
| 316L SS plate, 3 mm × 6 × 8 in | Lower tube carrier | 1 | McMaster | $20 | $20 |
| 316L SS rod ¼ in, threaded both ends | Standoffs (4×) | 4 | McMaster 90575A136 or similar | $5 ea | $20 |
| 316L SS rod 1/8 in × 6 in | Cable shelf posts | 4 | McMaster | $3 ea | $12 |
| PEEK rod stock, ½ in dia × 1 ft | Larger bushings (5622-32, 5623B, 5606) | 1 | McMaster 8504K72 | $50 | $50 |
| PEEK rod stock, ¼ in dia × 1 ft | Smaller bushings (5622-05, 5622-10) | 1 | McMaster | $25 | $25 |
| 18-8 SS socket head cap screws (M4 or 8-32) | Fasteners | ~12 | McMaster | <$10 | $10 |
| Spring wire or SS clip | 1.5 ml tube retainer | 1 | McMaster | $5 | $5 |
| Optional: Macor rod, ½ in × 4 in | Test piece for 280 °C variant bushing if PEEK creeps | 1 | McMaster 8489K family | $80 | $80 |
| Total (without Macor backup) | | | | | ~$177 |
| Total (with Macor backup) | | | | | ~$257 |

Fabrication approach:

1. Water-jet cut the 316L lid plate outer profile and the access window cutouts (Zund or external water jet — 316L 6 mm is within water-jet capability).
2. Water-jet or saw + mill the lower carrier plate; drill its tube-holes.
3. Drill-press the six probe bores in the lid plate oversize, then move to the lathe to bore each receptacle to its final ID + counterbore.
4. Lathe-turn each PEEK bushing: OD to slip-fit the receptacle (clearance 0.05–0.10 mm), ID to slip-fit its probe sheath (0.5, 1.0, 3.2, 3.1, 6.35 mm with 0.05–0.10 mm clearance), shoulder to set depth and prevent fall-through.
5. Machine cable-shelf standoffs on the lathe; thread their bottoms M4 or 8-32; tap matching holes in the lid plate.
6. Cut and thread the four main standoffs that connect lid plate to lower tube carrier; assemble.
7. Deburr, passivate the SS (nitric or citric — nitric preferred for 316L; Promega lab can do this or send out).
8. Engrave/label each bushing slot by probe model.

Thermal performance: Calculated ~50 W heat loss at 280 °C, dominated by air-side convection — within bath heater authority. PEEK bushings keep direct probe-to-metal contact off (probes touch only PEEK), so even if the metal plate is hot on top, heat conduction into the probe through the bushing is small. Do the deferred PEEK lip-temperature test in week 1: set 6331 to 280 °C, run an IR thermometer or a fine-gauge thermocouple at the bushing top surface, confirm <200 °C (well within PEEK).

Chemical compatibility verification: 316L wetted parts already match the bath's own 304 wetted parts. Silicone oil + 316L = excellent (industry standard for oil baths). Ethanol + 316L = excellent. IPA wipe = trivial. PEEK is essentially inert to all three. No incompatibility.

Risks / unknowns:

- (Low) PEEK creep under sustained 280 °C — mitigated by short bushing length (~20–30 mm), no axial load on bushing, and using 30% glass-filled PEEK if creep is observed in the deferred test.
- (Low) CTE mismatch between PEEK bushing and SS bore — manageable with slip fit + shoulder, not press fit.
- (Medium) Fluid splash / vapor condensation on the cable shelf at high T — mitigate with a small SS heat shield or raise the shelf further (verify against bath cabinet clearance).
- (Low) The 5606 must NOT be used on the 6331 (160 °C limit). Make this clear with bushing labeling and/or physically block its slot on the 6331 fixture variant.
- (Low) The 5623B must NOT be used on the 6331 (156 °C limit). Same labeling/blocking approach.

In-house machinability rating: Easy. Plate is water-jet/Zund. Bores are drill-press + manual lathe. PEEK is one of the most machinable engineering plastics. Co-op-shop appropriate.

---

### PATH B (ALTERNATIVE — single material, no bushings): Titanium Grade 2 Frame, Direct Bores

Concept: Same overall geometry as Path A, but the entire fixture is commercially pure (Gr 2) titanium. Probe bores are reamed directly into the Ti plate to slip-fit each probe sheath. No insulation bushings — Ti's thermal conductivity (~17 W/m·K, similar to SS) combined with its bulk being smaller than a steel equivalent gives modest thermal-break benefit, and Ti is strong enough to be thinner than SS for the same stiffness, reducing thermal mass.

Bill of Materials:

| Item | Description | Qty | Source | Est. unit cost | Subtotal |
|---|---|---|---|---|---|
| Ti Grade 2 plate, 4 mm × 6 × 8 in | Lid body | 1 | McMaster 9039K family or specialty Ti supplier | $120–180 | $150 |
| Ti Gr 2 plate, 3 mm × 6 × 8 in | Lower tube carrier | 1 | McMaster | $80 | $80 |
| Ti Gr 2 rod | Standoffs | as needed | McMaster | $40 | $40 |
| SS fasteners (Ti-compatible) | Fasteners | ~12 | McMaster | $10 | $10 |
| Total | | | | | ~$280 |

Fabrication approach: Same as Path A but slower. Ti requires sharper tools, slower feeds, flood coolant, and the Zund will likely NOT cut Ti — water jet only. Reaming requires patience. Ti swarf is a fire/health hazard with grinding — manage carefully.

Thermal performance: k ≈ 17 W/m·K is essentially identical to 316L (16 W/m·K) — so the much-touted "low thermal conductivity" advantage of titanium only really materializes with Gr 5 (Ti-6Al-4V) at k ≈ 7, which is harder still to machine. No meaningful thermal-isolation advantage over Path A's 316L frame, and direct probe-to-Ti contact actually conducts heat into the probe sheath better than via a PEEK bushing.

Risks / unknowns:

- (High) Cost is ~50–100% above Path A.
- (High) Machining time is ~3× Path A on a manual lathe.
- (Medium) No bushing means if a probe gets stuck or scored, the bore is hard to re-machine in place.
- (Low) Galvanic compatibility with 316 SS probe sheaths is fine in oil/ethanol baths.

Recommendation: Build this only if Path A fails the PEEK lip-temperature test AND you decide the additional cost is justified. Otherwise it's a worse Path A.

---

### PATH C (CONTINGENCY — premium high-T): 316L Frame + Macor Bushings (in 6331 variant only)

Concept: Identical to Path A but the 6331 (280 °C) fixture variant uses Macor bushings instead of PEEK. Macor's CTE matches metals better, has higher temperature ceiling (800 °C), and is rigid (no creep concern at all). The 7381 / 7341 fixtures continue to use cheaper PEEK bushings.

BOM delta from Path A: Substitute Macor rod for PEEK rod for the 6331-variant bushings only, +$60–120 in stock; otherwise identical.

Fabrication: Macor machines on standard carbide tooling but is brittle — drill press and lathe work require sharp tools, light cuts, and care. Promega's tooling can handle it but expect ~2× the machining time of PEEK and budget for breaking 1–2 trial bushings.

Thermal performance: Better than PEEK at high T (no soft point), comparable to PEEK in terms of insulation (k = 1.46 vs 0.25 — Macor is ~6× worse insulator than PEEK, but still ~10× better than 316L).

Risks / unknowns:

- (Medium) Thermal shock: cycling –80 → +280 °C is exactly the load Corning warns against. Mitigate with thin walls (<5 mm), gradual ramp rates (the bath's natural ~250 min ramp is already gentle), and only using the Macor bushings in the 6331 (high-T) fixture, never in the cryogenic 7381.
- (Low) Brittleness if dropped/over-torqued.

When to choose Path C: Use Path C bushings specifically in the 6331 (280 °C) fixture variant if PEEK shows any softening or creep, while keeping PEEK bushings in the 7381/7341 fixtures.

---

### Side-by-side design summary

| Criterion | Path A (316L + PEEK) | Path B (Ti Gr 2 solo) | Path C (316L + Macor) |
|---|---|---|---|
| Coverage of –80 to +280 °C | ✅ (after PEEK lip-temp test) | ✅ | ✅ |
| Material cost | ~$177 | ~$280 | ~$257 |
| Machining time | Low | High | Medium |
| In-house tooling sufficient | ✅ | ⚠️ Zund probably no | ✅ (carbide) |
| Probe-contact thermal isolation | Best (k=0.25 PEEK) | Worst (k=17, direct Ti) | Medium (k=1.46 Macor) |
| Mechanical robustness | Good | Excellent | Fair (brittle bushings) |
| Maintenance / replaceable parts | Easy (swap bushings) | Hard (re-bore plate) | Easy (swap bushings) |
| Risk of in-service failure | Low | Low | Low–Medium (thermal shock) |
| Co-op timeline (May/June) | ✅ Achievable | ⚠️ Tight | ✅ Achievable |
| Overall | Recommended | Backup if A fails | High-T variant |

---

## Recommendations

### Stage 1 (Week 1 of May 2026): Burn down the unknowns the polymer phase left open

1. Run the deferred PEEK lip-temperature test. Take a scrap PEEK piece (rod, plate, or block — even a 3D-printed substitute is acceptable for a rough first read), place it across the 6331 access opening with the bath at 280 °C, and instrument the top surface with a thermocouple or IR thermometer. If the top surface stays below ~220 °C continuous, PEEK bushings are validated. This single measurement is the highest-information action available and was skipped during the polymer phase.
2. Physically measure every Feynman bath's lip profile (depth, lip width, any retaining edge), the CMC backup bath's lip profile (likely different), and the actual handle/cable transition dimensions on each of the five probe models. Photograph the existing jigs.
3. Contact Fluke Calibration sales and request: (a) drawings/dimensions for the LIG kit fluid-level adapter and the 10-probe carousel, (b) drawings for the 6332A/7342A "optional probe holding fixture." Use these as reference design even if not purchased.
4. 30-minute literature pass on NIST SP 250-series thermometer-calibration publications and any ASTM E77/E563/E644 fixture geometry notes — confirms or refines minimum probe-to-probe clearance and depth-stop tolerances.

### Stage 2 (Weeks 2–3 of May): Build Path A prototype

1. Order materials via Promega Parts Order Form (SAP ERSA): 316L plate, PEEK rod stock, 316L rod for standoffs, fasteners. McMaster part numbers above.
2. Water-jet the lid plate outline and access windows; saw/mill the lower carrier plate.
3. Drill+lathe the probe bores in the lid plate; turn the PEEK bushings on the lathe.
4. Machine the standoffs and cable shelf posts; assemble.
5. Passivate the SS parts (nitric or citric).
6. Fit-check on the 7341 bath (mid-range, easiest to work with).
7. Run a calibration cycle at –38 °C, 80 °C, 157 °C, 280 °C and record (a) bath stability deviation with and without the fixture in place, (b) probe-tip temperatures vs reference, (c) bushing condition after thermal cycling.

### Stage 3 (Late May / June): Iterate and validate

1. If PEEK shows any creep, deformation, or temperature concerns at 280 °C: re-machine the 6331-fixture bushings in Macor (Path C bushings) and keep PEEK bushings in the lower-T fixtures.
2. If Path A fails outright (extremely unlikely): pivot to Path B (titanium frame, no bushings) — order Ti plate immediately upon failure decision because lead time is longer.
3. Build the "baby bath" variant fixtures once the baby bath models/quantities are confirmed by Metrology. Same Path A approach scales down.
4. Build the CMC backup-bath variant once that lip profile is measured.

### Decision thresholds — when to pivot

- Pivot from Path A to Path C if: PEEK lip-temperature test exceeds 230 °C continuous, OR post-cycling PEEK bushings show >0.1 mm dimensional change, OR any sign of creep along the loaded sheath bore.
- Pivot from Path A to Path B if: PEEK fails AND Macor breaks during thermal cycling testing (vanishingly unlikely).
- Add an FFKM (Kalrez 7075) O-ring at the bushing-to-metal interface only if vapor leakage at the lid becomes a measurable problem; otherwise an unsealed bushing is preferable for ease of swap.

### Open questions Ryan should still collect

- Existing-jig photos and dimensions (already on his action list per the project context)
- Exact lip thickness and any flange retaining-lip on all 4 Feynman baths AND the CMC backup
- Whether the "baby baths" share the 120 × 172 mm lip profile or differ (this changes whether the fixture is truly universal)
- Cable transition handle dimensions on all 5 probe models (drives cable-shelf design)
- 6331 wetted-parts material — assumed 304 SS by family, verify from the 6331 user guide before final material decision
- Promega's preferred passivation vendor for 316L (in-house or send-out)
- Annual count of full-range cycles per bath (14–20/year stated — confirm whether this is total or per-bath, drives wear-life calc on PEEK)
- 1.5 ml reaction tube exact OD/height tolerance (affects lower-carrier bore size)
- Whether Metrology wants the fixture to also serve as a vapor-loss reduction lid at 280 °C (affects whether to add a solid splash cover above the bushings)

---

## Caveats

- Web-research budget was 12 searches this session, exhausted before Inconel/Hastelloy specifics, Fluke OEM probe-holder accessory pricing, aluminum-ethanol corrosion specifics, and NIST/ASTM thermometer-fixture standards could be web-verified. The values cited for those items reflect standard engineering reference data; before procurement, verify Inconel/Hastelloy properties against MatWeb or AMS specs, verify Fluke OEM accessory pricing by direct Fluke sales contact as recommended in Stage 1, and run the 30-minute NIST/ASTM literature pass.
- The 6331 wetted-parts material is not explicitly confirmed in the materials I retrieved; the 7381 is explicitly 304 SS and the family is presumed consistent, but worth confirming from the 6331 user guide before assuming.
- The 5622-32 specific upper temperature limit is the 5622-series family rating of 350 °C from the Fluke product page; the spec sheet I retrieved does not separately call out a different limit for the -32 size. Promega's stated use to 280 °C is well within that, but the 5622 cable rating of 90 °C remains the binding thermal constraint above the bath surface.
- Thermal calculations are order-of-magnitude estimates based on natural-convection assumptions and steady-state 1-D heat flow. For a publication-grade thermal model, a simple Solidworks Flow Simulation or COMSOL run is warranted but is not necessary to start fabrication.
- Material cost estimates are typical small-quantity values from McMaster and industrial distributors; they were not all individually re-quoted in this session and should be confirmed at order time.
- PEEK lip-temperature test result is the single biggest unknown. All Path A confidence is conditional on that test passing. If it fails decisively, Path C (Macor at the 6331 bath only) is the immediate fallback and is also low-risk.
- Aluminum-ethanol corrosion at elevated temperature is a real, well-documented concern but I could not web-verify a specific corrosion-rate datapoint in this session. The disqualification of 6061 in Path discussion rests on (a) the well-established 200 °C+ softening behavior of 6061-T6 (which alone is disqualifying for 280 °C continuous use), and (b) the secondary corrosion risk; the first reason alone is sufficient.
- The recommendation to drop elastomer barriers as the primary thermal break is robust against the materials surveyed; if a novel formulation surfaces (e.g., a perfluoroelastomer with verified –80 °C performance — not currently in any catalog I found), the conclusion would update accordingly.
- Macor's thermal-shock sensitivity is real but practically manageable here because bath ramp rates are slow (the 6331 takes ~250 min to heat from 35 to 300 °C; the 7381 takes ~210 min to cool from 25 to –80 °C). The fixture is exposed gradually, not plunged into hot bath cold.
- The "polymer phase reasoning" (that metal would compromise bath stability via convective heat loss) is partially valid but quantitatively small — see the thermal calc above. The 2026-04-22 pivot to metal was the right call; Path A in this report addresses the residual concern via PEEK bushings as a probe-side thermal break, not via fixture material choice.
- Design pattern literature gap: NIST SP 250 series, ASTM E77/E563/E644, Isotech and Hart application notes, and patent literature were not searched this session. Path A's geometry is built on first-principles + Fluke user-guide best practices, which is sufficient for the May/June timeline, but a confirming literature pass is recommended before final design freeze.

> [!info]- Details & Notes
>
> **Status:** Reference document. Recommendations pending validation via Stage 1 actions (PEEK lip-temp test, physical bath measurements, Fluke OEM accessory inquiry).
>
> **Encountered in:** [[My Projects/Calibration Probe Fixture/Calibration Probe Fixture\|Calibration Probe Fixture]]
>
> **See also:** [[My Projects/Calibration Probe Fixture/Calibration Probe Fixture\|Calibration Probe Fixture]], [[Other/Metrology Meeting 2026-04-22\|Metrology Meeting 2026-04-22]], [[Definitions/Metrology\|Metrology]], [[Definitions/Resistance Temperature Detector\|Resistance Temperature Detector]], [[People/Kimberly Steinhauer\|Kimberly Steinhauer]], [[People/Matt Wahl\|Matt Wahl]], [[People/David Velazquez\|David Velazquez]], [[Definitions/Materials/316L Stainless Steel\|316L Stainless Steel]], [[Definitions/Materials/PEEK\|PEEK]], [[Definitions/Materials/Delrin\|Delrin]]
