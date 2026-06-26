---
{"dg-publish":true,"permalink":"/definitions/quality/cc-sections/justification-for-change/","tags":["Definitions"],"dg-note-properties":{"tags":["Definitions"],"source":"cc-documentation skill (Ethan)","last_updated":"2026-06-09"}}
---


#Definitions

The Justification for Change explains why the change is safe and acceptable — it is the risk assessment argument. It is written before or during the Evaluations stage. It must always begin with exactly: "This change is acceptable because" — no variation. One to three sentences is the target; longer is acceptable for complex multi-scope changes but should be the exception. Plain text, active voice.

Two useful angles when writing it: what the change does not affect, and what testing or review will confirm it works correctly. For multi-scope CCs, address each sub-change separately if their risk profiles differ.

To write it you need: what makes the change low-risk or controlled, and what testing or review will be performed.

> [!info]- Examples
>
> Strong — tight scope statement plus testing confirmation:
> This change is acceptable because the modification is limited to the setpoint accumulation logic within the ADD_INGR_WITH_PUMP unit procedure and does not alter any other recipe behavior or process parameters. Testing actions have been defined to verify correct recipe operation across all affected tank sizes prior to returning the recipes to production use.
>
> Strong — hardware removal, argues from redundancy:
> This change is acceptable because removal of the vent filters does not compromise tank performance or safety. System design ensures adequate venting through automated valve control. Updated production recipes will be tested to confirm proper operation and venting under all expected process conditions.
>
> Acceptable — brief, relies on precedent:
> This change is acceptable because the caustic wash step is already used in other CIP recipes at the facility, and the testing actions will verify the successful completion of the new CIP recipe.
>
> Weak — avoid this pattern:
> This change is acceptable because it has been reviewed and approved by the appropriate stakeholders. (Circular, no specifics.)
>
> **See also:** [[Definitions/Quality/Change Control\|Change Control]], [[Definitions/Quality/CC Sections/Reason for Change\|Reason for Change]], [[Software/EtQ Reliance\|ETQ Reliance]]
