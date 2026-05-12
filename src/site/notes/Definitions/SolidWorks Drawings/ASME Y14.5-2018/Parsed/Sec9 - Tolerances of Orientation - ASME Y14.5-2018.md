---
{"dg-publish":true,"permalink":"/definitions/solid-works-drawings/asme-y14-5-2018/parsed/sec9-tolerances-of-orientation-asme-y14-5-2018/","tags":["Definitions","reference-document"],"dg-note-properties":{"tags":["Definitions","reference-document"],"source":"ASME Y14.5-2018","last_updated":"2026-04-30"}}
---


# Sec9 - Tolerances of Orientation - ASME Y14.5-2018

**Standard:** ASME Y14.5-2018 Dimensioning and Tolerancing
**Section:** Section 9
**PDF pages:** 181-196

> Note: Orientation tolerance applications are highly visual. Open PDF at pages 181-196.
> PDF path: `Definitions/SolidWorks Drawings/ASME Y14.5-2018/ASME-Y14.5-2018-R2024-Dimensioning-and-Tolerancing.pdf`

---

## 9.1 General

Orientation tolerances control the angular relationship of features to one or more datum features. The three orientation tolerances are angularity, parallelism, and perpendicularity. All orientation tolerances require datum references.

Orientation tolerances also control form. A perpendicularity tolerance applied to a planar surface also controls flatness of that surface within the perpendicularity tolerance value.

## 9.2 Orientation Control

### 9.2.1 Angularity

Angularity controls a surface, axis, or center plane at a specified basic angle (other than 0° or 90°) relative to a datum. The tolerance zone is two parallel planes (or a cylinder with ⌀) at the specified basic angle relative to the datum.

The basic angle must be specified. The tolerance zone is oriented at the basic angle — it does not have its own angular tolerance.

### 9.2.2 Parallelism

Parallelism controls a surface, axis, or center plane at basic 0° (parallel) to a datum. Tolerance zone: two parallel planes (or cylindrical zone with ⌀) parallel to the datum.

Applied to a planar surface — all surface elements must lie between two parallel planes parallel to the datum plane.

Applied to a feature axis (RFS) — the axis must lie within a cylindrical tolerance zone (⌀ precedes tolerance) or between two parallel planes, both parallel to the datum axis.

### 9.2.3 Perpendicularity

Perpendicularity controls a surface, axis, or center plane at basic 90° to a datum. Tolerance zone: two parallel planes (or cylindrical zone with ⌀) perpendicular to the datum.

Applied to a planar surface — the surface must lie between two parallel planes perpendicular to the datum.

Applied to an axis (pin or boss, RFS) — the axis must lie within a cylindrical tolerance zone perpendicular to the datum plane.

Applied to an axis (MMC) — a bonus tolerance is available as the feature departs from MMC. The axis must lie within the cylindrical zone, but the zone diameter increases as the actual feature size departs from MMC. See Figures 9-13 and 9-14 (PDF p.173-174).

Projected tolerance zone — used for threaded holes or press-fit inserts where the perpendicularity of the installed mating part matters, not just the hole. The tolerance zone is projected above the surface by a specified height. See Figure 9-11 (PDF p.172).

## 9.3 Specifying Orientation Tolerances

Orientation tolerances are placed in a feature control frame with the geometric characteristic symbol, tolerance value (and material condition modifier if applicable), and datum reference(s).

The basic angle must be shown on the drawing for angularity. For parallelism and perpendicularity, the 0° or 90° relationship is implied.

## 9.4 Tangent Plane

Where the tangent plane modifier T (circled) is added to an orientation tolerance, the tolerance applies to a plane tangent to the surface (contacting the high points) rather than to all elements of the surface. This allows form variations while controlling orientation of the tangent plane.

## 9.5 Alternative Practice

A combination of angular and linear tolerances may be used to control angular surfaces as an alternative to orientation geometric tolerances (per Appendix I). However, this practice is being phased out in favor of profile tolerances.

Key figures:
- Fig 9-1 through 9-4: Angularity (PDF p.183-184)
- Fig 9-2 through 9-7: Parallelism (PDF p.183-186)
- Fig 9-8 through 9-15: Perpendicularity (PDF p.187-192)
- Fig 9-11: Projected tolerance zone for threaded hole (PDF p.190)
- Fig 9-17 through 9-18: Tangent plane (PDF p.195-196)
