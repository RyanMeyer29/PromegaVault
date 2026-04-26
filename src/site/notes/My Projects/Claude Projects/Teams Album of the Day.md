---
{"dg-publish":true,"permalink":"/my-projects/claude-projects/teams-album-of-the-day/","tags":["My-Projects"],"dg-note-properties":{"tags":["My-Projects"],"source":"personal_notes","last_updated":"2026-03-23"}}
---

#My-Projects

The Teams Album of the Day is an active automation that posts a daily album recommendation card to a Microsoft Teams channel. It is built entirely with Power Automate and Microsoft Forms — there is no Claude component. Each day it posts a card with a randomized greeting and an album submitted via the form. A startup guide exists as a .docx file (link TBD).

## Technical Info

### Workflow
Each daily post includes a randomized greeting assembled from a table of greeting words, adjectives, and audience nouns — e.g. "Good morning, tired engineers."

### Form
Submissions come in via Microsoft Forms: [Album of the Day Submissions](https://forms.microsoft.com/r/yVDDNu3fp5)

### Data
Excel file path: `C:\Users\rmeyer\OneDrive - Promega Corporation\Album Project\PRO\Album of the Day Submissions.xlsx`

### Spotify API
- Client ID: a1945bd7dba54394834857e4fcecd8e8
- Client Secret: c0e5c9a08c624cc286cf2ed5b5b279fe

### Webhook (Testing)
`https://default6567301b7e83403aa15f56d9dc59f1.9c.environment.api.powerplatform.com:443/powerautomate/automations/direct/workflows/254ff2bebc18440a8fb175cdafb8dfa6/triggers/manual/paths/invoke?api-version=1&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=mlvArGW93G2TpDNzGeIJjq6B5zz0hlUvvCyG75bUVmQ`

## Future Improvements

- Add Spotify link to each card
- Auto-fill card from submitted link
- Add form link directly to the daily card
- Improve card formatting
- Add like/dislike functionality
