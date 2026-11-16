# Tongyi heat-pump guide — notes for the next session

Static site (no build step): an installer/homeowner guide for the **Tongyi TAHMV12S R** 12 kW R290 heat pump + **EFJ01-A01 Hydro Box** + 200 L buffer + 500 L DHW tank. Open the HTML files directly in a browser.

## Files
- `index.html` — wiring + controller guide (terminal explorer, connections, water/pipes, scenarios, controller manual).
- `app-menu-guide.html` — Huilian Smart app / wired-controller menu guide (parameter tables, status, glossary).
- `index-sl.html`, `app-menu-guide-sl.html` — Slovenian versions.
- `assets/` — photos and screenshots used by the pages.

## Rules when editing
- **Every content change goes into both languages** (EN file and its `-sl` twin).
- **Keep EN and SL element-for-element identical in structure.** The 🇸🇮 SL / 🇬🇧 EN header button keeps the reading position by passing the index of the element at the top of the screen (`?pos=<index>_<fraction>`, script at the end of each page). If the structures diverge, the switch lands in the wrong place. Verify after edits: render both pages in headless Chrome (`google-chrome --headless=new --dump-dom`) and compare the sequence of tags inside `<body>` — it must match.
- Controller/app **menu names and on-screen values stay in English** (e.g. `[Hot Water Function]`, `On`, `Config 6`), optionally with a Slovenian gloss. Only switch to Slovenian names if it's confirmed the controller offers Slovenian (Set menu → Display Setting → Language; not yet checked on a real unit).
- Slovenian terms in use: TSV = topla sanitarna voda (DHW, owner approved), hranilnik toplote (buffer), FID stikalo (RCD), Monter (installer badge).
- English text uses US spelling (color, gray).
- SVG diagram labels must fit their boxes — Slovenian is longer; shorten text rather than resize boxes.
- No Claude/AI attribution in commits, PRs or anywhere on GitHub.

## Status (as of 2026-11-16)
Done and pushed:
- Slovenian translation of both pages + EN/SL toggle that keeps the scroll position.
- Condensate-drain section (index.html §5, `#condensate`): the drain hole is at the very bottom of the outdoor unit; route the water into soil/gravel **away from concrete** so it doesn't soak in, freeze and crack it.

Open items:
- **Hosting:** the site is not published anywhere yet (GitHub Pages is off). Ask the owner whether to enable GitHub Pages (`https://fixmoose.github.io/guide_tongyi/`) or host elsewhere.
- Check on a real controller whether Slovenian is an available language (see rule above).
- Slovenian text was machine-translated — a native-speaker read-through is worthwhile.
- Decimal style is mixed on SL pages (comma in prose, point in diagrams/tables) — cosmetic.

## Source material (not in this repo)
The manufacturer manuals the guide is built from live on the owner's desktop in the parent `Tongyi/` folder (Service Manual R290 V2 PDF, Hydro Box user manual, Huilian Smart app manual, photos). They are not on GitHub (public repo; some files are business documents). The service-manual accessory table lists 2 drain nipples, 2 PVC hoses and 3 rubber plugs for the outdoor-unit base pan; §4.1.4 says to raise the unit enough to fit the drain nipple.
