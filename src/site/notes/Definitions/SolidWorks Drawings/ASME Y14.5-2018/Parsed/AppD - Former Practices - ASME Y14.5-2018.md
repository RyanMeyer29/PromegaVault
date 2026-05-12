---
{"dg-publish":true,"permalink":"/definitions/solid-works-drawings/asme-y14-5-2018/parsed/app-d-former-practices-asme-y14-5-2018/","tags":["Definitions","reference-document"],"dg-note-properties":{"tags":["Definitions","reference-document"],"source":"ASME Y14.5-2018","last_updated":"2026-04-30"}}
---


# AppD - Former Practices - ASME Y14.5-2018

**Standard:** ASME Y14.5-2018 Dimensioning and Tolerancing
**Appendix:** Appendix D (Nonmandatory)
**PDF pages:** 344-347

> PDF path: `Definitions/SolidWorks Drawings/ASME Y14.5-2018/ASME-Y14.5-2018-R2024-Dimensioning-and-Tolerancing.pdf`

---

## Overview

Appendix D documents former practices that were used in previous versions of Y14.5 but are no longer part of the current standard. Useful for interpreting older drawings that reference ASME Y14.5-2009 or earlier.

## Key Former Practices

### Concentricity Symbol

The concentricity symbol (two concentric circles) was removed in Y14.5-2018. It controlled the median points of all diametrically opposed elements of a feature of revolution to a datum axis.

**Current replacement:** Use position (⊕) with ⌀ tolerance zone and RFS to control coaxiality of surfaces of revolution. For median point control specifically, profile of a surface is the preferred control.

### Symmetry Symbol

The symmetry symbol (three parallel horizontal lines) was removed in Y14.5-2018. It controlled the median points of opposed feature elements to a datum center plane.

**Current replacement:** Use position (⊕) to control the center plane of a width feature. For median point control, profile of a surface is preferred.

### Why They Were Removed

Both concentricity and symmetry were eliminated because:
1. Their requirements (controlling median points) are difficult to measure and verify
2. Position and profile tolerances achieve the same functional result more clearly
3. The symbols were frequently misapplied or misunderstood

### Reading Old Drawings

When encountering concentricity or symmetry symbols on legacy drawings (pre-2018):
- The drawing was created to Y14.5-2009 or earlier
- Concentricity: the median points of diametrically opposed surface elements must fall within a cylindrical tolerance zone coaxial with the datum axis
- Symmetry: the median points of opposed surface elements must fall within a tolerance zone centered on the datum center plane

For inspection of legacy drawings, the measurement approach should be confirmed with the drawing originator or quality engineering.
