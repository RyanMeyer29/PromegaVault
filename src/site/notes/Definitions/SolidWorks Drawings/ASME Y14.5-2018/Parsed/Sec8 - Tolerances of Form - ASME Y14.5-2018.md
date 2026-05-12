---
{"dg-publish":true,"permalink":"/definitions/solid-works-drawings/asme-y14-5-2018/parsed/sec8-tolerances-of-form-asme-y14-5-2018/","tags":["Definitions","reference-document"],"dg-note-properties":{"tags":["Definitions","reference-document"],"source":"ASME Y14.5-2018","last_updated":"2026-04-30"}}
---


# Sec8 - Tolerances of Form - ASME Y14.5-2018

**Standard:** ASME Y14.5-2018 Dimensioning and Tolerancing
**Section:** Section 8
**PDF pages:** 166-180

> Note: Figures are essential for understanding form tolerance applications. Open PDF at pages 166-180.
> PDF path: `Definitions/SolidWorks Drawings/ASME Y14.5-2018/ASME-Y14.5-2018-R2024-Dimensioning-and-Tolerancing.pdf`

---

## 8.1 General

Form tolerances control the shape of individual features independent of datums. The four form tolerances are: straightness, flatness, circularity (roundness), and cylindricity. Form tolerances never reference datums.

## 8.2 Form Control

Form tolerances are applied when the size tolerance alone does not adequately control the form. Rule #1 (para. 5.8.1) controls form at MMC automatically — form tolerances refine below what size tolerances permit.

## 8.3 Specifying Form Tolerances

Form tolerances are specified in a feature control frame with the geometric characteristic symbol and tolerance value. No datum references are included.

## 8.4 Form Tolerances

### 8.4.1 Straightness

Straightness controls a line element or derived median line/axis.

Applied to a surface — the tolerance zone is the distance between two parallel lines within which each longitudinal line element of the surface must lie. Applied to a flat surface, each line element must lie within the straightness tolerance zone.

Applied to a feature of size (axis/median plane) — the tolerance zone is a cylinder (with ⌀) or two parallel planes within which the derived median line/axis must lie. Can exceed Rule #1 when applied to the axis (allows bowing/bending of the part).

Per unit length — straightness may be applied per unit length to prevent abrupt variations: e.g., .003/25 means .003 over any 25mm length. A total straightness may also be specified.

### 8.4.2 Flatness

Flatness controls a surface so that all elements lie in one plane. The tolerance zone is the space between two parallel planes.

Applied to a surface — the entire surface must lie between two parallel planes separated by the tolerance value.

Applied to a derived median plane (feature of size) — used to control the center plane of a width feature. Applied to the size dimension with ⌀ preceding the tolerance if applied to a cylinder.

Per unit area — flatness may be specified per unit area to limit abrupt local variations.

### 8.4.3 Circularity (Roundness)

Circularity controls each circular cross-section of a cylinder, cone, or sphere. The tolerance zone is an annular area between two concentric circles. Each circular element must lie within the tolerance zone at each cross-section.

Circularity tolerance must be less than the size tolerance (with Rule #1 in effect) unless applied to the average diameter.

### 8.4.4 Cylindricity

Cylindricity controls the entire cylindrical surface simultaneously — all surface elements must lie between two coaxial cylinders. The tolerance zone is the radial distance between two coaxial cylinders.

Cylindricity combines roundness, straightness, and taper in one control. It is a comprehensive form tolerance.

## 8.5 Average Diameter

Where a feature is intended to be assembled in a flexible state (e.g., a ring that deflects when pressed into a bore), circularity may be applied to the average diameter rather than individual cross-sections.

Key figures:
- Fig 8-1 through 8-6: Straightness applications (PDF p.169-174)
- Fig 8-7 through 8-9: Flatness applications (PDF p.174-175)
- Fig 8-10 through 8-13: Circularity applications (PDF p.177-179)
- Fig 8-12: Cylindricity (PDF p.178)
- Fig 8-13: Circularity with average diameter (PDF p.179)
- Fig 8-14: Restraint for nonrigid parts (PDF p.180)
