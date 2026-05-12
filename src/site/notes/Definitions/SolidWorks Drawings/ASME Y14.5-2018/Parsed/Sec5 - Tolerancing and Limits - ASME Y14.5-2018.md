---
{"dg-publish":true,"permalink":"/definitions/solid-works-drawings/asme-y14-5-2018/parsed/sec5-tolerancing-and-limits-asme-y14-5-2018/","tags":["Definitions","reference-document"],"dg-note-properties":{"tags":["Definitions","reference-document"],"source":"ASME Y14.5-2018","last_updated":"2026-04-30"}}
---


# Sec5 - Tolerancing and Limits - ASME Y14.5-2018

**Standard:** ASME Y14.5-2018 Dimensioning and Tolerancing
**Section:** Section 5
**PDF pages:** 51-71

> Note: Figures and diagrams in this section are not captured in this text extraction. For visual reference, open the PDF directly at the page range above.
> PDF path: `Definitions/SolidWorks Drawings/ASME Y14.5-2018/ASME-Y14.5-2018-R2024-Dimensioning-and-Tolerancing.pdf`

---

## 5.1 General

5.1.1 Tolerancing Defaults — applies UOS in the title block or drawing notes.

5.1.1.3 Implied 90° Angle Tolerance — where center lines or surfaces are shown at right angles without a specified angle, the implied 90° is controlled by the angular tolerance in the general tolerance block.

5.1.1.4 Implied 90° Basic Angle Tolerance — where features shown at right angles are located by basic dimensions, a geometric tolerance controls the 90° relationship.

## 5.2 Direct Tolerancing Methods

Tolerances are applied directly to dimensions using:
- Limit dimensioning: max and min values given (e.g., .748/.752)
- Plus and minus tolerancing: nominal dimension with bilateral or unilateral tolerance (e.g., .750 ± .002 or .750 +.002/-.000)

## 5.3 Tolerance Expression

5.3.1 Millimeter tolerances:
(a) Where bilateral, both values have same number of decimal places (e.g., 25.0 +0.25/-0.10, not 25 +.25/-.1)
(b) Unilateral tolerance — zero shown with sign: 25.0 +0.25/-0.00
(c) Limit dimensions — both values same number of decimal places

5.3.2 Decimal inch tolerances:
(a) Limits and bilateral tolerances expressed to same number of decimal places as the tolerance
(b) Unilateral tolerance zero shown without decimal point sign: .500 +.005/-.000

## 5.4 Interpretation of Limits

All limits are absolute. Dimensional limits, regardless of number of decimal places, are used as if they were continued with zeros. Example: 12.2 means 12.20000...

## 5.5 Single Limit Toleranced Dimensions

MIN or MAX is placed after a dimension where other limits are governed by design requirements, manufacturing limitations, or standard practices. Examples: .06 R MIN (minimum radius), .500 DEEP MIN.

## 5.6 Tolerance Accumulation

5.6.1 Datum-based dimensions have less tolerance accumulation than chain dimensioning. Ordinate dimensions (all from a common datum) have the advantage of no tolerance accumulation between features.

## 5.7 Dimensions Related to an Origin

Where a dimension originates from a specific surface or feature and not from another dimension, a dimension origin symbol is placed at the origin end.

## 5.8 Limits of Size

5.8.1 Rule #1 (Envelope Principle) — where only a size tolerance is specified, the limits of size prescribe the extent within which variations of geometric form and size are allowed:
(a) The surface of a feature shall not extend beyond a boundary of perfect form at MMC.
(b) There is no requirement for perfect form at LMC.

Note: Rule #1 applies to individual regular features of size. It does not apply to stock material, parts subject to free state variation, or where perfect form is not required at MMC.

5.8.2 Applicability of Modifiers — geometric tolerances applied to features of size may use MMC (M), LMC (L), or RFS modifiers.

## 5.9 Applicability of Modifiers on Geometric Tolerance Values

RFS applies to the tolerance value and datum feature reference where no modifier symbol is shown. MMC (M) and LMC (L) must be explicitly specified.

## 5.10 Screw Threads

Where a geometric tolerance is applied to a screw thread feature, the tolerance applies to the pitch cylinder axis UOS. Where a datum feature symbol is applied to a thread, it applies to the axis of the pitch cylinder.

## 5.11 Gears and Splines

Tolerances applied to gears and splines must identify the specific feature (major diameter, pitch diameter, minor diameter).

## 5.13 Angular Surfaces

Angular surfaces are toleranced using combinations of angular and linear dimensions. The tolerance zone for an angular surface is defined by two boundaries formed at the specified angle and tolerance width.

## 5.14 Conical Tapers

A conical taper may be specified by:
(a) A basic taper and a basic diameter
(b) A size tolerance combined with a profile of a surface tolerance
See Figures 5-21 and 5-22 (PDF p.70).

## 5.15 Flat Tapers

Flat tapers are specified similar to conical tapers. See Figure 5-23 (PDF p.70).

## 5.16 Radius

5.16.1 Radius (R) — a radius with no additional qualifier is a general radius. The tolerance zone is bounded by two arcs of maximum and minimum radius. The surface may be of any fair curve within these boundaries.

5.16.2 Controlled Radius (CR) — a controlled radius creates a tolerance zone bounded by two arcs, and the part surface must be a fair smooth curve with no reversals of curvature. Straight line elements are not permitted. See Figure 5-25 (PDF p.71).

Note on reference dimensions and radii — where a fillet or radius is an incidental byproduct of tooling (e.g., end mill radius, carbide tool radius at intersection of machined surfaces) and not a designed functional feature, it may be dimensioned as a reference dimension using parentheses: (R.01) TYP CARBIDE RADIUS. This communicates the expected condition without creating a machined tolerance requirement.

## 5.18 Statistical Tolerancing

Statistical tolerancing assigns tolerances based on statistical methods. The statistical tolerance symbol (ST) is placed in the feature control frame following the tolerance value. Arithmetic limits are also required.

Key figures in this section:
- Fig 5-14 through 5-19: Virtual/resultant condition and inner/outer boundary concepts (PDF p.64-69)
- Fig 5-20: Angular surface tolerancing (PDF p.69)
- Fig 5-21 through 5-23: Taper specifications (PDF p.70)
- Fig 5-24 through 5-25: Radius and controlled radius (PDF p.71)
