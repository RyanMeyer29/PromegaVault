---
{"dg-publish":true,"permalink":"/definitions/solid-works-drawings/asme-y14-5-2018/parsed/sec7-datum-reference-frames-asme-y14-5-2018/","tags":["Definitions","reference-document"],"dg-note-properties":{"tags":["Definitions","reference-document"],"source":"ASME Y14.5-2018","last_updated":"2026-04-30"}}
---


# Sec7 - Datum Reference Frames - ASME Y14.5-2018

**Standard:** ASME Y14.5-2018 Dimensioning and Tolerancing
**Section:** Section 7
**PDF pages:** 88-165

> Note: Section 7 is heavily diagram-dependent — the text defines rules but figures are essential for understanding datum establishment. For visual reference open the PDF at pages 88-165.
> PDF path: `Definitions/SolidWorks Drawings/ASME Y14.5-2018/ASME-Y14.5-2018-R2024-Dimensioning-and-Tolerancing.pdf`

---

## 7.1 General

A datum reference frame consists of three mutually perpendicular planes from which measurements are made. Datums are derived from features of the part called datum features. The physical boundary used to establish a datum is the datum feature simulator (e.g., a gage surface, machine table, or mandrel).

## 7.2 Degrees of Freedom

A part in space has six degrees of freedom: three translational (x, y, z) and three rotational (u, v, w). The datum reference frame constrains these degrees of freedom. Primary datum constrains the most, secondary constrains additional, tertiary constrains the remaining.

## 7.3 Degrees of Freedom Constrained by Primary Datum Features RMB

- Planar primary datum: constrains 3 DOF (1 translation, 2 rotation)
- Cylindrical primary datum: constrains 4 DOF (2 translation, 2 rotation)
- Width primary datum: constrains 3 DOF (1 translation, 2 rotation)

## 7.7 Datum Reference Frame

The datum reference frame is established from simulated datums (not directly from the part surfaces). The simulated datums are the true geometric counterparts of the datum features — theoretically perfect planes, cylinders, etc.

## 7.8 Datum Features

Any feature may be used as a datum feature if it is sufficiently functional, accessible, and repeatable. Datum features are identified by a datum feature symbol (letter in a square box with a triangle leader).

## 7.10 Specifying Datum Features in an Order of Precedence

Datum features are referenced in order A, B, C (primary, secondary, tertiary) in the feature control frame. The order determines the constraint sequence.

## 7.11 Establishing Datums

7.11.1 Planar Datum Features — the datum plane is the simulated plane contacting the high points of the surface.

7.11.2 Cylindrical Datum Features — the datum axis is the axis of the true geometric counterpart (simulated cylinder) that contacts the feature.

7.11.3 Width Datum Features — the datum center plane is midway between the two simulated parallel planes contacting the feature surfaces.

## 7.14 Multiple Datum Reference Frames

A part may have multiple datum reference frames for different functional requirements. Each feature control frame references its own applicable datums.

## 7.19 Simultaneous Requirements

When two or more geometric tolerances reference the same datums in the same order at the same material boundary conditions, they apply as simultaneous requirements — the part must satisfy both within a single setup/orientation relative to those datums.

To invoke separate requirements (separate setups), add "SEP REQT" below the feature control frame.

## 7.20 Restrained Condition

Where a part is flexible and its free-state form differs from its assembled form, tolerances may apply in the restrained condition. This is noted by "RESTRAINED" on the drawing. See subsection 5.1.1 and Figure 8-14.

## 7.21 Datum Reference Frame Identification

Where a part has multiple datum reference frames, they may be identified by letters added after the coordinate system label or by a note.

## 7.22 Customized Datum Reference Frame

Degrees of freedom constrained by a datum feature reference may be customized using translation (►) and other modifiers. This allows partial constraint from a single datum.

## 7.24 Datum Targets

Datum targets are designated points, lines, or areas used to establish datums, particularly on irregular, non-planar, or flexible part surfaces.

7.24.1 Datum target symbol — a circle divided horizontally: upper half contains target number, lower half contains target size (for areas and lines). Connected to the target location by a leader with a filled dot (point), line, or area.

7.24.2 Datum Target Point — an X at the target location, dimensioned in two coordinates.

7.24.3 Datum Target Line — an X on the edge view of a surface, or a phantom line on the direct view.

7.24.4 Datum Target Area — a section-lined area of specified shape and size, located by coordinates.

Key figures in this section:
- Fig 7-1: Datum Reference Frame (PDF p.88)
- Fig 7-2 through 7-6: Sequence of datum features and DOF (PDF p.89-93)
- Fig 7-7 through 7-11: Establishment of datums for various feature types (PDF p.94-97)
- Fig 7-40 through 7-45: Irregular features of size as datum features (PDF p.122-128)
- Fig 7-54 through 7-64: Datum targets (PDF p.138-147)
