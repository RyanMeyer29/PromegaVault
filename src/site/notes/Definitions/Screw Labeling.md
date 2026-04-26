---
{"dg-publish":true,"permalink":"/definitions/screw-labeling/","tags":["Definitions"],"dg-note-properties":{"aliases":[],"tags":["Definitions"],"source":"personal_notes","last_updated":"2026-03-30"}}
---


#Definitions

Screw labeling refers to the standardized naming conventions used to describe the size, thread pitch, and length of threaded fasteners. There are two main systems used in engineering: Metric (ISO) and Unified National (imperial/inch-based). Both systems appear in equipment and fabrication work at Promega.

In the metric system, the format is M[diameter] × [pitch] × [length]. For example, M3 × 0.5 × 10 means a metric screw with a 3 mm nominal outer diameter, a thread pitch of 0.5 mm (distance between threads), and a length of 10 mm. Length is typically measured from under the head for most head types. The pitch is sometimes omitted when it is the standard coarse pitch for that diameter — so "M3" alone generally implies M3 × 0.5. Fine-pitch variants (e.g. M3 × 0.35) are always called out explicitly. Common metric sizes encountered in equipment include M3, M4, M5, M6, and M8.

In the Unified National (imperial) system, the format is [diameter]-[TPI] × [length]. For number sizes (#0–#12), the diameter is given as a screw number defined by ASME (specifically ASME B18.6.3 for machine screws). The nominal diameter in inches is calculated as: diameter = (N × 0.013) + 0.060, where N is the screw number. So a #4 screw has a nominal diameter of (4 × 0.013) + 0.060 = 0.112 inches (~2.8 mm). For example, 6-32 × 1/2 means a #6 diameter screw (~3.5 mm), 32 threads per inch, and 1/2 inch long. Above #12, fractional inch diameters are used — for example, 1/4-20 × 3/4 means 1/4 inch diameter, 20 TPI, and 3/4 inch long. Common imperial sizes encountered include 4-40, 6-32, 8-32, 10-32, and 1/4-20. Coarse thread (e.g. 6-32) is standard; fine thread (e.g. 6-40) appears occasionally on precision equipment.

Head type and drive type are not encoded in the size label but are typically specified alongside it when ordering or calling out a fastener. Common head types include Socket Head Cap Screw (SHCS), button head, flat head (countersunk), and pan head. Common drive types include hex/Allen, Phillips, Torx, and slotted.

> [!info]- Details & Notes
>
> **Unknowns:** Length measurement convention can vary by head type — flat/countersunk heads measure total length; most others measure from under the head. Worth confirming when precision matters.
>
> **See also:** [[Fabrication\|Fabrication]]

