---
{"dg-publish":true,"permalink":"/definitions/quality/cc-sections/testing-actions/","tags":["Definitions"],"dg-note-properties":{"tags":["Definitions"],"source":"cc-documentation skill (Ethan)","last_updated":"2026-06-09"}}
---


#Definitions

Testing Actions is a Word document attached to the CC that lists the verification steps confirming the change works as intended. It uses the same structure as Implementation Actions but with two additional columns: the table has six columns total — Action, Expected Result / Acceptance Criteria, Result As Expected (Yes/No), PASSED (Yes/No), Initials, Date. Sign-off columns are always left blank in the document.

Every testing step must have an Expected Result populated. The expected result should state the observable outcome, not restate the action. Use present tense. Name the specific condition that confirms success — fault state, valve position, level reading, alarm status. For recipe runs, always note fault and alarm status, and call out any specific behavior being verified by this CC.

Steps should cover all affected systems or equipment individually. If multiple tank sizes or units are affected, test each one separately. Section headers and sub-headers follow the same rules as Implementation Actions.

To write it you need: what systems or equipment need to be tested, what specific operations should be run, and what pass criteria look like for each.

> [!info]- Examples
>
> Simple recipe run test:
> Action: Run a CIP_MEDIA recipe to P1.
> Expected Result: Recipe completes successfully without holds or alarms.
>
> Recipe run with recorded output:
> Action: Run a successful 500L recipe on a 500L tank. Record Unique ID#: ____________________________
> Expected Result: Run completes with no faults or alarms. The vent valve opens correctly during the fill IBC step.
>
> Logic interlock verification:
> Action: Verify Biokill sanitization starts when the Biokill tank level reaches 20% and no CIP recipe is running.
> Expected Result: Biokill sanitization automatically starts when the tank level drops below 20% and no CIP recipe is active.
>
> Negative test confirming a restriction works:
> Action: Initiate a CIP recipe when Biokill sanitization is not running.
> Expected Result: Biokill sanitization does not start when the tank level reaches 20% while a CIP recipe is active.
>
> **See also:** [[Definitions/Quality/Change Control\|Change Control]], [[Definitions/Quality/CC Sections/Implementation Actions\|Implementation Actions]], [[Software/EtQ Reliance\|ETQ Reliance]]
