---
{"dg-publish":true,"permalink":"/definitions/quality/cc-sections/reason-for-change/","tags":["Definitions"],"dg-note-properties":{"tags":["Definitions"],"source":"cc-documentation skill (Ethan)","last_updated":"2026-06-09"}}
---


#Definitions

The Reason for Change explains why this change must happen. It is written during Initiation & Planning. It must always begin with exactly: "This change is necessary because" — no variation. One to three sentences maximum; a small paragraph. Plain text, active voice. The focus should be on the operational, safety, or quality driver, not just intent. One crisp sentence is often enough for simple changes.

To write it you need: the core problem, risk, or operational need driving the change.

> [!info]- Examples
>
> Strong — names the specific failure and its consequence:
> This change is necessary because the current ADD_INGR_WITH_PUMP logic incorrectly accumulates pump addition setpoints against the maximum batch size, causing false faults during multi-pump additions. These faults interrupt production runs and require operator intervention to resolve.
>
> Strong — clear operational driver, concise:
> This change is necessary because the vent filters are no longer functionally necessary but require frequent maintenance and replacement. Venting during active unit procedures is already managed through the tank vent valves, making the filters redundant.
>
> Weak — avoid this pattern:
> This change is necessary because the current system needs to be updated to improve performance. (Vague, no consequence stated.)
>
> **See also:** [[Definitions/Quality/Change Control\|Change Control]], [[Definitions/Quality/CC Sections/Justification for Change\|Justification for Change]], [[Software/EtQ Reliance\|ETQ Reliance]]
