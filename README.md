# Coast Implementation Guide

The customer-facing implementation deck, as a single self-contained HTML page. No build step, no dependencies, no framework. Everything — styles, scripts, the Coast logo — lives in `index.html`.

## Publishing it

1. Create a repo (e.g. `coast-implementation-guide`) and add `index.html` at the root.
2. **Settings → Pages → Source: Deploy from a branch**, branch `main`, folder `/ (root)`.
3. It goes live at `https://<org>.github.io/<repo>/` within a minute or two.
4. Optional: add a `CNAME` file containing a custom domain (e.g. `implementation.coastapp.com`) and point a DNS CNAME record at `<org>.github.io`.

## Personalizing per customer

Append URL parameters to the link. Nothing is stored server-side and no file is duplicated — one page serves every customer.

| Parameter | What it does | Example |
|---|---|---|
| `co` | Customer company name | `co=Acme%20Foods` |
| `owner` | Customer project owner (adds a row to the cover) | `owner=Jane%20Diaz` |
| `ipm` | Implementation Planning Meeting date, `YYYY-MM-DD`. Every milestone date is computed from this in business days. The old name `kickoff` still works. | `ipm=2026-09-15` |
| `track` | `standard` (5 weeks) or `custom` (7 weeks). Defaults to standard. | `track=custom` |
| `spec` | Implementation specialist name | `spec=Sam%20Ortega` |
| `ae` | Account executive name | `ae=Chris%20Lee` |

Full example:

```
https://<org>.github.io/<repo>/?co=Acme%20Foods&owner=Jane%20Diaz&ipm=2026-09-15&track=custom&spec=Sam%20Ortega
```

Any parameter you leave off falls back to a generic placeholder, so the bare link is always safe to send. Spaces need to be `%20`.

## Editing the content

Open `index.html` in the GitHub web editor and find the block marked `CONTENT CONFIG` near the top of the `<body>`. Everything customer-facing lives in the `CONFIG` object:

- **`thresholds`** — the deadline numbers. Change `dataDueBizDays` and every computed date, the checklist, and the commitment slide all update together.
- **`tracks`** — the two timelines. Each has an `overview` array (drives the at-a-glance week grid — `from`/`to` are week numbers) and a `rows` array (drives the week-by-week detail slide). Keep them consistent with each other.
- **`dataItems`** — everything we may ask for. One deadline; which items apply is confirmed at the IPM.
- **`delays`** — the "what slows implementations down" items.
- **`links.template`** — currently `#`. **Point this at the data collection template before sending the deck to anyone.**

Slide copy that isn't in `CONFIG` sits in plain HTML further down, one `<section class="slide">` per screen, in order.

## Adding or removing a slide

Copy an existing `<section class="slide" id="sN" data-label="...">` block and give it a unique `id`. Footer numbers build themselves from whatever sections are present, in document order, so there's no renumbering to do. `data-label` is just a plain-English note naming the section — nothing renders it.

## Notes

- **Printing.** `Cmd/Ctrl+P` produces a clean one-slide-per-page PDF, for customers who want a file.
- **Checklist state** is saved in the customer's own browser via `localStorage`, keyed on the `co` parameter. It never reaches Coast, and it's per-browser — not a progress tracker.
- **Mobile** drops the deck behaviour and becomes a normal scrolling page.
- **Keyboard**: arrow keys, page up/down, space, home, and end all navigate between slides.
