---
{"dg-publish":true,"permalink":"/software/batch/","tags":["Software"],"dg-note-properties":{"tags":["Software"],"source":"personal_notes","last_updated":"2025-01-01"}}
---


#Software

Batch is the recipe management and sequencing system used to control the [[My Projects/ArC Notes/Fermentation\|Fermentation]] process at Promega. A "batch" in this context refers to a pre-configured recipe that sequences all the steps and phases of a fermentation run in the correct order, with standardized parameters, so operators don't have to configure them manually each time. If you're running the same product for months in a row, Batch captures everything so nothing needs to be re-entered each run. The layered control hierarchy Batch uses is based on the [[Definitions/ISA-88\|ISA-88]] standard, also commonly called S88. The system is being set up on Promega's fermenters with help from [[Definitions/Cybertrol\|Cybertrol]], an external contractor.

Batch is structured in layers, from lowest to highest:

Control Modules are the lowest level — individual physical devices like a valve, a switch, a pump, or a sensor. They represent a single controllable component on the equipment.

Equipment Modules sit above control modules and are mode-based. A given mode defines a specific combination of control module states — which valves are open or closed, which pumps are running, etc. Rather than commanding individual devices one at a time, you switch the equipment module into a mode and it handles the underlying devices accordingly.

Phases are the recipe-level building block above equipment modules. A phase transitions the equipment through a sequence of modes and applies parameters like temperature setpoints, timing, pressure targets, and [[My Projects/ArC Notes/Dissolved Oxygen\|dissolved oxygen]] control strategy. Examples include seal [[My Projects/ArC Notes/Sterilize in Place\|SIP]], exhaust SIP, vessel SIP, [[My Projects/ArC Notes/Biomass\|Biomass]], [[My Projects/ArC Notes/Induction\|Induction]], and transfer out.

Operating Procedures (OPs) sit above phases and sequence them in the correct order. The OP is the link between the physical process control system and the Batch recipe layer. OPs also define Transitions — the prompts presented to the operator between steps asking them to confirm before advancing. Every transition must be acknowledged to move the recipe forward.

Unit Procedures sit above OPs and are what recipes are actually built from. They sequence multiple OPs together into a coherent process block (e.g. "sterilize vessel" or "run biomass and manage additions").

The full recipe is assembled from Unit Procedures. Recipes can include parallel branches, meaning multiple Unit Procedures run simultaneously — for example, [[My Projects/ArC Notes/Biomass\|biomass]] growing in one vessel while addition lines from another vessel are being sterilized.

## Using the Batch Editor

To create and run a batch, you open the batch editor and go to Batch View, then Batches, then click Create New. This presents a list of pre-built OP or UP templates to choose from. After selecting one (e.g. 3000L OP Biomass), a parameter list appears that must be filled out before starting. Once started, you navigate to the relevant fermenter control tab (e.g. P3 Control → P3 Fermentor Detail → P3 Phases) to monitor the run and respond to prompts as the recipe steps execute.

Operators interact with Batch through the [[Definitions/HMI\|HMI]]. Engineering access is via [[EWS\|EWS]] workstations. The system is used across the 30-liter, 300-liter, and 3000-liter [[My Projects/ArC Notes/Fermenters\|Fermenters]], with each size having some configuration differences.

> [!info]- Details & Notes
>
> **Unknowns:** Promega-specific names for "Control Module" and "Equipment Module" not yet confirmed — these are the standard [[Definitions/ISA-88\|ISA-88]] (S88) terms for these concepts.
>
> **Encountered in:** [[My Projects/ArC Notes/Fermentation 101\|Fermentation 101]], [[My Projects/ArC Notes/Batch Run Testing\|Batch Run Testing]]
>
> **See also:** [[My Projects/ArC Notes/Fermentation\|Fermentation]], [[My Projects/ArC Notes/Fermenters\|Fermenters]], [[Definitions/HMI\|HMI]], [[EWS\|EWS]], [[My Projects/ArC Notes/Sterilize in Place\|Sterilize in Place]], [[My Projects/ArC Notes/Biomass\|Biomass]], [[My Projects/ArC Notes/Induction\|Induction]], [[Definitions/ISA-88\|ISA-88]], [[Definitions/Cybertrol\|Cybertrol]], [[My Projects/ArC Notes/Batch Run Testing\|Batch Run Testing]]
