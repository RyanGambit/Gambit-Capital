# Gambit Capital — Handoff to Claude Code

## What this is

A single-page marketing site for **Gambit Capital**, a new PE arm leveraging Gambit Co's operator DNA. Sister site to Ancrage (`github.com/RyanGambit/ancrage-PE`) but with its own positioning and visual system.

Working file: `gambit-capital-v3.html` (single-file HTML with inline CSS and a small block of vanilla JS at the bottom).

## Brand non-negotiables

- **No em-dashes anywhere in copy.** House rule. Use commas, periods, parentheses.
- **"Workers" not "agents" or "copilots."** Brand-defining language across all Gambit properties.
- **Green is status-only.** `--working: #16a34a` is reserved for the pulsing eyebrow dot and "in production" tags. Never decorative.
- **Typography:** General Sans (body), Orbitron (lockup only), JetBrains Mono (eyebrow / labels / mono).

## Palette

```
--ink: #0a0a0a            (primary dark)
--ink-deep: #050505       (contact band)
--ink-blue: #1a2942       (cool dark register, available)
--sand: #f5f5f3           (warm light section bg)
--page: #fafafa           (cool light section bg)
--white: #ffffff
--clay: #b8957a           (editorial accent — Mandate top border, How rail, Insights featured)
--clay-soft: #d6c0aa
--working: #16a34a        (status only)
--secondary, --muted, --border (utility grays)
```

Clay was added recently as the editorial accent. It appears in 3 places intentionally: Mandate card top border, How we invest sticky rail graphic, and Insights featured card border. Don't add clay to other sections without thinking about it.

## Page structure (locked)

1. **Hero** — ink band. H1 "We build. We deploy. We back." Subheader: "From the pioneers at Gambit. We've watched AI compound enterprise value in physical industries. **Now we're putting that capital to work**, with forward-deployed teams and AI workers in every deal."
2. **01 · Thesis** — light. Two beats. Headline: "The next decade of outsized returns belongs to operators who put AI inside the physical world."
3. **02 · Mandate** — sand band, white inset card with clay top border. Headline: "Looking for the next generation of compounders." Spec table + pass coda.
4. **03 · How we invest** — ink band (visual chorus). Sticky vertical SVG rail on the left + three Moments on the right. Headline: "We work first. We invest second."
5. **04 · Team** — light. Two cohorts: 5 partners (4 named + 1 pending Portfolio Mgmt) and 5 AI workers. Real photos with grayscale filter, color-on-hover.
6. **05 · News & Insights** — sand. Magazine layout: featured card on the left + 3 stacked list items on the right.
7. **06 · Contact** — ink-deep. Headline: "We'd like to hear from you." Email: capital@gambitco.io.

Section rhythm: ink → light → sand → **ink** → light → sand → ink-deep. The three dark bands act as the page's chorus.

## Open work (priority order)

### 1. Hero background photograph (NEXT UP)

Hero is currently using a placeholder gradient that simulates dark warehouse atmosphere. The plan is to swap in a real Unsplash photo.

**Spec for the photograph:**
- Subject: machinery or industrial interior at human scale (warehouse aisle, factory floor, conveyor system, refinery interior)
- Strong directional perspective (rows or lines toward a vanishing point)
- Empty or sparsely populated (no people in frame)
- Already moody / dark / contrasty
- Horizontal aspect ratio
- **Avoid:** city skylines, glass office towers, smiling workers, bokeh, tech grid, anything cliché

**Where to put it:**
The hero has a `.hero-bg` div as the first child of `<section id="hero">`. Currently styled with a placeholder gradient. To use a real photo, replace the `.hero-bg` CSS rule's `background-image` with an Unsplash hotlink:

```css
.hero-bg {
  background-image: url('https://images.unsplash.com/photo-XXXXX?w=2400&q=80&auto=format&fit=crop');
}
```

The `.hero-overlay` div above the photo handles text legibility. Don't remove it.

**Suggested Unsplash starting points:**
- https://unsplash.com/s/photos/dark-warehouse
- https://unsplash.com/s/photos/factory-interior
- https://unsplash.com/s/photos/distribution-center
- Specific candidate already considered: https://unsplash.com/photos/a-dark-room-filled-with-lots-of-shelves-scKZFa9oW_Q

### 2. Repo + deploy

This file should go into a fresh GitHub repo (suggest: `gambit-capital`), Vercel-connected with auto-deploy from main. Same model Ryan uses on Ancrage. Team photos in `/img/` need to come along.

### 3. AI workers cohort copy (lower priority)

Currently the second cohort uses placeholder names (Daniel, Priya, Catherine, Adam, Jordan) and bios pulled from Ancrage. These need a Gambit Capital-specific pass. Each AI worker should map to a real role on the deal team. Confirm with Ryan before writing.

### 4. Insights cards (placeholder content)

The Insights section has 4 placeholder articles. These are aspirational — once real long-form content exists, replace. Until then, the cards are stylish vapor.

## Things NOT to do

- **Don't add green outside of status indicators.** Hard rule.
- **Don't introduce new colors** without checking with Ryan. The palette is intentionally narrow.
- **Don't claim NASCAR as a client.** Gambit Co worked with a driver, not the org. Same applies to other Gambit Co clients — confirm before referencing in Gambit Capital materials.
- **Don't over-explain in copy.** The site has been through aggressive trimming. If a sentence reads explanatory, it's probably wrong.
- **Don't restore the "Looking for the first" section.** It was cut intentionally because it duplicated the Contact section's job.

## File locations

- Working HTML: `gambit-capital-v3.html`
- Team photos: `img/team-{hai,pat,seb,ryan}.jpg`
- Pending partner uses an inline SVG monogram, no photo file needed

## Voice cues from this build

- Restrained institutional. Capital firm reading on sophisticated readers.
- Branded illustration / graphic moments (the SVG rail in How we invest is the prototype). Not stock photography overload.
- Short copy. Punch lines do the work. Argument beats are typically 30-50 words, not 80+.
- Headline cadence: declarative, often two-beat. ("We build. We deploy. We back." / "We work first. We invest second.")

