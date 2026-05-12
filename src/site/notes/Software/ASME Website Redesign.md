---
{"dg-publish":true,"permalink":"/software/asme-website-redesign/","tags":["Software"],"dg-note-properties":{"tags":["Software"],"source":"personal_notes","last_updated":"2026-05-10"}}
---

#Software

# ASME Website Redesign

## Status
Active -- redesign complete, CMS setup next

## Action Items
- [x] Redesign site as clean HTML/CSS (no UW theme)
- [x] Remove all UW logos and branding from header and throughout site
- [ ] Set up CMS editor (Decap CMS or Sveltia CMS) at uwmadisonasme.org/admin
- [ ] Test CMS setup with GitHub login
- [ ] Make remaining visual changes after CMS is confirmed working
- [ ] Decide on new domain name (must not start with "UW-Madison")
- [ ] Purchase new domain on Cloudflare
- [ ] Update GitHub Pages custom domain setting
- [ ] Update Cloudflare DNS A records and CNAME to point at new domain
- [ ] Test HTTPS enforcement on new domain
- [ ] Transfer repo ownership to club email (asme@rso.wisc.edu) org account

---

## Background

The UW-Madison Chapter of ASME was removed from university `.edu` hosting. The site was migrated to an independent domain at `uwmadisonasme.org` using GitHub Pages and Cloudflare DNS. After reaching out to Olivia Lemke (Student Engagement and Leadership Manager, College of Engineering), two compliance issues were confirmed per UW Policy UW-207:

1. No UW logos or university indicia may be used in the header area of the site
2. The domain name cannot have "UW-Madison" listed first

The old site was a scraped static copy of the original WordPress site using the UW WordPress theme. The redesign replaced it with a clean HTML/CSS site built on the HTML5 UP Arcana template, keeping all page content and removing all UW branding.

## Compliance Requirements (UW-207)
- No UW logos, crest, or university indicia anywhere in the header
- Domain name must not begin with "UW-Madison"
- No use of the official UW WordPress theme
- No AI-generated images to be used anywhere on the site
- Site must remain on GitHub Pages + Cloudflare setup for easy officer handoff

## What Was Built (Redesign Complete)

Full rebuild using HTML5 UP Arcana template with ASME red (#C5050C) branding. All pages rewritten: Home, Academic, Professional, Design Team, Calendar, Officers, ASHRAE, and all 15 individual officer profile pages.

Changes made:
- Replaced all WordPress blue buttons with ASME red
- Added ASME logo to every page, left-aligned in the header
- Cleaned up all image paths into organized folders (images/officers, images/logos, images/photos)
- Replaced button-based contact links with plain mailto email links
- Added gray placeholder avatars for officers without photos
- Added `<!-- EDIT: update content here -->` comments throughout HTML to mark sections needing regular updates

## Pages
- Home
- Professional
- Academic
- Officers (+ 15 individual officer profile pages)
- Calendar
- Design Team
- ASHRAE

## Local Preview
To test the site locally before pushing:
```
cd "C:\Users\rmeyer\OneDrive - Promega Corporation\Documents\GitHub\uw-madison-asme"
python -m http.server 8000
```
Then open http://localhost:8000 in a browser.

## CMS Setup (Next Step)

Goal is to add a visual editor at `uwmadisonasme.org/admin` so non-technical officers can update content without touching code. Two options being evaluated:

**Decap CMS** -- the more established option, free, works with GitHub. Formerly known as Netlify CMS. Note: Netlify Identity (the login system it relied on) has been deprecated -- authentication needs to go through GitHub OAuth instead.

**Sveltia CMS** -- newer, actively maintained, designed as a drop-in replacement for Decap CMS. Generally considered the better option going forward.

Either way, once set up officers log in at `uwmadisonasme.org/admin` with their GitHub account and can edit content without any coding tools.

## Officer Succession Process
Each year:
1. Add incoming officer as org admin before losing access
2. Remove outgoing officer after handoff
3. Share club email login credentials through a secure handoff document

## Domain Name Options to Consider
- `asme-madison.org`
- `madisonasme.org`
- `asmewisconsin.org`
- `badgerasme.org`
- `asmeuw.org`

Final name TBD -- check availability and purchase through Cloudflare (~$10/year).

## Tools and Stack

**Hosting and deployment:**
- GitHub Pages -- free static site hosting, auto-publishes when changes are pushed to main
- Cloudflare -- DNS management and domain registration
- GitHub Desktop -- pushing changes to the repo without command line

**Development:**
- Claude Code (desktop app) -- used for all HTML/CSS work; point it at the repo folder
- Claude (this interface) -- planning, prompts, and drafting before handing off to Claude Code
- GitHub.com pencil icon -- for simple text edits without any tools

**Repo:**
- GitHub org: `uw-madison-asme`
- Repo: `uw-madison-asme.github.io`
- Local path: `C:\Users\rmeyer\OneDrive - Promega Corporation\Documents\GitHub\uw-madison-asme`



# GOOGLE DOC TO DO LIST
Here's the to-do list you can paste into a Google Doc:

**ASME UW-Madison Website — Handoff & Maintenance To-Do List**

**Step 1: Secure the Repository (Do This Soon)**
- Create a free GitHub Organization at github.com/organizations/new
  - Name suggestion: uw-madison-asme (or similar)
  - Use the club email (asme@rso.wisc.edu) as the owner, not your personal account
- Transfer the website repo into the org (Settings → Danger Zone → Transfer)
- Verify the site still works after transfer (GitHub Pages may need to be re-enabled)

**Step 2: Officer Succession Process (Do Each Year)**
- Add the incoming officer as an org admin BEFORE you lose access
- Remove the outgoing officer from the org after handoff
- Share the club email login credentials through a secure handoff document

**Step 3: Optional — Add a Visual Editor (Decap CMS)**
- Lets officers update calendar, officers list, and partner logos without touching code
- Requires a few hours of setup (ask a technical officer or use Claude Code)
- Free, no subscription, works with GitHub
- Once set up, editors just go to uwmadisonasme.org/admin and log in with GitHub

**Step 4: Regular Site Maintenance (Each Semester)**
- Update officer names, photos, and emails on the Officers page
- Update calendar events
- Update partner logos on the Professional page
- Update Design Team contact info if it changes

**Notes**
- All editable sections are marked with `<!-- EDIT: update content here -->` in the HTML files
- To edit HTML files directly without code tools: go to github.com, navigate to the file, click the pencil icon, edit, and commit
- Site is hosted on GitHub Pages and auto-publishes when changes are pushed to main





> [!info]- Details & Notes
>
> **Unknowns:** New domain name TBD; CMS choice (Decap vs Sveltia) TBD
>
> **See also:** [[GitHub\|GitHub]], [[Cloudflare\|Cloudflare]], [[GitHub Pages\|GitHub Pages]]
