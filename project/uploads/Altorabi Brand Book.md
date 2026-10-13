# The Altorabi Brand Book — v3.0

Machine-readable edition. This is the complete visual and verbal system for the
Altorabi brand (Wael Altorabi — entrepreneur, advisor, investor; Riyadh, Saudi Arabia).

**If you are an AI agent or a developer, this file is the contract.** Treat it as the
single source of truth. Where it conflicts with your defaults, this wins. Never invent
a colour, a typeface, a radius or a spacing value — every one you need is in §10. If a
value you need is genuinely absent, say so rather than inventing it.

The three rules broken most often, in order:
1. The brand green used as text.
2. `letter-spacing` applied to Arabic.
3. Status communicated by colour alone.

Every ratio in this document was measured, not estimated. Colour values were generated
at fixed OKLCH coordinates and run through a colourblindness validator in both themes.
Where a rule says **never**, a measurement failed.

---

## 01 — The mark

A geometric face built from a small number of strokes, set beside the name.

**Assets** (raster PNG, pre-composited per ground):
- Horizontal lockup — light (white / mist grounds)
- Horizontal lockup — night, composited on `#1A1B21` (web dark)
- Horizontal lockup — charcoal, composited on `#2A2A33` (deck slides)
- Face mark — light / night / green (avatar, favicon, corner stamp)

**Clear space** — the height of the face mark, on all four sides. Nothing enters it.

**Minimum sizes**

| Use | Minimum | Asset |
|---|---|---|
| Print | 28 mm | Horizontal lockup |
| Screen | 110 px | Horizontal lockup |
| Below that | 24 px | Face mark alone — never a shrunken lockup |
| Favicon / avatar | 16–512 px | Face mark, centred, 12% padding |

**Rules**
- Use a supplied asset at its native aspect ratio. Never recreate the wordmark by typing the name in a font.
- Match the asset to the ground. A lockup composited on `#2A2A33` placed on `#1A1B21` shows a visible lighter box — this has actually shipped twice.
- The logo does **not** mirror in RTL. Exclude it from any global flip: `[dir="rtl"] .logo{transform:none}`.
- The logo is Latin in both languages. This is settled, not an oversight. Do not typeset an Arabic wordmark.
- Never recolour, gradient, outline, shadow, stretch, condense, rotate or arch it.
- Never place it on a photograph without a solid plate behind it.
- `alt` text is always "Altorabi", never "logo".

---

## 02 — Colour

### Brand

| Name | Hex | Token | Note |
|---|---|---|---|
| Brand green | `#64C379` | `--green` | **Fill only** on light grounds |
| Green ink | `#1F7346` | `--green-ink` | 5.83:1 on white — this is the text green |
| Charcoal | `#2A2A33` | `--char` | Decks, plates |
| Night | `#1A1B21` | `--night` | Web dark ground |
| Green wash | `#E6F3EA` | `--green-wash` | Tints |
| Mist | `#F1F4F2` | `--surface` | Cards on white |

### The three green laws

**1. The brand green is a fill, never text on a light ground.**
`#64C379` on `#FFFFFF` = **2.18:1** against a 4.5:1 requirement — less than half.
Green text uses `--green-ink` at 5.83:1. On dark grounds the brand green becomes
legible again (`#64C379` on `#1A1B21` = 7.87:1) and may be used as text there.

**2. The focus ring is never the brand green.**
Focus indicators need 3:1. At 2.18:1 on white the ring would be legally invisible.
Use `--focus`: Green Ink on light, `#7FD094` (9.88:1) on dark.

**3. Green is identity, not success.**
It appears on primary buttons whether or not anything passed. Success is its own
darker step, `#0A7E3A` at 5.17:1. Corollary: **text on brand green is always dark** —
`#2A2A33` on `#64C379` = 6.51:1, while white on the same green is 2.18:1.

### Neutrals

Green-biased greys. Three text weights, no more.

| Token | Light | On white | Dark | On night | Use |
|---|---|---|---|---|---|
| `--ink` | `#1E2320` | 15.95:1 | `#E9EFE9` | 15.66:1 | Body, headings |
| `--ink-2` | `#4F5A54` | 7.18:1 | `#AAB5AE` | 8.64:1 | Secondary, descriptions |
| `--ink-3` | `#66716B` | 5.07:1 | `#8B968F` | 5.97:1 | Labels, captions, metadata |
| `--ground` | `#FFFFFF` | — | `#131519` | — | Page |
| `--surface` | `#F1F4F2` | — | `#1D2024` | — | Cards, wells |
| `--rule` | `#E1E7E2` | — | `#2B2F31` | — | Hairlines, dividers |

### Status — reserved

| Status | Light | Ratio | Dark | Ratio | Icon |
|---|---|---|---|---|---|
| Success | `#0A7E3A` | 5.17:1 | `#67D283` | 9.68:1 | ✓ |
| Warning | `#935B00` | 5.62:1 | `#F2AF48` | 9.57:1 | ! |
| Serious | `#AF4803` | 5.60:1 | `#F99262` | 8.11:1 | ▲ |
| Critical | `#B32228` | 6.61:1 | `#F97770` | 6.88:1 | ✕ |

Status colours never decorate, never become a chart series, and never appear without
a word or an icon alongside them. Roughly one man in twelve cannot separate the amber
from the green.

**Never introduce a colour that is not in §10.** No new greys, and never use `opacity`
to make text quieter — that breaks the measured ratio. Use `--ink-2` / `--ink-3`.

---

## 03 — Typography

### The stack

| Role | English | Arabic | Arabic delta |
|---|---|---|---|
| Display | Archivo 700–800, tracking −0.025em | IBM Plex Sans Arabic 700, tracking 0 | — |
| Body | IBM Plex Sans 400 · 15.5px / 1.55 | IBM Plex Sans Arabic 400 · 16.5px / 1.75 | +1px / +0.20 |
| UI / labels | IBM Plex Sans 500–600 | IBM Plex Sans Arabic 500–600 | +1px |
| Data, code, IDs | IBM Plex Mono 400–500 | IBM Plex Mono, Western digits | — |

All four are open-licence and load from Google Fonts:

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Archivo:wght@600;700;800&family=IBM+Plex+Sans:wght@400;500;600&family=IBM+Plex+Sans+Arabic:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500&display=swap">
```

Do not substitute Inter, Poppins or Space Grotesk.

### Scale

| Step | Size | Line | Face & weight | Tracking |
|---|---|---|---|---|
| Display | 44–60 | 1.02 | Archivo 800 | −0.03em |
| H1 | 32 | 1.10 | Archivo 800 | −0.028em |
| H2 | 24 | 1.15 | Archivo 700 | −0.022em |
| H3 | 18 | 1.25 | Archivo 700 | −0.015em |
| Body large | 17 | 1.60 | Plex Sans 400 | 0 |
| Body | 15.5 | 1.55 | Plex Sans 400 | 0 |
| Small | 13.5 | 1.50 | Plex Sans 400 | 0 |
| Label | 11 | 1.35 | Plex Sans 600, uppercase | +0.07em |
| Mono | 12–13 | 1.65 | Plex Mono 400–500 | 0 |

Running text stops at about 68 characters — set `max-width:68ch` on prose containers.

### On the STC typeface — do not use it

Three STC font files (Light / Regular / Bold) were supplied for this brand and have
**not** been adopted.

**STC is another company's corporate typeface.** It was drawn by Tarek Atrissi Design
as the custom identity face for **stc — Saudi Telecom Group**. Custom corporate
typefaces are commissioned works, exclusive to the company that paid for them; they
are not licensed for third-party use and there is no shop that sells one. The supplied
files carry `Tarek Atrissi Design` in the manufacturer field and version dates of
October 2014; one also carries an Arabic download-site name in the designer field,
the usual fingerprint of a free-font aggregator rather than an original release.
For a Saudi audience this is not a technicality — the stc face is recognised on sight
in this market.

Setting the licence aside, the files would not carry the system:

| Checked | Found | Consequence |
|---|---|---|
| Weights | 3 — 300 / 400 / 700 | No 500 or 600; the UI scale uses both |
| Glyphs | 372 | No small caps, no tabular figures |
| Latin accents | **none at all** | "José", "Müller", "Zürich", "café" render as missing-glyph boxes |
| Currency | £ only, no € | Fails on a European term sheet |
| Arabic coverage | complete, plus پ چ ژ گ ڤ and both digit sets | Genuinely good |
| Arabic mark positioning | `GPOS` covers `latn` only | Harakat are not properly positioned |

If asked to use STC, say this and offer one of the alternatives below.

### If a single bilingual family is wanted

| Family | Licence | Scripts | Weights | Character |
|---|---|---|---|---|
| **Rubik** | SIL OFL | Arabic, Latin, Latin-ext, Cyrillic, Hebrew | 300–900 variable | Geometric with softened corners — closest legal neighbour to STC's warmth |
| **Tajawal** | SIL OFL | Arabic, Latin | 200–900 | Geometric, cooler, more neutral |

This is a decision to make once, by eye. Changing the stack means re-cutting the deck,
both design-system documents and the Lovable build pack.

### Type rules

**Always**
- Western numerals (0 1 2 3) in both languages. Saudi business and finance use them, and dashboards compare across locales.
- `font-variant-numeric: tabular-nums` wherever digits align in a column.
- Arabic at +1px and +0.2 line-height versus its Latin equivalent.
- Apply the Arabic face by direction, not by class: `[dir="rtl"]{font-family:var(--arabic); line-height:1.75}`

**Never**
- Any `letter-spacing` on Arabic. Arabic letters join — tracking severs them and words break apart. Ship this globally: `[dir="rtl"] *{letter-spacing:normal !important}`
- `text-transform: uppercase` on Arabic. Arabic has no case, so it silently does nothing and the hierarchy disappears. Eyebrow labels are uppercase + tracked in English, and weight-600 in `--green-ink` with no transform in Arabic.
- A fifth typeface, faux bold, faux italic, or Arabic-Indic digits ٠١٢٣ in interfaces.

---

## 04 — Arabic & right-to-left

Every screen must work in **both** English LTR and Arabic RTL from the first commit,
even when only English is requested.

### What mirrors

Page flow, navigation, sidebars, breadcrumbs. Back/forward arrows, chevrons, list
indentation. Progress bars, sliders, steppers. Text alignment, table column order,
form label position.

### What never mirrors

The logo and face mark. Clocks and anything showing real-world direction. Media
playback controls. Checkmarks, and the numerals themselves.

### Time-series charts stay left-to-right in both languages

A time axis is a continuous scale rather than a block of prose, and Arabic readers
meet left-to-right timelines constantly in finance and analytics. Legends, labels,
tooltips and category axes all follow RTL — only the direction of time is held.
Category bar charts **do** mirror. This is the most contested RTL decision in
dashboards; test it with real users.

### Build it logical from day one

```css
[dir="rtl"]   { font-family: var(--arabic); line-height: 1.75; }
[dir="rtl"] * { letter-spacing: normal !important; }
```

Never emit `ml-` `mr-` `pl-` `pr-` `left-` `right-` `text-left` `text-right`
`border-l` `border-r`. Use `ms-` `me-` `ps-` `pe-` `start-` `end-` `text-start`
`text-end` `border-s` `border-e`. In plain CSS: `margin-inline-start`,
`padding-inline-end`, `inset-inline-start`, `text-align: start`, `border-inline-start`.

Doing this on day one is free. Retrofitting it is a rewrite — every hard-coded `left`
becomes a bug that only Arabic users see.

Every user-facing string goes through `t()` into `en.json` / `ar.json` from the start.
No hard-coded English anywhere.

**Before reporting a screen done**, render it in Arabic and confirm: sidebar moved,
chevrons flipped, logo did *not* flip, no broken-apart Arabic words (that means
tracking leaked in).

---

## 05 — Space, shape, elevation

**Spacing — 4px base grid. These eight values only:**
`4 · 8 · 12 · 16 · 24 · 32 · 48 · 64`
In Tailwind: `1 2 3 4 6 8 12 16`. Never an arbitrary value like `p-[13px]`.

**Radius by role**

| Token | Value | Applies to |
|---|---|---|
| `--r-sm` | 6px | Buttons, inputs, chips |
| `--r-md` | 10px | Cards, wells, alerts |
| `--r-lg` | 14px | Panels, modals |
| `--r-pill` | 999px | Status pills only |

**Elevation** — `--e-1` resting card, `--e-2` raised card / dropdown / popover,
`--e-3` modal / floating overlay. **There is no fourth level.**

Not everything is a card. Border, fill, radius and shadow each announce "separate
object". Spend them by role — one radius and one shadow stamped on every block
flattens the hierarchy instead of building it.

**Breakpoints**

| Name | Width | Layout |
|---|---|---|
| Mobile | < 640 | One column, nav in a drawer, tables scroll in their own container |
| Tablet | 640–1023 | Two columns, nav collapses to icons |
| Desktop | 1024–1439 | Sidebar plus content, 12-column grid |
| Wide | ≥ 1440 | Content caps at 1280; sidebar stays fixed |

Lay siblings out with flex/grid and `gap`, not per-element margins. Wide content —
tables, code, charts — gets `overflow-x:auto` on its own container; the page body
never scrolls sideways. Touch targets ≥ 44×44px, icon-only buttons included.

---

## 06 — Components

Use shadcn/ui as the component base and re-skin through the tokens in §10. Do not
hand-roll primitives.

### Buttons

| Variant | Fill | Text | Use |
|---|---|---|---|
| Primary | `--green-ink` | `--on-green-ink` | One per view. The single thing you want done. |
| Secondary | `--ground` + `--rule-strong` border | `--ink` | Everything else |
| Tertiary | none | `--green-ink` | In-table and in-card actions |
| Destructive | `--critical` | white | Deletes, always behind a confirm |

Primary is `--green-ink`, **not** `#64C379`. The label says exactly what happens:
"Publish", then a toast that says "Published". Not "Submit", not "OK", never
"Click here".

### Status pills

Every pill carries an icon **and** a word: `✓ Complete`, `! In review`, `▲ At risk`,
`✕ Blocked`, `— Not started`. Background is the matching `--*-bg`, text the matching
status colour, radius `--r-pill`.

### Empty and loading states

An empty state says what belongs there and offers the action. Never a bare "No data" —
that tells the reader they are missing something without telling them what. Example:
"No documents in Governance yet. Board resolutions, the bylaws and shareholder
consents belong here." followed by the upload control.

Loading uses skeletons shaped like the content that is coming, so nothing jumps. A
centred spinner on a full page is a last resort.

### Tables

Sticky header over ten rows. Numerals end-aligned and `tabular-nums`. Column order
mirrors in RTL. Row actions revealed on hover **and** reachable by keyboard.
`overflow-x:auto` on the wrapper, not the page.

Never: zebra striping and borders together; a coloured row as the only signal of
state; truncation without a title or tooltip carrying the full value; more than seven
columns before offering a column chooser.

Icon-only buttons need an `aria-label` and a 44px hit area.

---

## 07 — Data & charts

Seven series hues, generated at fixed OKLCH coordinates and validated for
colourblindness in both themes. **Assigned in this order, always.**

| # | Light | Dark |
|---|---|---|
| `--s1` | `#1B9247` | `#2C974F` |
| `--s2` | `#4777D2` | `#4E7DD6` |
| `--s3` | `#AC6900` | `#B17000` |
| `--s4` | `#8F5FC0` | `#9567C5` |
| `--s5` | `#C24D5D` | `#C75664` |
| `--s6` | `#0091A4` | `#0097A9` |
| `--s7` | `#6C8700` | `#728D02` |

**The order is warm–cool–warm–cool, and that is the whole trick.** Red-green
colourblindness collapses green, olive, amber and rose toward one another.
Interleaving them with blue, violet and teal means no two confusable hues ever land
side by side. An earlier draft ordered these by taste and failed at ΔE 0.9 — two
adjacent series a deuteranopic reader could not tell apart at all.

**Always**
- Series assigned `--s1` → `--s7` in order, from the first series. Never generate a palette.
- A legend whenever there are two or more series.
- Every axis label names a value the chart actually reaches.
- Chart text takes theme text tokens (`--ink` / `--ink-2`), never the series colour, so it reads in both themes.
- A "View as table" toggle beside every chart, for screen readers.
- Sequential data: one hue, light to dark. Diverging: two hues with a neutral grey midpoint.
- In SVG, leave room in the `viewBox` for the outermost labels and give every shape an explicit fill.

**Never**
- Two y-axes. Ever. Use two charts.
- Reorder or recycle series when a filter changes the count — series 3 keeps `--s3` when series 2 is hidden.
- An eighth hue. Fold rare categories into "Other" at `--ink-3`.
- A status colour as a series colour.
- A pie chart with more than five slices, or a 3D chart at all.
- A truncated y-axis on a bar chart.

---

## 08 — The accessibility contract

WCAG 2.2 AA, as a build requirement rather than an audit at the end. Nine checks — if
all nine pass, the work is done. State which ones you verified.

| # | Check | Threshold |
|---|---|---|
| 1 | Body text contrast | ≥ 4.5:1 |
| 2 | Large text (≥ 24px, or ≥ 19px bold) | ≥ 3:1 |
| 3 | Focus indicator and UI component boundaries | ≥ 3:1 |
| 4 | Visible `:focus-visible` ring on every interactive element | 2px, 2px offset |
| 5 | Touch target | ≥ 44×44px |
| 6 | Status never communicated by colour alone | Icon or word |
| 7 | Every icon-only control has an `aria-label` | — |
| 8 | Keyboard reaches everything a mouse reaches | — |
| 9 | `prefers-reduced-motion` respected | — |

Three real defects were found this way in material that had already shipped: a muted
tone measuring 4.45:1 where it needed 4.5; two chart series a colourblind reader could
not separate; white text on the flipped dark-mode green at 1.85:1 — fixed at token
level with a paired `--on-green-ink` that flips with it, rather than patched in one
component. **Measure, don't estimate.**

Never remove a focus outline without replacing it with a visible one measuring 3:1.
Screenshot every route in four states: English light, English dark, Arabic light,
Arabic dark.

---

## 09 — Voice

The audience is founders, investors, boards and regulators — people short of time and
allergic to being sold to. Assume the reader is clever and busy.

**Sounds like us**
- **Specific.** "Nine sections, roughly forty documents" — not "comprehensive coverage".
- **Evidence first.** The number, then the claim it supports.
- **Plain.** Short sentences. Ordinary words. Say the thing.
- **Practitioner, not commentator.** Written by someone who has done it, for someone about to.
- **Direct address.** "You", "your company".

**Doesn't**
- Hype. Banned in brand copy: revolutionary, game-changing, unlock, supercharge, leverage, seamless, cutting-edge, world-class.
- Hedging: "we believe we may be able to help you consider".
- Credential-stacking as a substitute for a point.
- Exclamation marks. Emoji in professional material.
- Anglicised Arabic.

**Arabic is written, not translated.** Modern Standard Arabic, in the register of Saudi
business rather than literature. Interface strings stay short — Arabic runs longer than
English and a translated button label will break the layout that fitted the English one.
Names of institutions, funds and companies keep their registered form in both languages.

**Interface copy.** A control says what happens: Publish → Published. An error says what
went wrong and how to fix it, with no apology and no vagueness: "That file is 48 MB. The
limit is 25 MB — try compressing it or splitting it in two." Name things the way a person
recognises them: someone manages *notifications*, not *webhook configuration*.

---

## 10 — Tokens

Copy a block verbatim. **Do not adjust any value**, even slightly.

Define every token in the bare `:root` before any media or `[data-theme]` block
redefines it — a colour that exists only inside a dark block renders one theme's text
on the other theme's ground. Style components through tokens only; never a literal hex
in a component.

### CSS custom properties

```css
:root{
  /* brand */
  --green:#64C379; --green-ink:#1F7346; --green-wash:#E6F3EA; --on-green-ink:#FFFFFF;
  --char:#2A2A33; --night:#1A1B21; --slate:#24252D;
  /* surfaces */
  --ground:#FFFFFF; --surface:#F1F4F2; --surface-2:#E8ECEA;
  --rule:#E1E7E2; --rule-strong:#CBD4CE;
  /* text */
  --ink:#1E2320; --ink-2:#4F5A54; --ink-3:#66716B;
  --on-night:#E8EFE9; --on-night-2:#A7B3AC;
  /* status */
  --success:#0A7E3A; --warning:#935B00; --serious:#AF4803; --critical:#B32228;
  --success-bg:#E4F3E9; --warning-bg:#F8EFDC; --serious-bg:#FAEBE0; --critical-bg:#FAE7E7;
  --focus:#1F7346;
  /* data series — fixed order */
  --s1:#1B9247; --s2:#4777D2; --s3:#AC6900; --s4:#8F5FC0;
  --s5:#C24D5D; --s6:#0091A4; --s7:#6C8700;
  /* type */
  --display:"Archivo","Arial Black",Helvetica,sans-serif;
  --body:"IBM Plex Sans","Segoe UI",Helvetica,Arial,sans-serif;
  --arabic:"IBM Plex Sans Arabic","Segoe UI",Tahoma,sans-serif;
  --mono:"IBM Plex Mono",ui-monospace,SFMono-Regular,Menlo,monospace;
  /* space & shape */
  --s-1:4px; --s-2:8px; --s-3:12px; --s-4:16px;
  --s-5:24px; --s-6:32px; --s-7:48px; --s-8:64px;
  --r-sm:6px; --r-md:10px; --r-lg:14px; --r-pill:999px;
  --e-1:0 1px 2px rgba(30,35,32,.05);
  --e-2:0 1px 2px rgba(30,35,32,.04), 0 8px 24px rgba(30,35,32,.06);
  --e-3:0 2px 4px rgba(30,35,32,.06), 0 18px 44px rgba(30,35,32,.10);
}

/* dark — redefine tokens only, never component styles.
   Repeat this same block under :root[data-theme="dark"] so an explicit
   toggle wins in both directions. Three theme states, not two. */
@media (prefers-color-scheme: dark){ :root:not([data-theme="light"]){
  --green-ink:#7FD094; --green-wash:#1D3227; --on-green-ink:#12200F;
  --ground:#131519; --surface:#1D2024; --surface-2:#262A2E;
  --rule:#2B2F31; --rule-strong:#3A4043;
  --ink:#E9EFE9; --ink-2:#AAB5AE; --ink-3:#8B968F;
  --success:#67D283; --warning:#F2AF48; --serious:#F99262; --critical:#F97770;
  --success-bg:#16301F; --warning-bg:#33270F; --serious-bg:#331F14; --critical-bg:#331717;
  --focus:#7FD094;
  --s1:#2C974F; --s2:#4E7DD6; --s3:#B17000; --s4:#9567C5;
  --s5:#C75664; --s6:#0097A9; --s7:#728D02;
  --e-1:0 1px 2px rgba(0,0,0,.35);
  --e-2:0 1px 2px rgba(0,0,0,.4), 0 8px 24px rgba(0,0,0,.3);
  --e-3:0 2px 4px rgba(0,0,0,.45), 0 18px 44px rgba(0,0,0,.4);
}}

/* base rules — ship these in every project */
[dir="rtl"]{font-family:var(--arabic); line-height:1.75}
[dir="rtl"] *{letter-spacing:normal !important}
:focus-visible{outline:2px solid var(--focus); outline-offset:2px}
@media (prefers-reduced-motion:reduce){*{animation:none !important; transition:none !important}}
```

`--on-green-ink` flips with the theme, and that is the point. In light mode the accent
is dark green and its text is white. In dark mode the accent lightens to `#7FD094`,
where white text would measure 1.85:1 — the paired token flips to near-black at 9.16:1.
Fix that pairing at token level; never patch it inside one component.

### shadcn/ui — HSL triplets

For React + Tailwind + shadcn, including anything built in Lovable. Drop into
`src/index.css`.

```css
@layer base {
  :root {
    --background: 0 0% 100%;          --foreground: 144 8% 13%;
    --card: 140 12% 95%;              --card-foreground: 144 8% 13%;
    --popover: 0 0% 100%;             --popover-foreground: 144 8% 13%;
    --primary: 148 58% 29%;           --primary-foreground: 0 0% 100%;
    --secondary: 150 10% 92%;         --secondary-foreground: 144 8% 13%;
    --muted: 140 12% 95%;             --muted-foreground: 147 5% 42%;
    --accent: 133 44% 58%;            --accent-foreground: 240 10% 18%;
    --destructive: 358 68% 42%;       --destructive-foreground: 0 0% 100%;
    --border: 130 11% 89%;            --input: 140 9% 81%;
    --ring: 148 58% 29%;
    --success: 145 85% 27%; --warning: 37 100% 29%; --serious: 24 97% 35%;
    --chart-1: 142 69% 34%;  --chart-2: 219 61% 55%;  --chart-3: 37 100% 34%;
    --chart-4: 270 43% 56%;  --chart-5: 352 49% 53%;  --chart-6: 187 100% 32%;
    --chart-7: 72 100% 26%;
    --radius: 0.625rem;
  }
  .dark {
    --background: 220 14% 9%;         --foreground: 120 16% 93%;
    --card: 214 11% 13%;              --card-foreground: 120 16% 93%;
    --popover: 214 11% 13%;           --popover-foreground: 120 16% 93%;
    --primary: 136 46% 66%;           --primary-foreground: 109 36% 9%;
    --secondary: 210 10% 16%;         --secondary-foreground: 120 16% 93%;
    --muted: 214 11% 13%;             --muted-foreground: 142 5% 57%;
    --accent: 133 44% 58%;            --accent-foreground: 240 10% 18%;
    --destructive: 3 92% 71%;         --destructive-foreground: 231 12% 12%;
    --border: 200 7% 18%;             --input: 200 7% 25%;
    --ring: 136 46% 66%;
    --success: 136 54% 61%; --warning: 36 87% 62%; --serious: 19 93% 68%;
    --chart-1: 140 55% 38%;  --chart-2: 219 62% 57%;  --chart-3: 38 100% 35%;
    --chart-4: 269 45% 59%;  --chart-5: 353 50% 56%;  --chart-6: 186 100% 33%;
    --chart-7: 72 97% 28%;
  }
}
```

`--accent` is the brand green and `--primary` is Green Ink. They are not
interchangeable. In shadcn, `--primary` is what buttons and links wear, so it has to
be the readable one. The brand green lives in `--accent`, used as a fill, with
`--accent-foreground` (dark charcoal) as its text.

**Tailwind config:** map `success`, `warning`, `serious` and `chart-1..7` to the
variables; fontFamily `display` / `sans` / `arabic` / `mono`; borderRadius sm 6 / md 10
/ lg 14; spacing stays on the 4px scale.

---

## 11 — Assets & what's still missing

### Available

Horizontal lockup (light / night / charcoal), face mark (light / night / green),
headshot, LinkedIn QR — all PNG.

### Gaps — stated plainly

**There is no vector logo.** Everything is raster. Fine on screen, but a printer,
signmaker or embroiderer will ask for SVG or EPS and cannot proceed without it. This
is the most valuable thing to commission next. **Do not trace, redraw or regenerate
the mark** — say it is missing.

| Missing | Bites when | Priority |
|---|---|---|
| Vector logo (SVG + EPS, transparent) | Any print, signage, merchandise, large-format | **High** |
| Icon set — one family, one stroke weight | The first dashboard. Mixed icon sets are the fastest way to look unfinished. | **High** |
| Motion scale — durations and easing | Transitions arrive ad hoc; each screen animates differently | Medium |
| Hijri date handling | Any Saudi-facing product showing dates or expiries | Medium |
| Bilingual glossary — fixed Arabic for recurring business terms | Two translators render "data room" two different ways | Medium |
| Photography direction | The first time someone else sources an image | Low |
| Email & document templates | Proposals and decks drift off-system | Low |

Where a rule is not specified here — no icon set, no motion scale — pick a sensible
default (Lucide icons; 150–200ms ease-out), **say that you chose it**, and do not
present it as part of the system.

---

*Altorabi brand book v3.0. Supersedes Brand System v1 and Product System v2, which it
consolidates. Colour values generated in OKLCH and validated for contrast and
colourblind separation in both themes; every ratio printed here was measured.*
