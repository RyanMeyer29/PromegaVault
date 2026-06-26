---
{"dg-publish":true,"permalink":"/definitions/quality/cc-sections/implementation-actions/","tags":["Definitions"],"dg-note-properties":{"tags":["Definitions"],"source":"cc-documentation skill (Ethan)","last_updated":"2026-06-09"}}
---


#Definitions

Implementation Actions is a Word document attached to the CC that lists every step required to implement the change. Each step must be completed and signed off during the Implement Changes stage. It is a table with four columns: Action, Completed (Yes/No), Initials, Date. The sign-off columns are always left blank in the document — they are filled on paper during execution.

Steps are written in plain text, active voice, imperative. They should be specific enough to include equipment tags, SAP numbers, document names, and file names where relevant. Steps are ordered sequentially; no explicit step numbers are added.

Steps are grouped under section header rows. Standard groupings are Prior to Change Actions, Change Actions, and Post Change Actions. Sub-headers can be added within a section when steps span multiple work domains, such as PLC Changes, Physical Modifications, or Documentation Updates. A CC with no natural grouping can use a single Change Actions header with all steps flat.

If a step requires recording information, include a fill-in blank in the action text. If a step requires uploading a file, reference the As Found or As Left state explicitly.

To write it you need: all phases of work, any sub-groupings within phases, and each specific step within each phase.

> [!info]- Examples
>
> Step requiring verification before work begins (Prior to Change Actions):
> Verify all contractors have completed ECR training. Attach completed and signed training.
>
> Step with a fill-in blank for recording a value:
> Check in the final CIP_MEDIA recipe in FactoryTalk Batch Recipe Manager.
> Record Recipe Name:
> ____________________________
>
> Step listing multiple files (newlines within the cell, not separate rows):
> Unrelease from production and check out the following large scale portable recipes:
> MC127_1200L
> MC134_1000L
> MD131_000721_4200L
>
> Step handing off to the Testing Actions document:
> Complete Testing Actions. Once Testing Actions are completed successfully, all edited recipes can be checked in and released.
>
> **See also:** [[Definitions/Quality/Change Control\|Change Control]], [[Definitions/Quality/CC Sections/Testing Actions\|Testing Actions]], [[Definitions/Quality/CC Sections/Impacted Documentation\|Impacted Documentation]], [[Software/EtQ Reliance\|ETQ Reliance]]
