---
{"dg-publish":true,"permalink":"/definitions/solid-works-drawings/asme-y14-5-2018/parsed/sec12-tolerances-of-runout-asme-y14-5-2018/","tags":["Definitions","reference-document"],"dg-note-properties":{"tags":["Definitions","reference-document"],"source":"ASME Y14.5-2018","last_updated":"2026-04-30"}}
---


# Sec12 - Tolerances of Runout - ASME Y14.5-2018

**Standard:** ASME Y14.5-2018 Dimensioning and Tolerancing
**Section:** Section 12
**PDF pages:** 305-323

> PDF path: `Definitions/SolidWorks Drawings/ASME Y14.5-2018/ASME-Y14.5-2018-R2024-Dimensioning-and-Tolerancing.pdf`

---

## 12.1 General

Runout tolerances control the relationship of a surface to a datum axis. They are used on parts with surfaces of revolution (cylinders, cones, surfaces perpendicular to an axis). Runout always requires a datum axis.

## 12.2 Runout

Runout is measured by rotating the part about the datum axis and measuring variation with an indicator. Two types: circular runout and total runout.

## 12.3 Runout Tolerance

The runout tolerance value is the total indicator reading (TIR) — the full range of indicator movement. Not a radius value.

## 12.4 Types of Runout Tolerances

### 12.4.1 Circular Runout

Circular runout controls each individual circular cross-section independently. The indicator is placed at one axial position and the part is rotated. The variation at that cross-section must not exceed the tolerance value.

Applied to a cylindrical surface: controls a combination of circularity and coaxiality at each cross-section.
Applied to a face (surface perpendicular to axis): controls wobble at each circular line element.

Circular runout symbol: single arrow (↗).

### 12.4.2 Total Runout

Total runout controls the entire surface simultaneously. The indicator is moved along the full length of the surface while the part rotates. All surface elements must fall within the total runout tolerance zone.

Applied to a cylindrical surface: controls cylindricity and coaxiality combined.
Applied to a face: controls flatness and perpendicularity to the datum axis combined.

Total runout symbol: double arrow (⇗).

Total runout is more restrictive than circular runout.

## 12.5 Runout Tolerance and Size

Runout tolerance and size tolerance are independent unless controlled form at MMC applies. Runout tolerance does not limit the size of a feature, and size tolerance does not limit runout.

## 12.6 Application

### 12.6.1 Single Cylindrical Datum Feature

The datum axis is established from a single cylindrical feature. The controlled feature's axis must be coaxial within the runout tolerance.

### 12.6.2 Common Datum Axis (Two Features)

Two coaxial features may be identified as common datum features to establish a single datum axis. Identified as A-B (with a dash) in the feature control frame.

### 12.6.3 Datum Surface and Diameter

A datum axis may be established by a combination of a cylindrical surface (for axis) and a planar surface (for axial location). Both are referenced in the feature control frame.

## 12.7 Specification

Runout tolerances are applied by placing the feature control frame:
- Adjacent to the surface in a view showing the feature as a line
- Connected with a leader to the surface
- Below or adjacent to the size dimension

Key figures:
- Fig 12-1: Features applicable to runout tolerancing (PDF p.308)
- Fig 12-2 through 12-5: Circular and total runout on cylinders and faces (PDF p.309-313)
- Fig 12-6 through 12-7: Size and runout tolerance interaction (PDF p.313-314)
- Fig 12-9 through 12-14: Multi-datum and combined datum applications (PDF p.316-322)
