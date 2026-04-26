---
{"dg-publish":true,"permalink":"/lines/ma-3/ma-3/","tags":["Lines"],"dg-note-properties":{"aliases":["MaxAuto3"],"tags":["Lines"],"source":"personal_notes","last_updated":"2026-04-10"}}
---


MA3 (MaxAuto3) is one of the MaxAuto fill/finish lines in the Feynman building. Like the other MaxAuto lines, it fills, seals, and labels cartridges used in Promega's Maxwell® RSC instrument kits.

#Lines

**Known Equipment:**

- Filling station
- Side print unit
- Camera (upstream)
- Rake
- [[Lines/MA3/MA3 Pusher\|Pusher]]

**Active Projects:**

- [[Definitions/Engineering Study\|Engineering Study]] — [[My Projects/MA3 Pusher Redesign\|New pusher design]]  _(I will be involved in this project)_
- MA2 software improvements being ported to MA3 by Bethany Zepnick (scheduled Friday 2026-03-27). Includes fixing mislabeled HMI buttons, a vacuum pump that never shuts off, and a crash issue when rejecting all objects.

**Notes:**

- Cartridges on MA3 do not travel on a conveyor belt. Instead, they sit in slots on a rake — a comb-like mechanism that runs in sections along the cartridge path. The rake operates on a CAM cycle: it lifts the cartridges up, moves them forward one step, sets them down, then returns to its original position. This repeats continuously, advancing pairs of two cartridges through each station on the line (filling, foil, labeling, sealing, etc.). At the end of the line, the [[Lines/MA3/MA3 Pusher\|pusher]] takes over and advances the cartridges to the [[Unknown/Drop Gate\|Drop Gate]] and tray stacker.
- MA3 has had more communication issues than MA2, potentially related to firmware version differences. A firmware upgrade (65400 series) was discussed in the P5 meeting (2026-03-25) but specifics are unresolved.
- Applied torque target is 26 in-lb; removal torque measured at ~21 in-lb (~81% of applied). This is within expected range. The torque range spec (24.5–27 in-lb) may need to be revisited since the set point does not match actual applied torque despite positive feedback from the machine.

> [!info]- Details & Notes
>
> **See also:** [[Lines/MaxAuto\|MaxAuto]], [[Lines/MA1\|MA1]], [[Lines/MA2\|MA2]], [[Definitions/Maxwell RSC\|Maxwell RSC]], [[My Projects/MA3 Pusher Redesign\|MA3 Pusher Redesign]], [[Definitions/HMI\|HMI]]