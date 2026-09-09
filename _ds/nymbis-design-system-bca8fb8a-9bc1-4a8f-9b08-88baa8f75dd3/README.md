# Nymbis Design System

The design system for **Nymbis Cloud Solutions** and its product family:
**Cuumulo** (AI chatbot) and **PortKey** (access product).

> *"Navigate the Cloud Continuum. Our seamlessly integrated Cloud Solutions
> enhance enterprise fluidity, so you work smarter, not harder."* — Nymbis
> Brand Guide v2

---

## The company

Nymbis Cloud Solutions is a South-African-born, customer-centric cloud
integrator. It delivers enterprise-grade cloud infrastructure and AI
solutions: data protection (Veeam Gold Service Provider), cloud computing,
backup, disaster recovery, storage, and data-centre hosting. The pitch is
**"fast to deploy, easy to manage, impossible to outgrow."**

The brand architecture is:

```
         Nymbis (parent brand — Cloud Solutions)
        ┌─────────────────┴─────────────────┐
   Cuumulo (AI chatbot)              PortKey (product)
```

- **Nymbis** — the master brand. Sober plum + cherry-red tone, expert
  and reassuring voice. Used for all corporate collateral, the main
  marketing site, product sheets, decks.
- **Cuumulo** — AI chatbot. Friendly cloud mark with a chat-bubble twist
  and eye dots. Leans more playful, but stays in the Nymbis gradient
  family.
- **PortKey** — access / key product. A wordmark with a small key-stem
  hanging off the `p`. Ships in the widest colour range of the three
  (orange, pink, red, light + dark purple, nymbis gradient).

### Brand voice (from the brief)

> Expert, enabling, dependable, and proudly local. Professional,
> strategic and reassuring on LinkedIn; more conversational and human
> on Facebook. Clear, with conviction — translate complex cloud and
> security topics into practical business outcomes. Occasionally
> playful.

---

## Sources

All source files the system was built from live under `uploads/` (kept
for reference; do not ship):

| File | What it gave us |
| ---- | --------------- |
| `uploads/Nymbis_Brand_Guide-040723-v2.pdf` | Master brand guide — palette, type, clear-space, gradient mesh, circuit-board & cloud motifs, iconography rules, applications (cards, letterhead, email sig, deck, vehicle, homepage) |
| `uploads/EncodeSans-VariableFont_wdthwght.ttf` | Encode Sans variable font (weights 100–900 × widths 75–125). Used at **wdth ≈ 112 ("SemiExpanded")** per the brand guide — all other widths are forbidden. |
| `uploads/EncodeSans_Expanded-Medium.ttf` | Display cut for headline typography |
| `uploads/Nymbis RGB logos-*.png` | Horizontal Nymbis brandmark — Black / White / Purple / Red / Gradient |
| `uploads/Cuumulo Logo_*.png` | Cuumulo cloud-mark — full logo, icon only, logotype only, each in Black / White / Purple / Gradient |
| `uploads/PortKey RGB logo-*.png` | PortKey wordmark in 9 colourways |

All logos have been copied into `assets/logos/` under predictable
kebab-case names (`nymbis-gradient.png`, `cuumulo-purple-icon.png`,
`portkey-nymbis-gradient.png`, etc.).

> **No codebase or Figma was provided.** The UI kits in `ui_kits/` are
> high-fidelity recreations built from the brand guide + logo assets
> alone. Where a production product UI exists, it should be imported and
> these kits re-aligned against it.

---

## File index

```
colors_and_type.css        ← foundational tokens + typography roles
fonts/                     ← Encode Sans TTFs (variable + Expanded-Medium)
assets/
  logos/                   ← all brand & product logos, kebab-case
preview/                   ← design-system preview cards (700×N)
ui_kits/
  nymbis-marketing/        ← Nymbis homepage + product sheet patterns
  cuumulo/                 ← Cuumulo AI chatbot product UI
  portkey/                 ← PortKey product UI
SKILL.md                   ← cross-compatible Agent Skill manifest
README.md                  ← this file
```

---

## Components

Built React components, exposed on `window.NymbisDesignSystem_bca8fb`. Each
lives in `components/` with a `.jsx` implementation, a `.d.ts` prop
contract, and a `@dsCard` preview.

| Component | What it is |
| --- | --- |
| `Button` | Pill-radius action. Variants: primary (solid plum + cherry glow), secondary (deep plum), outline, ghost, danger. Sizes sm / md / lg. |
| `Badge` | Status pill. Tonal (info, critical, healthy, atRisk), solid, outline and neutral — Nymbis palette only, optional leading dot. |
| `Card` | Content surface with optional eyebrow, title and footer. Tones: light, plum, deep. |
| `Alert` | Inline status message with a left-border accent drawn from the semantic tokens. |
| `Input` | Text field with label, helper text and error state. Forces Encode Sans inside the native control. |

```js
const { Button, Badge, Card, Alert, Input } = window.NymbisDesignSystem_bca8fb;
```

---

## CONTENT FUNDAMENTALS

How Nymbis writes.

### Voice

**Expert, enabling, dependable, proudly local.** The brand guide leads
with the line *"Cloud is the future of business success"* — set big
goals and then get operational about delivering them. Never cocky,
never breezy. Always pragmatic.

### Tone by channel

| Channel | Tone |
| ---     | ---  |
| LinkedIn, product sheets, decks | Professional, strategic, reassuring. Full sentences, plain language, outcome-framed. |
| Facebook, social | More conversational, human. Slightly warmer. Still no jokes-for-jokes'-sake. |
| UI (in-product) | Clear and short. Instructional. "Back up your data", not "Let's get that backup going 🚀". |

### Casing

- **Sentence case** for headlines and UI buttons. *"Book an assessment"*, not *"Book An Assessment"*.
- **Title Case** for proper nouns only (product names, section titles in decks).
- Product names are always `Nymbis`, `Cuumulo`, `PortKey` — never nymbis / PORTKEY.
- Capitalise "Cloud" when it refers to the platform/concept in brand
  copy (per the guide: *"Cloud is the future…"*, *"Navigate the Cloud
  Continuum"*).

### Pronouns

- **"We"** for Nymbis — *"We build the infrastructure… so you can focus."*
- **"You"** for the customer — direct, benefit-led.
- Avoid first-person singular. Never "I".

### Sentence shape

- Short declarative openers. *"Data is the currency of business and losing it can prove catastrophic."*
- Benefit-first, mechanism-second. *"Recover exactly what you need, where and when you need it"* — not *"Our platform uses CDP with snapshot orchestration so…"*
- Pair-statements are a Nymbis tic: three short phrases with parallel structure, e.g. *"Data Security · Data Recovery · Data Freedom"*, *"Two platforms. One vision."*

### What to avoid

- **No emoji** in any Nymbis / Cuumulo / PortKey surface. The brand
  guide has none, and nothing in the tone calls for them.
- **No exclamation marks** except on Cuumulo onboarding/empty states
  where "playful" is explicitly in scope — and then sparingly.
- **No jargon dumps** — "hyperconverged multi-tenant edge" etc. If
  a product sheet needs the technical term, always follow with the
  business outcome.
- **No buzzwords on their own** — "Seamless", "Synergy" etc. must be
  attached to a concrete verb or result.

### Example copy

**Hero, long form (product sheet)**
> Intelligent data management for all physical, virtual, onsite and cloud-based workloads.

**Hero, marketing**
> A Customer Centric Cloud Integrator. We provide internationally
> accessible cloud services, solutions and platforms to everyone.

**Sub-hero list (parallel bullets, no periods)**
> - Single point of contact account management
> - Simplified monthly billing
> - Easy to navigate support and escalation to engineering

**CTA pairing**
> Book an Assessment · Content Hub

**Three-up value prop (the Nymbis rhythm)**
> Data Security · Data Recovery · Data Freedom

---

## VISUAL FOUNDATIONS

### Colour

Anchored by **Nymbis Plum** (`#900080`) — the primary brand colour —
with **Fuchsia Purple** (`#9D0081`) as its near-sibling and **Pantone
262 C** (`#420A38`) as the deep plum for large surfaces, footers and
shadows. A warm accent ramp (Pantone 192 C cherry red → orange-red →
salmon → soft pink → light coral) forms the Nymbis Gradient mesh
family, used on hero headlines, CTA strips, and inside the product
logos themselves.

| Role | Hex | RGB |
| --- | --- | --- |
| Primary · Plum | `#900080` | 144 · 0 · 128 |
| Fuchsia Purple | `#9D0081` | 157 · 0 · 129 |
| Pantone 262 C (deep) | `#420A38` | 66 · 10 · 56 |
| Pantone 192 C (cherry) | `#FF1A40` | 255 · 26 · 64 |
| Orange-Red | `#FF583C` | 255 · 88 · 60 |
| Salmon Pink | `#FF6980` | 255 · 105 · 128 |
| Soft Pink | `#FF8C9F` | 255 · 140 · 159 |
| Light Coral | `#FFA89C` | 255 · 168 · 156 |

Neutrals are **warm plum-tinted greys**, not cold slates — the warmed
white `--ink-50` (`#FAF7F9`) next to plum reads as one family; cold
`#F5F5F7` would read as a different brand entirely.

PortKey alone ships in an expanded colourway set (orange, pink, red,
two purples, nymbis gradient) — useful when PortKey needs to feel like
a distinct sub-brand. Nymbis and Cuumulo stay in the primary gradient.

### Type

**Encode Sans Semi-Expanded**, always. The brand guide is explicit:
"*ONLY* use Encode Sans SemiExpanded weightings. Do NOT use
SemiCondensed or Expanded weightings."

Because we ship the variable font, the width axis is pinned to ~112
(`--wdth-semi-expanded`). The one approved departure is
**Encode Sans Expanded (Medium)** for display-scale wordmarks and
large decorative type, which matches the treatment in the Nymbis
wordmark itself. All other widths are out of bounds.

Scale runs 12 → 96 px (body 16 px, H1 56 px, display 72 px). Headlines
sit tight (`line-height: 1.08`), body copy breathes (1.45).

### Gradient mesh

The signature treatment is the Nymbis gradient **used as a fill inside
text outlines** — see `.gradient-text` in `colors_and_type.css`. The
brand guide reserves this for headers and important info, on either
white or plum backgrounds. Don't stack gradient copy on gradient
backgrounds — the guide's examples keep one surface flat.

### Backgrounds

Three canonical backgrounds, all from the brand guide:
1. **White** (`--bg-1`) — default
2. **Plum** (`--bg-plum`, `#900080`) — hero / section breaks
3. **Digital circuit-board on plum** — subtle texture, reserved for
   hero flourishes. *(We do not ship a stock circuit-board PNG; if
   you need one, ask the user to supply a raster from the guide.)*

Plus the creative "digital cloud" motif — soft cloud shapes bleeding
off the left/right edges — used mainly on web heroes.

### Imagery

Nymbis imagery is **treated photography**: product photos pushed into
the brand gradient via curves + saturation. Result: warm, slightly
unreal, still professional. Never stock-photo flat. If a real image is
missing, use a plum placeholder block rather than an untreated stock
image.

### Radii

Brand wordmarks are **heavily rounded** (the lowercase letterforms are
almost lozenge-like). UI echoes that with generous radii:
- `--radius-sm: 8px` — inputs, small chips
- `--radius-md: 12px` — buttons, cards
- `--radius-lg: 20px` — hero cards, modals
- `--radius-pill: 999px` — pills, primary CTAs at display scale

### Borders

- Default hairline: `1px solid var(--border-1)` (`#E4DBE3`). Warm, not cold.
- No heavy dark outlines on cards — the brand's "soft and rounded" DNA
  calls for either no border + subtle shadow, or a 1px warm border
  alone.

### Shadows

All shadows are **plum-tinted**, not grey. See `--shadow-xs` → `--shadow-xl`.
`--shadow-glow` is a magenta-red glow for hero CTAs and important
highlights.

### Hover & press states

- **Primary buttons** — on hover, brighten the gradient by ~6% and lift
  via `--shadow-glow`. On press, drop the shadow and scale(0.98).
- **Secondary / outline** — on hover, fill becomes `--bg-3`; border
  goes `--border-2`. On press, background goes `--nymbis-plum`/5%.
- **Ghost links** — hover = cherry-red underline; visited = plum.
- All transitions use `--dur-base` (200 ms) with `--ease-out`. No
  bounces in UI. Bounce / spring (`--ease-spring`) reserved for
  marketing animations — the playful Cuumulo onboarding, PortKey
  connection success, etc.

### Animation

The brand doesn't use motion heavily. When it does:
- **Fades** (200 ms ease-out) for appearance/disappearance
- **Rise** (12 px → 0, 360 ms ease-out) for hero reveals
- **No spin, no wobble, no typewriter effects**
- The gradient mesh can **shimmer** slowly on hero CTAs
  (`background-position` animated over 8 s linear) — sparingly.

### Corner & layout rules

- 12-column 1280 grid for marketing; 72 px gutters at full bleed.
- Hero sections cap at 1200 px content width with generous 96 px
  vertical padding.
- No right-hand column nav. The brand guide's homepage mock is a
  clean left-aligned hero with horizontal top nav.

### Transparency & blur

Used only on Cuumulo product chrome — a soft blurred plum glass panel
for the message bubble background in-product. Not used on marketing.

### Imagery vibe

**Warm, saturated, treated**. The colour temperature across the system
is warm — even the whites have plum in them. Nothing cold, no
monochrome, no grain.

---

## ICONOGRAPHY

The brand guide defines three valid icon styles:

1. **Gradient-mesh icons** — stroke-based icons filled with the Nymbis
   gradient. Used on plum backgrounds primarily. *Hero treatment.*
2. **Full-colour combo icons** — icons that use multiple palette
   colours per icon (e.g. a cloud in plum with a cherry accent).
3. **Flat colour icons** — single-fill icons in one brand colour.
   Used in dense UI (nav, product sheets).

There is **no built-in icon font** shipping with Nymbis. The brand
guide shows bespoke illustrations, not a systematic icon set. Because
we didn't receive a production icon sprite, the UI kits in this
design system use **[Lucide](https://lucide.dev)** loaded from CDN as
a stand-in: Lucide's rounded, medium-stroke aesthetic is the closest
widely-available match to Nymbis's soft lozenge letterforms.

> **Substitution flag.** Lucide is not the official Nymbis icon set.
> If you have a production icon library (SVG sprite, Figma component,
> etc), please share it and the UI kits will be updated to use it.

Usage rules, adapted from the brand guide:

- **Stroke weight**: 1.75 px (Lucide default at 24 px)
- **Size**: 16, 20, 24 px for UI; 32, 40, 48 px for marketing
- **Colour**:
  - On white → `--nymbis-plum` for primary icons, `--fg-2` for
    secondary, `--nymbis-cherry` for destructive.
  - On plum → `--ink-0` for primary, or fill with
    `--nymbis-gradient` for hero icons.
- **No emoji**. Not in marketing, not in-product, not in error
  toasts. This is a hard brand rule.
- **No Unicode dingbats as icons** (arrows, check-marks, etc). Use a
  real icon or a real SVG.

### Placeholder iconography

Where a unique product illustration is called for (cloud, circuit,
key), we reference the brand marks themselves — `assets/logos/cuumulo-gradient-icon.png`
makes a valid "cloud chat" glyph; `assets/logos/portkey-gradient.png`
carries the "key" stem.

---

## What's missing (known gaps)

These are captured here so the user can patch them back in:

1. **Production icon set** — substituted with Lucide. See above.
2. **Photographic imagery** — no stock of Nymbis-treated photos was
   supplied. UI kits use plum placeholder blocks.
3. **Circuit-board texture PNGs** — referenced in brand guide but not
   shipped as raster. The UI kits use a CSS-generated subtle noise
   where needed.
4. **Product-specific UI source** — no codebase or Figma link was
   shared. UI kits are brand-aligned recreations, not mirrors of
   production screens. Reconcile once real source is available.

---

## Iterating

When adding new components, follow the pattern in `preview/`: a 700 px
card that **shows the thing**, with no surrounding title or explanation
(the tab chrome renders the name outside the card). Register each card
via the asset manifest with its group (`Type`, `Colors`, `Spacing`,
`Components`, `Brand`).
