# Maintaining the Player Guide

This repo is the **player-facing website** for *The Shadow Exchange*: **https://delonsampaio.github.io/The-Shadow-Exchange-Players/**

It is built with **MkDocs Material** and republished automatically by GitHub Actions on every push to `main` (about a minute).

## How to update it

1. **Edit or add Markdown** in `docs/`.
2. **Links:** use normal Markdown links — `[Text](Page-Name.md)` — **not** `[[wiki links]]`.
3. **New page?** Add it to `nav:` in `mkdocs.yml` (recaps go under *The Campaign*).
4. **Images:** put them in `docs/assets/` (resize to ~1400 px wide, JPEG) and reference them with `../assets/name.jpg` from a page, or the `.portrait` / `.figure` CSS classes.
5. **Preview locally (optional):**
   ```
   pip install "mkdocs>=1.6,<2" mkdocs-material
   mkdocs serve        # live preview at http://localhost:8000
   mkdocs build --strict   # fails on broken links — run this before pushing
   ```
6. **Commit and push** to `main`. The site updates itself. Check the *Actions* tab if it doesn't.

## After every session
- Add `docs/Session-NN-Recap.md`, add it to `nav:`, and link it from `docs/Session-Recaps.md`.
- Add Anchor decisions to `docs/The-Anchor-Ledger.md` and newly met people to `docs/Known-Contacts.md`.
- Update `docs/Our-Lair.md` only if the lair changed.

## The Home page evolves as the campaign is played
- **Before Session 1:** Home is onboarding (three "Start here" cards). Leave it.
- **After the first recap is published:** swap those cards for three **current-state** cards, and refresh them after every session:

```markdown
<div class="grid cards" markdown>

- :material-book-open-page-variant:{ .lg } **Latest recap**

    One-sentence hook for the newest session.

    [Read Session N →](Session-NN-Recap.md)

- :material-map-marker-path:{ .lg } **Where we left off**

    Two or three sentences, from the crew's point of view, about what they carry into the next session.

- :material-help-circle:{ .lg } **What we're wondering**

    - An open question the *players* have (no answers)
    - Another one

</div>

*New here? [Start here](Quick-Start.md).*
```

- Keep the hero and pitch quote. The **Start Here** tab and onboarding pages stay for reference.
- Optional: a small "Crew status" table (Coin, Heat, Rep, and only clocks the players have seen).
- These cards get the **same spoiler check** as the recap — publish only what the crew has learned.

## IMPORTANT — spoilers
This site is **public** and is read by the players. **Publish only what the players' characters have actually seen or learned.** Before publishing any campaign content, run the **spoiler check in the GM's private notes** (`Wiki-Update-Protocol.md` in the private campaign repo). If you are unsure whether something is a secret, **leave it out** and ask the GM.

## Look and feel
Dark "rain-slick night" theme (light mode = old paper), amber accent, Oswald headings, Lora for quotes. Styles live in `docs/stylesheets/extra.css`; the Home page hero and cards are plain HTML/Markdown in `docs/index.md`.

## Credit
*Blades in the Dark* is by John Harper (One Seven Design), used under CC BY 3.0 — the credit is in the site footer (`copyright:` in `mkdocs.yml`). Keep it.
