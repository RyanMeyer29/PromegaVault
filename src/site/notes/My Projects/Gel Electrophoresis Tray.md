---
{"dg-publish":true,"permalink":"/my-projects/gel-electrophoresis-tray/","tags":["My-Projects"],"dg-note-properties":{"tags":["My-Projects"],"source":"personal_notes","last_updated":"2026-04-10"}}
---


#My-Projects

## Status & Remaining Work

**Priority (as of 2026-04-10): #4 of active projects**

Most of the tray components have been cut. The joint design has been updated to use a rabbet joint for cleaner, stronger epoxy bonds. [[Software/Solidworks\|Solidworks]] models need to be updated to reflect this before machining continues.

Remaining work:

- [ ] Update [[Software/Solidworks\|Solidworks]] models to incorporate rabbet joint on all mating surfaces
- [ ] Update 2D drawings to reflect rabbet joint geometry
- [ ] Machine updated parts and do test fit
- [ ] Cut combs and comb handles
- [ ] Epoxy tray together and check fit and stability
- [ ] Redesign and resize sealed wall — the O-ring cord didn't fit well in the current version
- [x] Get SAP part numbers assigned
- [ ] Fill out parts process forms (CoC and ePDM)
- [ ] Meet with [[People/Zack Wermeling\|Zack]] to review this project alongside the [[My Projects/96 Well Bracket\|96 Well Bracket]] project
- [ ] Make any changes from Zack's feedback, produce final parts, complete parts process
- [ ] Update [[People/Nikki Masterson\|Nikki]] on the amount made (for inventory)

---

[[People/Zack Wermeling\|Zack Wermeling]] asked me to fabricate a new gel electrophoresis tray. The tray is made of polycarbonate (acrylic was also considered). All pieces are cut at [[Buildings/Lamarr\|Lamarr]] and epoxied together into their final assemblies.

## Tray Components

The tray itself is made of 3 unique parts that get epoxied together:

**Base** — a flat rectangle with two groove slots that accept the sealed walls.

**Side Walls** — the long walls of the tray, with slots and grooves for both the combs and the sealed walls.

**Top Lip** — follows the perpendicular shape of the side walls and acts as a lip that slots into the holder machine.

## Sealed Walls

The sealed walls are based on a previous tray Zack gave me as reference. They use an O-ring cord lining the edges to create a watertight seal, and function as the two end walls of the gel tray. Currently Zack's team just tapes off the ends — the sealed walls are the improved solution. The base and side walls have grooves machined in to accept them.

## Combs

There are two comb variants: a 16-tooth comb and a 1-tooth comb (the 1-tooth is just a single large central tooth). Each comb is two parts epoxied together:

**Tooth plate** — the thin flat piece with the actual teeth.

**Handle/body** — a thicker piece that slots into the tray and acts as a handle.

They are two separate pieces for manufacturing purposes but become one assembly after epoxying.

## Fabrication Notes

Material is polycarbonate, sized to standard PC thicknesses already stocked at Lamarr to avoid needing to face anything down. This was a design adjustment made early on — originally parts were sized for smoothness/clarity thinking DNA contact mattered, but Zack confirmed only the gel contacts the tray so that wasn't necessary.

Most cuts are done on the [[Fabrication/Zund\|Zund]]. The Zund struggles with very thin plastic, so the combs will be cut differently — the plan is to face a sheet of PC on the Zund first, then use the [[Fabrication/Laser Cutter\|Laser Cutter]] for the fine comb cuts.

## Part Numbers

| SAP Material # | Description | Order Qty | BOM Equipment # | BOM Qty |
| :------------- | :---------- | :-------- | :-------------- | :------ |
| 1016469        | Tray, Gel Electrophoresis, Polycarbonate | 2 | 113596 | 1 |
| 1016470        | Comb, Gel Tray, Polycarbonate, 16-Tooth | 2 | 113596 | 1 |
| 1016475        | Comb, Gel Tray, Polycarbonate, 1-Tooth | 2 | 113596 | 1 |
| 1016480        | Wall, Gel Tray, Polycarbonate, Sealed | 4 | 113596 | 1 |

Note: Tray (1016469) contains 3 sub-part numbers (PN-A, PN-B, PN-C) for its different subcomponents — to be assigned.

See also: [[Definitions/Electrophoresis\|Electrophoresis]], [[Fabrication/Zund\|Zund]], [[Fabrication/Laser Cutter\|Laser Cutter]], [[Buildings/Lamarr\|Lamarr]]

