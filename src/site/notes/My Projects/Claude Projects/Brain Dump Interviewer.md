---
{"dg-publish":true,"permalink":"/my-projects/claude-projects/brain-dump-interviewer/","tags":["My-Projects"],"dg-note-properties":{"tags":["My-Projects"],"aliases":["Brain Dump Skill"],"source":"personal_notes","last_updated":"2026-03-23"}}
---

#My-Projects

The Brain Dump Interviewer is a Claude skill that conducts a conversational interview with a co-op to extract and document their accumulated workplace knowledge. It asks structured follow-up questions about terms, acronyms, people, places, equipment, software, and production lines — then outputs a clean, consistently formatted .txt file. That file is then fed into the New Hire Glossary Builder to be converted into Obsidian markdown notes.

The skill uses a widget-driven interview flow, steering the conversation through categories without reciting them as a checklist. It extracts glossary items from project stories rather than documenting the engineering specifics of the projects themselves. Every entry in the output includes a "Heard in context of" field to preserve the source and conversational context for the parser downstream.

The skill was created by Ryan and has been sent out to the other co-ops to gather more data for the Gizmos and Gadgets Glossary.

## How It Works

1. Co-op starts a new chat and the skill triggers via keywords like "brain dump" or "document what I know"
2. Claude interviews the co-op conversationally using widgets to steer and typed questions to extract detail
3. At the end, Claude runs a quality check to catch any missed terms, names, or locations
4. Output is a structured .txt file with sections for Definitions, People, Buildings, Lines, Manufacturing, Process Equipment, Software, My Projects, Other, and Unknown
5. That .txt file is handed off to the New Hire Glossary Builder skill for processing into the vault

## Future Improvements

- Continue refining the interview flow based on feedback from co-ops
- Improve coverage of edge cases (e.g. entries that span multiple categories)

> [!info]- Details & Notes
>
> **See also:** [[My Projects/Claude Projects/Gizmos and Gadgets Glossary\|Gizmos and Gadgets Glossary]], [[New Hire Glossary Builder\|New Hire Glossary Builder]], [[My Projects/Claude Projects/New Hire Help Hub\|New Hire Help Hub]]
