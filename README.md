# Portfolio Site

A single-page personal portfolio (`index.html`) showcasing lab projects, security write-ups, and certifications/badges.

## Structure

The page is organized into sections, including:

- **Lab Projects** — hands-on environments simulating real SOC workflows (Security Operations Home Lab, Wazuh SIEM & Endpoint Monitoring Lab, LetsDefend SOC Investigation Writeups)
- **Certifications & Badges** — a tabbed panel (`Certificates` / `LetsDefend Badges`) displaying earned certificates in a responsive grid, each opening a full-size preview modal on click

Everything lives in a single `index.html` file — HTML, CSS, and JS are all inline, and certificate/badge images are embedded as base64 `data:` URLs (no external image files needed).

## Known Issue Fixed (see CHANGELOG below)

The **Lab Projects** and **Certifications** grids previously had a bug where the last "lonely" card in an incomplete row (e.g., the 3rd project card, or the 7th certificate card) rendered outside the grid entirely and stretched full-width like a banner, instead of matching the size of the other cards.

### Root cause
Stray/duplicate closing `</div>` tags in the HTML closed the `.projects-grid` / `.certs-grid` containers **before** the last card element, pushing that card outside the grid as a sibling element rather than a grid child.

### Fix applied
1. Removed the premature closing `</div>` tags so the last card in each grid stays nested inside `.projects-grid` / `.certs-grid`.
2. Added the grid's real closing `</div>` after the last card instead.
3. Removed leftover/conflicting CSS rules (`.cert-card:last-child:nth-child(3n+1)` width/margin overrides) that were originally hacked in to "patch" the visual symptom — these are no longer needed now that the HTML nesting is correct, and were actually causing the last card to shrink/crop once it was back inside the grid.
4. Verified the file's `<div>`/`</div>` and `<section>`/`</section>` tag counts are balanced.

## Maintenance Notes

- If you add or remove cards from `.projects-grid` or `.certs-grid`, double-check that every `.proj-card` / `.cert-card` closes with exactly one `</div>` and that the grid container's closing tag comes **after** the last card, not before.
- Since the file is large (due to embedded base64 images), avoid using tools like `cat` or naive diff viewers that print the whole file — prefer searching for specific class names or line ranges when editing.
