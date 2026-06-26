---
{"dg-publish":true,"permalink":"/definitions/quality/change-types/","tags":["Definitions"],"dg-note-properties":{"tags":["Definitions"],"source":"QSOP24.009 Rev9","last_updated":"2026-06-22"}}
---


#Definitions

Eight [[Definitions/Quality/Change Control\|CC]] types are defined in QSOP24.009. Selecting the correct type at initiation determines which phases and evaluations ETQ will prompt for. Each type has a corresponding QRS guidance sheet in ETQ (QRS24.009.R01 through R09).

Supplier Change — any change that may affect the quality of material or service from an approved supplier, including supplier-initiated communications about changes to their company name, materials, methods, or facilities.

ERP Data Change — a change to a controlled field in the SAP ERP system.

Expiration Date Change — a change to the controlled expiration date field in ERP for a specific material batch. Only applicable when the customer-facing label does not include an expiration date.

Product and Process Change — changes with substantial or potentially substantial impact on [[Definitions/Quality/Form Fit Function\|Form, Fit or Function]] of a product or process. Also applies to substantial coordination across multiple areas. The most evaluation-intensive type and the one most likely to require external regulatory notification.

Equipment Change — changes to qualified equipment, equipment undergoing qualification, or systems that control or monitor environmental conditions used to manufacture or store product. Also covers facilities and utility systems that directly support production equipment or processes. This is the most common type for Operations Engineering work.

Quality System Change — changes to the Quality Management System or a quality process within the quality system. May require notification to external parties such as certifying bodies or regulatory bodies for substantial changes.

cGMP Software Change — changes to software used internally to support Promega operations or to maintain cGMP compliance.

cGMP Product Software Change — changes to regulated product software sold to Promega customers.

## Phase Requirements by Change Type

X = required phase, P = possible depending on evaluation outcome

| Phase | Supplier | ERP Data | Exp. Date | Product/Process | Equipment | Quality System | cGMP SW | cGMP Product SW |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Initiation & Planning | X | X | X | X | X | X | X | X |
| Evaluation | X | | | X | X | X | X | X |
| Finalize Change Plan | | | | X | X | X | X | X |
| Approval to Implement | X | X | X | X | X | X | X | X |
| Implement Changes | X | X | X | X | X | X | X | |
| Post Impl. Review (API only) | | | | X | X | X | X | X |
| Final Review | X | | | X | X | X | X | X |
| Closed — Implemented | P | X | X | P | P | P | P | P |
| Closed — Not Implemented | P | | | P | P | P | P | P |

Note: Initial Approval is also a possible phase for certain types — ETQ will prompt for it based on the change type and scope selected. Post Implementation Review only applies when the change impacts API manufacturing at Chappelle Manufacturing Center.

> [!info]- Details & Notes
>
> **Official document:** QSOP24.009 Rev 9, effective Jul 20, 2026 — see <iframe src="/img/user/Definitions/Quality/_attachments/QSOP24.009.pdf" width="100%" height="900px" title="QSOP24.009.pdf" style="border:1px solid #ccc;"></iframe>
>
> **Evaluation requirements:** Appendix 2 of QSOP24.009 lists the full matrix of required evaluations per change type (e.g. Training, Validation, Equipment, Documents/Records). ETQ will prompt the relevant evaluations automatically.
>
> **See also:** [[Definitions/Quality/Change Control\|Change Control]], [[Definitions/Quality/Form Fit Function\|Form Fit Function]], [[Definitions/Quality/Program-Level Change Control\|Program-Level Change Control]], [[Software/EtQ Reliance\|ETQ Reliance]]
