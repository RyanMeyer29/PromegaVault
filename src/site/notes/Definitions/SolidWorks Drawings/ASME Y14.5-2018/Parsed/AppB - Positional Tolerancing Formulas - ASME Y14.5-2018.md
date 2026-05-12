---
{"dg-publish":true,"permalink":"/definitions/solid-works-drawings/asme-y14-5-2018/parsed/app-b-positional-tolerancing-formulas-asme-y14-5-2018/","tags":["Definitions","reference-document"],"dg-note-properties":{"tags":["Definitions","reference-document"],"source":"ASME Y14.5-2018","last_updated":"2026-04-30"}}
---


# AppB - Positional Tolerancing Formulas - ASME Y14.5-2018

**Standard:** ASME Y14.5-2018 Dimensioning and Tolerancing
**Appendix:** Appendix B (Nonmandatory)
**PDF pages:** 333-335

> PDF path: `Definitions/SolidWorks Drawings/ASME Y14.5-2018/ASME-Y14.5-2018-R2024-Dimensioning-and-Tolerancing.pdf`

---

## Overview

Appendix B provides formulas for calculating positional tolerances for floating and fixed fastener assemblies.

## Floating Fastener Formula

Used when both parts have clearance holes (the fastener floats):

**T = H − F**

Where:
- T = positional tolerance diameter (applied to each part)
- H = minimum diameter of clearance hole (MMC hole size)
- F = maximum diameter of fastener (MMC fastener size)

Both parts get the same tolerance T when the tolerance is split equally. If tolerances are unequal between parts: T1 + T2 = H − F

See Figure B-1 (PDF p.335).

## Fixed Fastener Formula

Used when one part has a threaded hole or press-fit insert (fastener is fixed in one part):

**T = (H − F) / 2**

Where:
- T = positional tolerance diameter for the clearance hole part
- H = minimum diameter of clearance hole
- F = maximum diameter of fastener (or virtual condition of threaded/press-fit feature)

The threaded or press-fit part typically gets zero tolerance at MMC or a separate perpendicularity tolerance with projected tolerance zone.

See Figures B-2 and B-3 (PDF p.335).

## Coaxial Features Formula

For coaxial holes controlled by position:

**T = D1 − D2**

Where:
- T = total positional tolerance available
- D1 = minimum clearance hole at MMC
- D2 = maximum fastener at MMC

Tolerance may be split between the two coaxial features.

See Figure B-3 (PDF p.335).

## Notes

These formulas assume the worst case (no statistical allowances). For statistical tolerancing, larger tolerances may be justified using RSS (root sum of squares) methods per Section 5.18.

The formulas give minimum hole sizes for a given fastener and tolerance, or maximum positional tolerances for a given hole and fastener combination.
