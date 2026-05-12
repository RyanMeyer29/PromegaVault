---
{"dg-publish":true,"permalink":"/definitions/solid-works-drawings/asme-y14-5-2018/parsed/sec11-tolerances-of-profile-asme-y14-5-2018/","tags":["Definitions","reference-document"],"dg-note-properties":{"tags":["Definitions","reference-document"],"source":"ASME Y14.5-2018","last_updated":"2026-04-30"}}
---


# Sec11 - Tolerances of Profile - ASME Y14.5-2018

**Standard:** ASME Y14.5-2018 Dimensioning and Tolerancing
**Section:** Section 11
**PDF pages:** 258-304

> Note: Profile tolerancing is visually complex. Open PDF at pages 258-304 for figures.
> PDF path: `Definitions/SolidWorks Drawings/ASME Y14.5-2018/ASME-Y14.5-2018-R2024-Dimensioning-and-Tolerancing.pdf`

---

## 11.1 General

Profile tolerances control the form, orientation, and location of surfaces or line elements. Profile tolerances apply to any cross-section or the full surface simultaneously. Two types: profile of a line (2D) and profile of a surface (3D).

## 11.2 Profile

Profile tolerances reference a true profile defined by basic dimensions. The tolerance zone is defined relative to the true profile.

## 11.3 Tolerance Zone Boundaries

### 11.3.1 Bilateral (Equal)
Default when no modifier is shown. The tolerance zone is equally disposed about the true profile — half the tolerance on each side.

### 11.3.2 Unilateral
The tolerance zone is entirely on one side of the true profile. Indicated by the U (circled) modifier followed by the amount of tolerance on the outer side. Example: .010 ⓤ .010 means .010 total, all outside the true profile.

### 11.3.3 Unequal Bilateral
The tolerance zone is disposed unequally about the true profile. Uses the U modifier.

## 11.4 Profile Applications

Profile of a surface applies to the entire surface simultaneously. Profile of a line applies to each cross-section independently.

Profile tolerances may be applied:
- All around: ○ symbol at bend of leader — applies to the entire perimeter shown in that view
- All over: two concentric circles — applies to entire surface of the part
- Between two points: A↔B notation
- For a limited portion: between notation with basic dimensions

## 11.5 Material Condition and Boundary Condition Modifiers

Profile tolerances may use MMC (M) or LMC (L) modifiers when applied to features of size. This allows bonus tolerance as the feature departs from the specified material condition.

## 11.6 Composite Profile

Two-tier feature control frame similar to composite position:
- Upper tier: controls pattern location and orientation relative to datums. Larger tolerance zone.
- Lower tier: controls form and feature-to-feature relationship. Smaller tolerance zone.

## 11.7 Multiple Single-Segment Profile Tolerancing

Two separate profile feature control frames, each fully constrained to their datum references. More restrictive than composite.

## 11.8 Combined Controls

Profile of a surface may be combined with other tolerances (position, orientation) for complex surface requirements.

## 11.9 Profile of a Line as a Refinement

Profile of a line (2D) used as a refinement of profile of a surface (3D) — controls individual cross-sections more tightly than the overall surface requirement.

## 11.10 Dynamic Profile Tolerance Modifier

The dynamic profile modifier D (circled) allows the tolerance zone to shift normal to the true profile while maintaining form control. Used for features where size variation (scaled profile) is acceptable but form variation is not. Primarily used for complex contoured features.

Key figures:
- Fig 11-1 through 11-4: Bilateral, unilateral, and unequally disposed profile zones (PDF p.264-267)
- Fig 11-5 through 11-10: Profile applications — all around, all over, between points (PDF p.268-272)
- Fig 11-19 through 11-25: Coplanar surfaces, stepped surfaces, conical features (PDF p.277-283)
- Fig 11-26 through 11-31: Composite profile tolerancing (PDF p.283-286)
- Fig 11-35 through 11-38: Dynamic profile modifier applications (PDF p.301-304)
