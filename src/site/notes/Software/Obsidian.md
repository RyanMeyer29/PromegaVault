---
{"dg-publish":true,"permalink":"/software/obsidian/","tags":["Software"],"dg-note-properties":{"tags":["Software"]}}
---


Obsidian is a proprietary personal knowledge base and note-taking application that operates on markdown files. The software is free for personal and commercial use; only the offered cloud services, optional commercial licenses, and early access versions are paid. It is available as desktop versions for macOS, Windows and Linux as well as for mobile operating systems such as iOS and Android, but not as a web application.
## Custom Shortcuts

- `Ctrl+L` — Create new note from highlighted text and link to it
- `Ctrl+K` — Link highlighted text to existing note (auto-links if alias match found, otherwise shows dropdown)
- `F1` — Navigate back
- `F2` — Navigate forward

## Navigation

- `Ctrl+O` — Quick switcher (jump to any note)
- `Ctrl+Tab` — Cycle tabs
- `Ctrl+W` — Close tab

## Editing

- `[[` — Create wikilink (dropdown suggests existing notes)
- `Ctrl+F` — Search in note
- `Ctrl+B` — Bold
- `Ctrl+I` — Italic

## Headings

- `#` + Space — Heading 1
- `##` + Space — Heading 2
- `###` + Space — Heading 3

## Aliases

Stored in frontmatter at the top of a note. `Ctrl+K` handles this automatically.

```
---
aliases: [EMT, Short Name]
---
```

## Scripts

Custom JavaScript macros that power the Ctrl+L and Ctrl+K shortcuts above. These live in the vault root and are loaded by the Obsidian Macro plugin.

- [[create-linked-note.js]] — creates a new note from highlighted text and links to it (Ctrl+L)
- [[link-to-existing-note.js]] — links highlighted text to an existing note, auto-resolving aliases (Ctrl+K)

## Bases Files

Obsidian Bases are database-style views built on top of vault notes. They use `.base` files which cannot contain frontmatter and cannot be linked to from inside their own file, so they are referenced here instead.

- [[Active Projects.base]] — query view of active project notes
- [[People.base]] — query view of People notes
- [[Software.base]] — query view of Software notes
- [[Unpublished.base]] — query view of notes where dg-publish is false or absent
- [[Untitled.base\|Untitled.base]] — unnamed base file; contents unconfirmed
