---
{"dg-publish":true,"permalink":"/my-projects/ar-c-notes/batch-run-testing/","tags":["My-Projects"],"dg-note-properties":{"tags":["My-Projects"],"source":"personal_notes","last_updated":"2025-01-01"}}
---


#My-Projects

Batch run testing is the process of verifying that the [[Software/Batch\|Batch]] recipe system is configured correctly for each OP and UP before real fermentation runs are executed. The goal is to walk through every step in the recipe, confirm that the correct prompts appear, the correct parameters appear, and that the overall flow is working as expected. Issues found are logged in [[Software/Smartsheet\|Smartsheet]], which acts as a shared bug list accessible to a small team at [[Definitions/Cybertrol\|Cybertrol]], the external contractor helping set up Batch on the [[My Projects/ArC Notes/Fermenters\|fermenters]].

## Workflow

To start a test run, you open the batch editor, go to Batch View, then go to Batches and click Create New. This presents a list of options — these appear to be pre-built OPs or UP templates — from which you select the one you want to test (e.g. 3000L OP Biomass). A parameter list then appears, which you fill out. During batch testing, no physical process is running, so parameters are filled with unique but arbitrary values (e.g. sequential numbers 1, 2, 3, 4...) just to satisfy the input fields.

Once started, you navigate to the P3 Control tab, then the P3 Fermentor Detail tab, and open the P3 Phases window. As the batch runs, prompts appear sequentially — including prompts to acknowledge hand valve positions. Since no physical equipment is running during testing, hand valves are set to a safe position beforehand and the prompts are acknowledged without actually checking them.

You work through all the OPs and UPs for the vessel being tested, checking each individual step. Successful run paths are tracked by printing out the process trees and highlighting the completed paths.

## Notes on P3 Testing

The first batch run testing done was on the 3000L P3 fermenter, starting with the 3000L OP Biomass. Multiple UPs and OPs for P3 were completed in the first session.

> [!info]- Details & Notes
>
> **Encountered in:** Active project as of early 2025
>
> **See also:** [[Software/Batch\|Batch]], [[My Projects/ArC Notes/Fermenters\|Fermenters]], [[Definitions/Cybertrol\|Cybertrol]], [[Software/Smartsheet\|Smartsheet]], [[Definitions/HMI\|HMI]]
