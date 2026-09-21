# Design system

RLCore is sold to businesses that judge a web agency by how its own site looks. The
visual language is therefore a product decision, and it is written down rather than
improvised per page.

---

## Tokens first

Color, spacing, radius, elevation and motion are CSS custom properties defined once on
`:root`, redefined under a dark-mode block, and consumed everywhere through Tailwind 4's
theme layer. No component hardcodes a hex value. Switching the accent color of a client
site is one variable, not a find-and-replace.

---

## A catalogue of motifs, not one-off backgrounds

Fourteen decorative primitives are specified — geometry, layering and the exact token
each one draws from — so that a new page composes from a known vocabulary instead of
inventing another gradient:

| | |
|---|---|
| Hero halo | Bi-tone aura |
| Technical grid | Dot matrix |
| 45° hatching | Conic aura |
| Gradient rules | Break diamond |
| Gradient frame (1px padding) | Corner markers |
| Icon chips (14% tint) | Status pills (good / warn / crit) |
| Organic blob | Background grain |

A "typical hero" combination is documented as a recipe, so the most-used composition is
reproducible rather than remembered.

---

## Material elements in pure CSS

Six objects — open laptop, browser window, keyboard in perspective, terminal, phone with
notifications, hovered tile with cursor — are built entirely in CSS. No image assets, no
3D library, no mockup PNGs to re-export when the brand shifts. They theme with the rest
of the system and cost nothing in bandwidth.

---

## One language, three surfaces

The same tokens drive the marketing site, the tenant dashboard and transactional email.
Email gets a deliberately reduced variant — mail clients do not have custom properties,
gradients or modern layout — derived from the same source values so the two never drift
into different brands.

---

## A constraint worth recording

The build's CSS minifier strips `backdrop-filter` in some contexts, so any real
background blur is applied as an inline style from JavaScript rather than a class. It is
the kind of thing that costs an afternoon once and five seconds forever after, provided
somebody wrote it down.
