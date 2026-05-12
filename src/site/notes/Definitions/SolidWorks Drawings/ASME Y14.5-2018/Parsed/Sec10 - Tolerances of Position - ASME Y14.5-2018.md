---
{"dg-publish":true,"permalink":"/definitions/solid-works-drawings/asme-y14-5-2018/parsed/sec10-tolerances-of-position-asme-y14-5-2018/","tags":["Definitions","reference-document"],"dg-note-properties":{"tags":["Definitions","reference-document"],"source":"ASME Y14.5-2018","last_updated":"2026-04-30"}}
---


# Sec10 - Tolerances of Position - ASME Y14.5-2018

**Standard:** ASME Y14.5-2018 Dimensioning and Tolerancing
**Section:** Section 10
**PDF pages:** 197-257

> Note: Section 10 is the largest section and is heavily figure-driven. Open PDF at pages 197-257 for figures.
> PDF path: `Definitions/SolidWorks Drawings/ASME Y14.5-2018/ASME-Y14.5-2018-R2024-Dimensioning-and-Tolerancing.pdf`

---

## 10.1 General

Position tolerances control the location of features of size (holes, pins, slots, bosses) relative to datums or to each other. True position is the theoretically exact location defined by basic dimensions. The position tolerance defines a zone within which the center, axis, or center plane of the feature must lie.

## 10.2 Positional Tolerancing

The position symbol ⊕ is used in a feature control frame. Basic dimensions locate the true position. The tolerance value defines the diameter (with ⌀) or width of the tolerance zone.

Key applications of material condition modifiers with position:
- RFS (default): tolerance applies regardless of actual feature size
- MMC (M): bonus tolerance available as feature departs from MMC — allows more tolerance when the hole is larger than MMC
- LMC (L): bonus tolerance available as feature departs from LMC — used to protect minimum wall thickness

## 10.3 Positional Tolerancing Fundamentals — I

### 10.3.1 True Position Defined by Basic Dimensions

Basic dimensions establish the true position. Basic dimensions are exact — tolerances on those dimensions come only from the feature control frame, not from any general title block tolerance.

### 10.3.2 Tolerance Zone Interpretation

For cylindrical features (holes, pins): the tolerance zone is a cylinder of diameter equal to the tolerance value, centered at true position. The axis of the feature must lie within this cylinder.

For non-cylindrical features (slots, tabs): the tolerance zone is two parallel planes centered at true position.

### 10.3.3 MMC Application

At MMC (smallest hole / largest pin), the full position tolerance applies. As the hole grows larger (departs from MMC), a bonus tolerance equal to the departure becomes available. Total allowable tolerance = specified tolerance + (actual size − MMC size).

### 10.3.4 LMC Application

At LMC (largest hole), the full tolerance applies. As the hole grows smaller (departs from LMC), bonus tolerance is added. Used to protect minimum wall thickness.

### 10.3.5 Zero Tolerance at MMC

A zero position tolerance at MMC means: at MMC, the feature must be at exactly true position. All tolerance is "bonus" derived from departure from MMC.

## 10.4 Positional Tolerancing Fundamentals — II

### 10.4.1 Projected Tolerance Zone

For threaded holes or press-fit inserts, the perpendicularity of the fastener passing through a mating part is controlled by specifying a projected tolerance zone. The zone is projected above the threaded surface by a minimum height (the thickness of the mating part). Symbol: P (circled) followed by the projection height.

### 10.4.2 Boundary Concept

An alternative to axis interpretation: the surface of the feature must not violate a virtual condition boundary at true position. Used where surface interpretation is preferred over axis interpretation.

## 10.5 Pattern Location

A pattern of features located by position tolerances may be treated as a group relative to datums (composite tolerancing) or individually.

### 10.5.1 Composite Positional Tolerancing

Two-tier feature control frame:
- Upper tier (PLTZF): controls pattern location relative to datums. Larger tolerance.
- Lower tier (FRTZF): controls feature-to-feature relationship within the pattern. Smaller tolerance.

The FRTZF is constrained in rotation to the datums but not in translation. This allows the whole pattern to shift while maintaining the tight feature-to-feature relationship.

### 10.5.2 Multiple Single-Segment Feature Control Frames

Two separate feature control frames, each with their own datum references. Both must be satisfied simultaneously. More restrictive than composite tolerancing because the lower segment is fully constrained to its datums.

## 10.6 Coaxial Feature Controls

Position tolerance (⊕ with ⌀) may be used to control the coaxiality of two or more cylindrical features. The axis of each controlled feature must fall within the positional tolerance zone relative to the datum axis.

## 10.7 Tolerancing for Symmetrical Relationships

Position tolerance may be used to control symmetrical relationships — the center plane of a feature must lie within two parallel planes centered at the true position plane.

Key figures:
- Fig 10-1 through 10-9: Basic position concepts, axis and surface interpretation (PDF p.207-212)
- Fig 10-10 through 10-16: MMC and LMC bonus tolerance (PDF p.213-217)
- Fig 10-21 through 10-24: Projected tolerance zones (PDF p.220-221)
- Fig 10-38 through 10-45: Composite position tolerancing (PDF p.232-243)
- Fig 10-50 through 10-60: Coaxial and symmetrical features (PDF p.249-257)
