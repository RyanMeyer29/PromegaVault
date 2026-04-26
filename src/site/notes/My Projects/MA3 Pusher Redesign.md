---
{"dg-publish":true,"permalink":"/my-projects/ma-3-pusher-redesign/","tags":["My-Projects"],"dg-note-properties":{"aliases":["New pusher design","MA3 Push"],"tags":["My-Projects"]}}
---


---

#My-Projects

## Action Items
- [ ] Check with [[People/Matt Wahl\|Matt]] about what improvements he has in mind for the pusher (flagged in 1:1, 2026-04-10)
- [ ] Verify whether the slots on the front plate are still needed (flagged in 1:1, 2026-04-10)
- [ ] Investigate fine adjustment mechanism for pusher plate position
- [ ] Shift front plate left by ~1-2 mm in model to correct alignment offset
- [ ] Verify pin hole diameter in model (may be undersized — required filing during fit test)
- [ ] Fix countersink dimensions in model (screw sitting slightly proud)
- [ ] Confirm whether plate offset is a model error or 3D print warping from transport
- [ ] Print updated prototype on [[Fabrication/Markforged Industrial X7\|Markforged Industrial X7]] once model is corrected
- [x] Print pusher (3D print test candidate — flagged in 1:1, 2026-04-03)

## Steps

### Step 1: Fix Offset Issue
Resolve the sideways translation (offset) issue with the pusher. See Prototype Fit Test below for findings.

### Step 2: Design Options for the End
Develop design options for the pusher end. [[Fabrication/3D Printers\|3D print]] and test candidates.

### Step 3: [[Unknown/Drop Gate\|Drop Gate]] Improvements
Evaluate how lead-ins on the [[Unknown/Drop Gate\|Drop Gate]] can be modified to improve function. Begin with a [[Fabrication/3D Printers\|3D print]]. Ryan leads [[Definitions/Change Control\|Change Control]] for this step.

**Step 3a:** Assess whether the connection point can be modified to allow for future adjustments, avoiding the need to redesign from scratch later.

---

## Prototype Fit Test — 2026-04-10 (ECR)

A prototype was printed in [[Fabrication/Markforged Industrial X7\|Markforged Onyx]] on the industrial X7 at [[Buildings/Lamarr\|Lamarr]]. The original design was modeled in [[Software/Solidworks\|Solidworks]] from measurements of the existing part. The redesign removes the bend/curve from the original fork while maintaining the front plate slot geometry. No changes were made to the mounting interface.

The screws used for the test were 4-40 stainless steel flat head hex screws (McMaster-Carr 91781A106). The originals are believed to have been sourced by [[Definitions/Optima\|Optima]], the vendor who built [[Lines/MA3/MA3\|MA3]], but the exact spec is unconfirmed. The McMaster screws were the closest available equivalent.

Note: some or all of the dimensional errors below may be attributable to polymer expansion/contraction during 3D printing rather than model inaccuracies.

### Issues Found

- **Pin hole too small** — the pin hole did not accept the mounting pin. The hole was filed open by hand to give enough clearance to seat the part. Could be a model error or a print shrinkage issue.
- **Countersink too shallow** — the flat head screws sit slightly proud of the surface rather than flush. Not a functional issue for the prototype but needs to be corrected in the model.
- **Front plate misaligned** — the plate slots are shifted approximately 1-2 mm to the right relative to the cartridge tabs. Pushing the plate face manually to the left brought the slots into alignment, confirming the offset is lateral and consistent. The plastic flexibility allowed this as a temporary check — slot spacing and slot width were confirmed good when manually corrected. The offset is likely a model measurement error, but warping from transport (prototype was carried in a backpack) is also possible.
- **Reduced rigidity** — the Onyx prototype is noticeably less rigid than the stainless steel original. This is expected given the material difference and is not a concern for the final machined part, but it affected how the prototype behaved during the fit test.

### Raw Notes from ECR

> "The pin hole is too small. Could be issue with plastic, but the slots are slightly to the right. Pushing the end face to the left aligns them correctly. Estimated shift: 1-2 mm."

---

## Long-Term Plan

- Evaluate model options, including 3D printed versions
- Conduct [[Definitions/Engineering Study\|Engineering Study]] (Ryan leads) — a structured internal process with informal steps **(active as of 2026-03-20)**
- Narrow down design options
- Machine final part
- Complete [[Definitions/Change Control\|Change Control]] to add final part:
  - [[Software/EPDM\|EPDM]] updates
  - [[Definitions/CoC\|CoC]]
  - Final parts process


   ![Ali's Pusher Dimensions.jpg](/img/user/Other/Images/Ali's%20Pusher%20Dimensions.jpg)



![MA3 Pusher kickoff drawing.png](/img/user/Other/MA3%20Pusher%20kickoff%20drawing.png)
