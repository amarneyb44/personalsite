# Warm Academia Design System — consolidated reference

Single-file version of the design system for Alli's personal website. Use this for any HTML design in this Project. Sections below are the original files, verbatim, with their paths as headings.

## readme.md

# Warm Academia Design System

A design system for a **personal academic website** of a Research Assistant in Economics preparing PhD applications (interests: applied microeconomics, household finance, health economics). Direction: *dark academia, but warmer and lighter* — cream paper, brown ink, earthy accents, classical serifs with a modern, youthful editorial edge.

**Sources:** none. No codebase, Figma, logo, or existing site was provided — everything here is authored from the written brief. The name "Jordan Ellis", "Whitlock College", "Center for Household Economics" and all papers/posts are **fictional placeholders**.

**Products / surfaces:** one — the personal website (Home, Research, CV, Writing + post, About/Contact). See `ui_kits/website/`.

---

## Content fundamentals

- **Voice:** first person, curious, precise, a little warm. Written like a thoughtful grad-school applicant, not a brand. "I study how households borrow, save, and stay healthy." Never "passionate", "leveraging", "thought leader".
- **Person:** *I* for the author; *you* sparingly (contact copy: "Always happy to hear about research").
- **Casing:** sentence case for headings, buttons and nav ("Download CV", "Working papers"). Mono eyebrows are UPPERCASE via CSS, but written in sentence case in source.
- **Headlines:** one italic accent word in terracotta — "Papers & *works in progress*", "Notes from the *data*". One per heading, max.
- **Numbers & specifics:** concrete over vague — "180,000 households", "1.8 percentage points", "2M-record panel". Dates as "Sep 2026", ranges with em-dash "2024 — present".
- **Academic conventions:** "with M. Okafor" for coauthors, venue in italics, status labels ("Working paper", "Work in progress", "Senior thesis"), footnotes for asides.
- **Emoji:** never. Unicode typographic glyphs instead (§ ¶ † ❦ → ↗ ←).
- **Length:** abstracts ≤ 3 sentences on list views; leads ≤ 2 sentences.
- **Humor:** light and human in About only ("too many sourdough experiments").

## Visual foundations

- **Color:** warm paper neutrals (`--paper-50…400`) for ground, warm brown inks (`--ink-900…400`) for text — never pure black/white. Primary accent **terracotta** `#A34A2A` (links, primary CTA, § numbers, italic accent word). Supporting earth accents: **olive** (health / success), **ochre** (applied micro / in-progress / highlight), **oxblood** (errors, "new"). **Walnut** `#3B2A20` is the only dark surface — footer band, tooltips, occasional quote band; the site is light overall.
- **Topic color convention:** household finance = terracotta, health = olive, applied micro/methods = ochre.
- **Type:** *Instrument Serif* (display, 400 only, roman + italic, tight −0.015em) gives the youthful editorial feel; *Newsreader* (text, optical sizes) for body/UI at 18/1.62, 66ch measure; *IBM Plex Mono* for eyebrows, dates, metadata, links-as-actions (uppercase, +0.06–0.14em). Headings are never bold.
- **Spacing:** 4px base; 24 (list rows), 48 (block gaps), 96 (between sections). Container 1120px, narrow 720px for essays. Lists use a **left gutter** for year/date (64–150px) — a CV/ledger layout.
- **Backgrounds:** flat cream paper. No gradients, no textures, no full-bleed photos by default. The only pattern is the diagonal hatch used for image placeholders.
- **Structure via rules, not boxes:** hairline (`--border-subtle`) between list items; **double rule** under page titles; ornament rule (§ or ❦) to end an essay. Cards are used sparingly (featured items, contact form, writing grid).
- **Cards:** `--bg-surface` (lighter than page), 1px `--border-subtle`, radius 8px, `--shadow-sm`. Interactive cards lift 2px with `--shadow-md`.
- **Corner radii:** small and bookish — 4px buttons/inputs, 8px cards, 14px dialogs, pill only for tags.
- **Shadows:** warm brown-tinted, low and soft; three steps + inset for inputs. Most surfaces are flat.
- **Borders:** 1px everywhere. Strong ink border for secondary buttons and double rules.
- **Hover:** links darken terracotta and the underline goes solid; nav links draw a terracotta underline from the left; text-only items turn terracotta; arrows (→) nudge 2–3px right; fills go one step darker (`--accent-hover`) or to `--bg-sunken` for outline/ghost.
- **Press:** 1px downward translate. No scale/shrink.
- **Focus:** 2px terracotta outline (offset 2) or 3px `--focus-ring` halo on inputs.
- **Active state:** italic + terracotta underline (nav, tabs). Selected chips fill with ink.
- **Motion:** quiet. 120ms colors, 200ms underline/lift/arrow, 360ms page fade-up (6px). Easing `cubic-bezier(.2,.7,.2,1)`. No bounce, no parallax.
- **Transparency & blur:** only the sticky header (88% paper + 8px blur) and dialog scrim (walnut 45% + 3px blur).
- **Imagery:** warm, natural light, slight film grain; portraits 4:5, desk/library still lifes, charts on paper backgrounds. Never cool/blue-toned. Until real photos exist, use the hatched placeholder.
- **Figures/charts (for research):** plot on `--paper-50`, ink axes, series in terracotta → olive → ochre → oxblood.
- **Layout rules:** sticky 68px header; content is centered in a container; the walnut footer closes every page.

## Iconography

- **No icon font or SVG set.** The brand leans on typography: unicode glyphs serve as icons — **→** internal link / next, **↗** external link or download, **←** back, **↑ ↓** expand/collapse abstract, **§** section numbers & ornament, **❦** end-of-essay, **†/superscript numerals** footnotes, **×** close, **▾** select caret, **✉** contact.
- **Emoji:** never.
- **If a real icon set is ever needed** (e.g. social icons in the footer), use **Lucide** from CDN (`https://unpkg.com/lucide-static`) at 1.5px stroke, 18px, `currentColor` — flagged as a substitution, not part of the current design.
- **Logo:** none provided. The wordmark is the name set in Instrument Serif with a mono caption ("Economics"). Do not invent a monogram or mark.

## Fonts

Loaded from Google Fonts via `tokens/fonts.css` (`@import`): Instrument Serif, Newsreader, IBM Plex Mono. **No font binaries were provided** — these are chosen, not substituted; self-host woff2 files later if desired.

---

## Index

- `styles.css` — entry point (imports only)
- `tokens/` — `fonts.css`, `colors.css`, `typography.css`, `spacing.css` (spacing, container, radii), `effects.css` (borders, shadows, motion), `base.css` (element defaults)
- `guidelines/` — foundation specimen cards (Colors, Type, Spacing, Brand)
- `components/` — React primitives (below), each with `.jsx`, `.d.ts`, `.prompt.md` and one card per directory
- `ui_kits/website/` — personal website click-through (see its README)
- `thumbnail.html`, `SKILL.md`

## Components

- **core/** — Button, Tag, Card, Divider
- **navigation/** — NavBar, Tabs
- **forms/** — Input (incl. multiline textarea), Select
- **content/** — SectionHeader, PaperItem, CVEntry, PostCard
- **feedback/** — Dialog, Tooltip (+ Footnote)

### Intentional additions
No source inventory existed. The standard set was trimmed to what a personal academic site needs (no Checkbox/Radio/Switch/Toast/Badge), and domain components were added: **PaperItem** (research list), **CVEntry** (CV rows), **PostCard** (writing), **SectionHeader** (§-numbered openers), **Footnote** (scholarly inline notes).

## Tokens (styles.css + tokens/*.css)

```css
/* ---- tokens/fonts.css ---- */
/* Google Fonts: Instrument Serif (display), Newsreader (text), IBM Plex Mono (labels) */
@import url('https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Newsreader:ital,opsz,wght@0,6..72,300..700;1,6..72,300..700&family=IBM+Plex+Mono:ital,wght@0,400;0,500;1,400&display=swap');

/* ---- tokens/colors.css ---- */
:root{
/* Paper — warm neutrals (backgrounds) */
--paper-50:#FBF7F0;--paper-100:#F5EEE2;--paper-200:#EDE3D2;--paper-300:#E0D2BB;--paper-400:#CBB897;
/* Ink — warm browns (text) */
--ink-900:#2A1F18;--ink-700:#4A3A2E;--ink-500:#6F5D4B;--ink-400:#9A8770;
/* Walnut — dark surfaces (used sparingly: footer, quote bands) */
--walnut-700:#4A372B;--walnut-800:#3B2A20;--walnut-900:#2A1E17;
/* Earth accents */
--terracotta-100:#F3DDD0;--terracotta-500:#BF6440;--terracotta-600:#A34A2A;--terracotta-700:#843A20;
--olive-100:#E4E6CF;--olive-500:#7A8547;--olive-600:#5C6634;--olive-700:#474F27;
--ochre-100:#F3E4C4;--ochre-500:#C08A2E;--ochre-600:#9C6C1C;--ochre-700:#7A5314;
--oxblood-100:#EFD6D1;--oxblood-600:#8A3530;--oxblood-700:#6E2A26;

/* Semantic — surfaces */
--bg-page:var(--paper-100);--bg-surface:var(--paper-50);--bg-sunken:var(--paper-200);--bg-inverse:var(--walnut-800);--bg-overlay:rgba(42,30,23,.45);
/* Semantic — text */
--text-primary:var(--ink-900);--text-secondary:var(--ink-700);--text-muted:var(--ink-500);--text-disabled:var(--ink-400);--text-inverse:var(--paper-100);--text-inverse-muted:var(--paper-300);--text-accent:var(--terracotta-600);
/* Semantic — lines */
--border-subtle:var(--paper-300);--border-default:var(--paper-400);--border-strong:var(--ink-700);
/* Semantic — accent & state */
--accent:var(--terracotta-600);--accent-hover:var(--terracotta-700);--accent-soft:var(--terracotta-100);--accent-contrast:var(--paper-50);
--link:var(--terracotta-600);--link-hover:var(--terracotta-700);
--highlight:var(--ochre-100);--focus-ring:rgba(163,74,42,.35);
--status-success:var(--olive-600);--status-success-soft:var(--olive-100);
--status-warning:var(--ochre-600);--status-warning-soft:var(--ochre-100);
--status-danger:var(--oxblood-600);--status-danger-soft:var(--oxblood-100);
}

/* ---- tokens/typography.css ---- */
:root{
--font-display:'Instrument Serif','Cormorant Garamond',Georgia,serif;
--font-text:'Newsreader','EB Garamond',Georgia,serif;
--font-mono:'IBM Plex Mono',ui-monospace,Menlo,monospace;
/* Scale (px) */
--text-display:80px;--text-h1:56px;--text-h2:38px;--text-h3:27px;--text-h4:21px;
--text-lead:22px;--text-body:18px;--text-small:15.5px;--text-caption:13.5px;--text-label:11.5px;
/* Line heights */
--lh-display:1.0; /* @kind other */
--lh-heading:1.12; /* @kind other */
--lh-snug:1.35; /* @kind other */
--lh-body:1.62; /* @kind other */

/* Weights */
--fw-light:300; /* @kind font */
--fw-regular:400; /* @kind font */
--fw-medium:500; /* @kind font */
--fw-semibold:600; /* @kind font */

/* Tracking */
--tracking-display:-0.015em; /* @kind font */
--tracking-label:0.14em; /* @kind font */
--tracking-body:0; /* @kind font */
--measure:66ch; /* @kind spacing */
}

/* ---- tokens/spacing.css ---- */
:root{
--space-0:0;--space-1:4px;--space-2:8px;--space-3:12px;--space-4:16px;--space-5:24px;--space-6:32px;--space-7:48px;--space-8:64px;--space-9:96px;--space-10:128px;
--container:1120px;--container-narrow:720px;--gutter:clamp(20px,5vw,48px); /* @kind spacing */

--radius-xs:2px;--radius-sm:4px;--radius-md:8px;--radius-lg:14px;--radius-pill:999px;
}

/* ---- tokens/effects.css ---- */
:root{
--border-width:1px; /* @kind other */
--rule:1px solid var(--border-subtle); /* @kind other */
--rule-strong:1px solid var(--border-strong); /* @kind other */

--shadow-sm:0 1px 0 rgba(42,31,24,.05),0 1px 2px rgba(42,31,24,.07);
--shadow-md:0 1px 2px rgba(42,31,24,.06),0 10px 24px -10px rgba(74,48,30,.22);
--shadow-lg:0 2px 6px rgba(42,31,24,.08),0 24px 48px -16px rgba(74,48,30,.32);
--shadow-inset:inset 0 1px 2px rgba(42,31,24,.07);
--ease-out:cubic-bezier(.2,.7,.2,1); /* @kind other */
--ease-in-out:cubic-bezier(.6,0,.3,1); /* @kind other */
--dur-fast:120ms; /* @kind other */
--dur-base:200ms; /* @kind other */
--dur-slow:360ms; /* @kind other */
}

/* ---- tokens/base.css ---- */
html{background:var(--bg-page);color:var(--text-primary);-webkit-font-smoothing:antialiased;text-rendering:optimizeLegibility}
body{margin:0;font-family:var(--font-text);font-size:var(--text-body);line-height:var(--lh-body);font-optical-sizing:auto}
a{color:var(--link);text-decoration:underline;text-decoration-thickness:1px;text-underline-offset:3px;text-decoration-color:color-mix(in srgb,var(--link) 40%,transparent);transition:color var(--dur-fast) var(--ease-out),text-decoration-color var(--dur-fast) var(--ease-out)}
a:hover{color:var(--link-hover);text-decoration-color:currentColor}
::selection{background:var(--highlight);color:var(--ink-900)}
:focus-visible{outline:2px solid var(--accent);outline-offset:2px}
h1,h2,h3{font-family:var(--font-display);font-weight:400;letter-spacing:var(--tracking-display);line-height:var(--lh-heading);text-wrap:balance;margin:0}
p{text-wrap:pretty}

```

## Guidelines (text of guidelines/*.html)

- **colors-earth:**  terracotta-100 terracotta-500 terracotta-600 terracotta-700 olive-100 olive-500 olive-600 olive-700 ochre-100 ochre-500 ochre-600 ochre-700 oxblood-100 oxblood-600 oxblood-700 
- **colors-ink:**  ink-900 #2A1F18 ink-700 #4A3A2E ink-500 #6F5D4B ink-400 #9A8770 walnut-700 #4A372B walnut-800 #3B2A20 walnut-900 #2A1E17 
- **colors-paper:**  paper-50 #FBF7F0 paper-100 #F5EEE2 paper-200 #EDE3D2 paper-300 #E0D2BB paper-400 #CBB897 
- **colors-semantic:**  --bg-page Page background --bg-surface Cards, inputs --bg-sunken Hover fills, code --bg-inverse Footer, quote band --text-primary Headings, body --text-secondary Meta, abstracts --text-muted Dates, captions --accent Links, primary CTA --highlight Selection, marker --status-success Published / accepted --status-warning Work in progress --status-danger Errors 
- **imagery:**  PORTRAIT 4:5 · warm light LIBRARY / DESK still life, film grain FIGURE chart on paper bg 
- **motion:**  FAST · 120MS color, bg on hover BASE · 200MS underline draw, lift, arrow nudge SLOW · 360MS page fade-in EASE-OUT cubic-bezier(.2,.7,.2,1); no bounce 
- **radii:**  xs · 2px sm · 4px md · 8px lg · 14px pill · 999px sm: buttons, inputs · md: cards · lg: dialogs · pill: tags only 
- **rules:**  hairline double / ledger ornament § glyphs § ¶ † ❦ → ↗ 
- **shadows:**  shadow-sm shadow-md shadow-lg shadow-inset 
- **spacing-layout:**  DATE GUTTER 64–150px Title in the text column TEXT ≤ 66CH · SECTIONS 96PX APART · LIST ROWS 24PX PADDING + HAIRLINE 
- **spacing:**  1·4 2·8 3·12 4·16 5·24 6·32 7·48 8·64 9·96 10·128 
- **type-body:**  I study how families borrow, save, and cope with health shocks — using administrative data and a stubborn interest in why . Body text is set at 18px on a 1.62 line-height, capped at 66ch. Semibold for emphasis in lists; italic for venues and asides. NEWSREADER 300–700 · OPTICAL SIZING · 18/1.62 
- **type-display:**  Households, health & money INSTRUMENT SERIF 400 · ROMAN + ITALIC · −0.015EM · LH 1.0–1.12 
- **type-mono:**  § 01  Research 2024 — present PDF ↗ reg y x, cluster(state) IBM PLEX MONO 400/500 · UPPERCASE LABELS +0.14EM 
- **type-scale:**  display · 80 Grad school h1 · 56 Research h2 · 38 Working papers h3 · 27 Buy Now, Pay Later lead · 22 A lead paragraph sets up a page. body · 18 Body copy for essays and abstracts. small · 15.5 Author lines, CV details label · 11.5 EYEBROW LABEL 
- **voice:**  “I’m interested in the small financial decisions that turn into big health outcomes .” DO “Right now I’m working on…” · sentence case · plain verbs DON’T “Passionate thought leader leveraging data” · Title Case Everything · emoji 
- **wordmark:**  Jordan Ellis Economics PLACEHOLDER NAME · INSTRUMENT SERIF + MONO CAPTION · NO GRAPHIC MARK 

## Components — usage and types

### CVEntry

CVEntry — a row in the CV (education, positions, awards, skills). Group under a SectionHeader size="sm".

```jsx
<CVEntry period="2024 — present" title="Research Assistant" org="Federal Reserve Bank" location="Chicago"
  bullets={['Built panel of 2M credit records','Cleaned and linked Medicaid claims']} />
```

```ts
import * as React from 'react';
/** CV line item: mono period gutter + role, italic org, detail/bullets. */
export interface CVEntryProps {
  /** e.g. "2024 — present" */
  period?: string;
  title: React.ReactNode;
  org?: string;
  location?: string;
  detail?: React.ReactNode;
  bullets?: React.ReactNode[];
  style?: React.CSSProperties;
}
export declare function CVEntry(props: CVEntryProps): JSX.Element;

```

### PaperItem

PaperItem — one entry in the research list; stack several (each draws its own top hairline).

```jsx
<PaperItem year="2026" status="Working paper" title="Buy Now, Pay Later and Household Liquidity"
  authors="with M. Okafor" tags={[{label:'Household finance',tone:'terracotta'}]}
  abstract="…" links={[{label:'PDF',href:'#'},{label:'Slides'}]} onCite={() => setCiteOpen(true)} />
```

```ts
import * as React from 'react';
export interface PaperLink { label: string; href?: string; }
/**
 * A research paper row: year gutter, status + field tags, display-serif title, authors, collapsible abstract, mono links.
 * @startingPoint section="Content" subtitle="Research paper list entry with abstract toggle" viewport="700x300"
 */
export interface PaperItemProps {
  title: React.ReactNode;
  /** e.g. "with A. Coauthor" */
  authors?: React.ReactNode;
  /** e.g. "Working paper", "Work in progress", "Senior thesis" */
  status?: string;
  /** @default "ochre" */
  statusTone?: 'neutral' | 'terracotta' | 'olive' | 'ochre' | 'oxblood';
  venue?: string;
  year?: string | number;
  abstract?: React.ReactNode;
  links?: PaperLink[];
  tags?: (string | { label: string; tone?: string })[];
  defaultOpen?: boolean;
  /** Shows a "Cite" link */
  onCite?: () => void;
  style?: React.CSSProperties;
}
export declare function PaperItem(props: PaperItemProps): JSX.Element;

```

### PostCard

PostCard — an essay/note teaser; `row` for the Writing index, `card` for a 2–3 up grid on Home.

```jsx
<PostCard date="Sep 2026" title="What I learned cleaning 40 years of CPS data" excerpt="…" readingTime="7 min" tag="Methods" tagTone="ochre" />
<PostCard layout="card" … />
```

```ts
import * as React from 'react';
/**
 * Blog / notes entry. `row` = list line with date gutter; `card` = paper card for grids.
 * @startingPoint section="Content" subtitle="Writing/notes entry, row or card" viewport="700x260"
 */
export interface PostCardProps {
  date?: string;
  title: React.ReactNode;
  excerpt?: React.ReactNode;
  /** e.g. "6 min read" */
  readingTime?: string;
  tag?: string;
  /** @default "neutral" */
  tagTone?: 'neutral' | 'terracotta' | 'olive' | 'ochre' | 'oxblood';
  /** @default "row" */
  layout?: 'row' | 'card';
  onClick?: () => void;
  href?: string;
  style?: React.CSSProperties;
}
export declare function PostCard(props: PostCardProps): JSX.Element;

```

### SectionHeader

SectionHeader — opens every page section; the "§ 01" numbering is a core motif.

```jsx
<SectionHeader number="01" eyebrow="Research" title={<>Papers & <em>works in progress</em></>}
  description="Applied micro questions about how households borrow, save, and stay healthy." />
```

```ts
import * as React from 'react';
/** Section opener: "§ 01" mono eyebrow + display-serif title + optional lead. */
export interface SectionHeaderProps {
  /** Rendered as "§ {number}" in terracotta */
  number?: string;
  eyebrow?: string;
  /** Can include <em> for an italic accent word */
  title: React.ReactNode;
  description?: React.ReactNode;
  /** @default "left" */
  align?: 'left' | 'center';
  /** @default "md" */
  size?: 'sm' | 'md' | 'lg';
  /** Right-aligned node on the title row (e.g. "All papers →") */
  action?: React.ReactNode;
  style?: React.CSSProperties;
}
export declare function SectionHeader(props: SectionHeaderProps): JSX.Element;

```

### Button

Button — the site's call-to-action; use primary once per view (e.g. "Download CV"), secondary/ghost for everything else.

```jsx
<Button iconRight="→">Read the paper</Button>
<Button variant="secondary" href="/cv.pdf" iconRight="↗">Download CV</Button>
<Button variant="ghost" size="sm">Cite</Button>
```

- `variant`: primary (terracotta) · secondary (ink outline) · ghost (terracotta text) · inverse (on walnut surfaces)
- `size`: sm 34px · md 42px · lg 52px
- Arrows are unicode (→ internal, ↗ external) passed as `iconRight`.

```ts
import * as React from 'react';
/**
 * Primary action control. Renders an <a> when `href` is set.
 * @startingPoint section="Core" subtitle="Primary, secondary, ghost & inverse buttons" viewport="700x260"
 */
export interface ButtonProps {
  /** @default "primary" */
  variant?: 'primary' | 'secondary' | 'ghost' | 'inverse';
  /** @default "md" */
  size?: 'sm' | 'md' | 'lg';
  disabled?: boolean;
  href?: string;
  iconLeft?: React.ReactNode;
  /** Nudges right on hover — use for "→" / "↗" */
  iconRight?: React.ReactNode;
  fullWidth?: boolean;
  type?: 'button' | 'submit' | 'reset';
  onClick?: (e: React.MouseEvent) => void;
  style?: React.CSSProperties;
  children?: React.ReactNode;
}
export declare function Button(props: ButtonProps): JSX.Element;

```

### Card

Card — a sheet of paper on the page; use for grouped content (featured paper, contact box). Prefer plain rules over cards for lists.

```jsx
<Card padding="lg"><h3>Featured</h3>…</Card>
<Card tone="sunken" interactive onClick={open}>…</Card>
<Card tone="inverse">Quote band</Card>
```

```ts
import * as React from 'react';
/** Paper container. Hairline border + faint warm shadow; lifts 2px when interactive. */
export interface CardProps {
  /** @default "surface" */
  tone?: 'surface' | 'sunken' | 'inverse' | 'plain';
  /** @default "md" */
  padding?: 'none' | 'sm' | 'md' | 'lg';
  interactive?: boolean;
  onClick?: () => void;
  style?: React.CSSProperties;
  children?: React.ReactNode;
}
export declare function Card(props: CardProps): JSX.Element;

```

### Divider

Divider — rules do the structural work instead of boxes; hairline between list items, double under page titles, ornament to close an essay.

```jsx
<Divider />
<Divider variant="double" />
<Divider variant="ornament" glyph="❦" />
<Divider variant="label" label="Earlier" />
```

```ts
import * as React from 'react';
/** Horizontal rule — hairline, double (ledger), ornament (centered glyph) or label. */
export interface DividerProps {
  /** @default "hairline" */
  variant?: 'hairline' | 'double' | 'ornament' | 'label';
  /** Ornament glyph. @default "§" */
  glyph?: string;
  label?: string;
  /** Vertical margin (CSS length). @default "var(--space-6)" */
  spacing?: string;
  style?: React.CSSProperties;
}
export declare function Divider(props: DividerProps): JSX.Element;

```

### Tag

Tag — small uppercase mono pill for research fields, paper status and topics; clickable + `selected` makes it a filter chip.

```jsx
<Tag tone="terracotta">Household Finance</Tag>
<Tag tone="olive">Health</Tag>
<Tag tone="ochre" size="sm">Work in progress</Tag>
<Tag variant="outline" selected={active} onClick={toggle}>Applied Micro</Tag>
```

Convention: terracotta = household finance, olive = health, ochre = applied micro / methods, oxblood = status "new".

```ts
import * as React from 'react';
/** Small uppercase mono label for research fields, paper status, post topics. */
export interface TagProps {
  /** @default "neutral" */
  tone?: 'neutral' | 'terracotta' | 'olive' | 'ochre' | 'oxblood';
  /** @default "soft" */
  variant?: 'soft' | 'outline';
  /** @default "md" */
  size?: 'sm' | 'md';
  /** Filled ink — for active filter chips */
  selected?: boolean;
  onClick?: () => void;
  style?: React.CSSProperties;
  children?: React.ReactNode;
}
export declare function Tag(props: TagProps): JSX.Element;

```

### Dialog

Dialog — modal for short tasks: BibTeX citation, contact confirmation. Keep content brief.

```jsx
<Dialog open={open} onClose={() => setOpen(false)} eyebrow="Cite" title="BibTeX"
  footer={<Button size="sm" onClick={copy}>Copy</Button>}>
  <pre>…</pre>
</Dialog>
```

```ts
import * as React from 'react';
/** Modal sheet over a blurred walnut scrim. Esc / scrim click closes. */
export interface DialogProps {
  open: boolean;
  onClose?: () => void;
  title: React.ReactNode;
  eyebrow?: string;
  children?: React.ReactNode;
  footer?: React.ReactNode;
  /** @default 560 */
  width?: number;
}
export declare function Dialog(props: DialogProps): JSX.Element | null;

```

### Tooltip

Tooltip — brief clarifications on hover; `Footnote` is the scholarly variant for inline notes in essays.

```jsx
<Tooltip content="Current Population Survey"><abbr>CPS</abbr></Tooltip>
<p>Delinquency rose sharply<Footnote n={1}>Measured as 60+ days past due.</Footnote>.</p>
```

```ts
import * as React from 'react';
/** Walnut tooltip that fades + rises on hover/focus. Also exports Footnote (superscript that reveals its note). */
export interface TooltipProps {
  content: React.ReactNode;
  children?: React.ReactNode;
  /** @default "top" */
  placement?: 'top' | 'bottom';
  style?: React.CSSProperties;
}
export declare function Tooltip(props: TooltipProps): JSX.Element;
export interface FootnoteProps { n: number | string; children?: React.ReactNode; }
export declare function Footnote(props: FootnoteProps): JSX.Element;

```

### Input

Input — single- or multi-line text field for the contact form or a search box.

```jsx
<Input label="Your email" placeholder="name@university.edu" />
<Input label="Message" multiline rows={5} hint="I usually reply within a few days." />
<Input label="Email" error="That doesn't look like an email." />
```

```ts
import * as React from 'react';
/** Text field / textarea with mono label, italic hint, focus ring. */
export interface InputProps {
  label?: string;
  hint?: string;
  /** Replaces hint, turns border oxblood */
  error?: string;
  /** Render as <textarea> */
  multiline?: boolean;
  /** @default 4 */
  rows?: number;
  value?: string;
  defaultValue?: string;
  onChange?: (value: string, e: React.ChangeEvent) => void;
  placeholder?: string;
  /** @default "text" */
  type?: string;
  disabled?: boolean;
  name?: string;
  style?: React.CSSProperties;
}
export declare function Input(props: InputProps): JSX.Element;

```

### Select

Select — native dropdown styled like Input; for short fixed choices (contact reason, sort order).

```jsx
<Select label="Reason" options={['Research question','Collaboration','Just saying hi']} />
```

```ts
import * as React from 'react';
export interface SelectOption { value: string; label: string; }
/** Native select styled to match Input. */
export interface SelectProps {
  label?: string;
  options?: (string | SelectOption)[];
  value?: string;
  defaultValue?: string;
  onChange?: (value: string, e: React.ChangeEvent) => void;
  hint?: string;
  disabled?: boolean;
  style?: React.CSSProperties;
}
export declare function Select(props: SelectProps): JSX.Element;

```

### NavBar

NavBar — the persistent site header; one per page.

```jsx
<NavBar brand="Jordan Ellis" subtitle="Economics"
  items={[{id:'research',label:'Research'},{id:'cv',label:'CV'},{id:'writing',label:'Writing'},{id:'about',label:'About'}]}
  active={page} onSelect={setPage}
  right={<Button size="sm" variant="secondary" iconRight="↗">CV</Button>} />
```

Translucent paper background with 8px blur when sticky.

```ts
import * as React from 'react';
export interface NavItem { id: string; label: string; href?: string; }
/**
 * Site header: display-serif name on the left, text links on the right. Active link is italic with a terracotta underline.
 * @startingPoint section="Navigation" subtitle="Sticky site header with name + links" viewport="1120x90"
 */
export interface NavBarProps {
  brand?: string;
  /** Mono caption after the name, e.g. "Economics" */
  subtitle?: string;
  items?: NavItem[];
  active?: string;
  onSelect?: (id: string) => void;
  onBrandClick?: () => void;
  /** Extra node at the end of the nav (e.g. a CV button) */
  right?: React.ReactNode;
  /** @default true */
  sticky?: boolean;
  style?: React.CSSProperties;
}
export declare function NavBar(props: NavBarProps): JSX.Element;

```

### Tabs

Tabs — underline tabs over a hairline; active tab goes italic with a terracotta rule. Counts render as zero-padded mono.

```jsx
<Tabs value={tab} onChange={setTab}
  items={[{id:'wp',label:'Working papers',count:2},{id:'wip',label:'In progress',count:3},{id:'ra',label:'RA projects'}]} />
```

```ts
import * as React from 'react';
export interface TabItem { id: string; label: string; count?: number; }
/** Underline tabs for switching sections of one page (e.g. Working papers / In progress / Teaching). */
export interface TabsProps {
  items?: TabItem[];
  value?: string;
  onChange?: (id: string) => void;
  style?: React.CSSProperties;
}
export declare function Tabs(props: TabsProps): JSX.Element;

```

## Components — source (JSX)

### components/content/CVEntry.jsx

```jsx
import React from 'react';

export function CVEntry({ period, title, org, location, detail, bullets=[], style }) {
  return (
    <div style={{ display:'grid', gridTemplateColumns:'150px minmax(0,1fr)', gap:'var(--space-5)', padding:'var(--space-4) 0', ...style }}>
      <div style={{ fontFamily:'var(--font-mono)', fontSize:12.5, letterSpacing:'0.02em', color:'var(--text-muted)', paddingTop:4 }}>{period}</div>
      <div style={{ minWidth:0 }}>
        <div style={{ fontSize:'var(--text-body)', fontWeight:500, color:'var(--text-primary)', lineHeight:1.4 }}>{title}</div>
        {(org || location) && <div style={{ fontSize:'var(--text-small)', color:'var(--text-secondary)', fontStyle:'italic' }}>{org}{org && location ? ', ' : ''}{location}</div>}
        {detail && <p style={{ margin:'6px 0 0', fontSize:'var(--text-small)', color:'var(--text-secondary)', lineHeight:1.55, textWrap:'pretty' }}>{detail}</p>}
        {bullets.length > 0 && <ul style={{ margin:'6px 0 0', paddingLeft:18, fontSize:'var(--text-small)', color:'var(--text-secondary)', lineHeight:1.55 }}>
          {bullets.map((b, i) => <li key={i} style={{ marginBottom:2 }}>{b}</li>)}
        </ul>}
      </div>
    </div>
  );
}

```

### components/content/PaperItem.jsx

```jsx
import React, { useState } from 'react';
import { Tag } from '../core/Tag.jsx';

function MiniLink({ href='#', children, onClick }) {
  const [h, setH] = useState(false);
  return <a href={href} onClick={onClick} onMouseEnter={() => setH(true)} onMouseLeave={() => setH(false)}
    style={{ fontFamily:'var(--font-mono)', fontSize:12, letterSpacing:'0.06em', textTransform:'uppercase', color: h ? 'var(--link-hover)' : 'var(--link)', textDecoration:'none', borderBottom:`1px solid ${h ? 'currentColor' : 'transparent'}`, cursor:'pointer' }}>{children}</a>;
}

export function PaperItem({ title, authors, status, statusTone='ochre', venue, year, abstract, links=[], tags=[], defaultOpen=false, onCite, style }) {
  const [open, setOpen] = useState(defaultOpen);
  return (
    <article style={{ display:'grid', gridTemplateColumns:'64px minmax(0,1fr)', gap:'var(--space-5)', padding:'var(--space-5) 0', borderTop:'1px solid var(--border-subtle)', ...style }}>
      <div style={{ fontFamily:'var(--font-mono)', fontSize:13, color:'var(--text-muted)', paddingTop:6 }}>{year}</div>
      <div style={{ display:'flex', flexDirection:'column', gap:10, minWidth:0 }}>
        {(status || tags.length > 0) && <div style={{ display:'flex', gap:8, flexWrap:'wrap' }}>
          {status && <Tag tone={statusTone} size="sm">{status}</Tag>}
          {tags.map((t) => <Tag key={t.label || t} tone={t.tone || 'neutral'} size="sm" variant="outline">{t.label || t}</Tag>)}
        </div>}
        <h3 style={{ margin:0, fontFamily:'var(--font-display)', fontWeight:400, fontSize:'var(--text-h3)', lineHeight:1.18, letterSpacing:'-0.01em', color:'var(--text-primary)', textWrap:'balance' }}>{title}</h3>
        {(authors || venue) && <div style={{ fontSize:'var(--text-small)', color:'var(--text-secondary)' }}>
          {authors}{authors && venue ? ' · ' : ''}{venue && <em>{venue}</em>}
        </div>}
        {open && abstract && <p style={{ margin:'4px 0 0', fontSize:'var(--text-small)', lineHeight:1.6, color:'var(--text-secondary)', maxWidth:'var(--measure)', textWrap:'pretty' }}>{abstract}</p>}
        <div style={{ display:'flex', gap:'var(--space-5)', flexWrap:'wrap', marginTop:2 }}>
          {abstract && <MiniLink onClick={(e) => { e.preventDefault(); setOpen(!open); }}>{open ? 'Hide abstract ↑' : 'Abstract ↓'}</MiniLink>}
          {links.map((l) => <MiniLink key={l.label} href={l.href}>{l.label} ↗</MiniLink>)}
          {onCite && <MiniLink onClick={(e) => { e.preventDefault(); onCite(); }}>Cite</MiniLink>}
        </div>
      </div>
    </article>
  );
}

```

### components/content/PostCard.jsx

```jsx
import React, { useState } from 'react';
import { Tag } from '../core/Tag.jsx';

export function PostCard({ date, title, excerpt, readingTime, tag, tagTone='neutral', layout='row', onClick, href, style }) {
  const [h, setH] = useState(false);
  const row = layout === 'row';
  return (
    <a href={href || '#'} onClick={(e) => { if (onClick) { e.preventDefault(); onClick(); } }} onMouseEnter={() => setH(true)} onMouseLeave={() => setH(false)}
      style={{ display:'grid', gridTemplateColumns: row ? '120px minmax(0,1fr)' : '1fr', gap: row ? 'var(--space-5)' : 'var(--space-3)', textDecoration:'none', color:'inherit',
        padding: row ? 'var(--space-5) 0' : 'var(--space-5)', borderTop: row ? '1px solid var(--border-subtle)' : 'none',
        background: row ? 'transparent' : 'var(--bg-surface)', border: row ? undefined : '1px solid var(--border-subtle)', borderRadius: row ? 0 : 'var(--radius-md)',
        boxShadow: !row && h ? 'var(--shadow-md)' : 'none', transform: !row && h ? 'translateY(-2px)' : 'none',
        transition:'box-shadow var(--dur-base) var(--ease-out), transform var(--dur-base) var(--ease-out)', ...style }}>
      <div style={{ fontFamily:'var(--font-mono)', fontSize:12.5, color:'var(--text-muted)', paddingTop: row ? 6 : 0, display:'flex', gap:10, alignItems:'center', flexWrap:'wrap' }}>
        {date}{!row && tag && <Tag size="sm" tone={tagTone}>{tag}</Tag>}
      </div>
      <div style={{ display:'flex', flexDirection:'column', gap:6, minWidth:0 }}>
        <h3 style={{ margin:0, fontFamily:'var(--font-display)', fontWeight:400, fontSize:'var(--text-h3)', lineHeight:1.18, color: h ? 'var(--text-accent)' : 'var(--text-primary)', transition:'color var(--dur-fast) var(--ease-out)', textWrap:'balance' }}>{title}</h3>
        {excerpt && <p style={{ margin:0, fontSize:'var(--text-small)', lineHeight:1.55, color:'var(--text-secondary)', textWrap:'pretty' }}>{excerpt}</p>}
        <div style={{ display:'flex', gap:12, alignItems:'center', marginTop:4, fontFamily:'var(--font-mono)', fontSize:11.5, letterSpacing:'0.06em', textTransform:'uppercase', color:'var(--text-muted)' }}>
          {row && tag && <Tag size="sm" tone={tagTone}>{tag}</Tag>}
          {readingTime && <span>{readingTime}</span>}
          <span style={{ color:'var(--text-accent)', transform: h ? 'translateX(3px)' : 'none', transition:'transform var(--dur-base) var(--ease-out)' }}>→</span>
        </div>
      </div>
    </a>
  );
}

```

### components/content/SectionHeader.jsx

```jsx
import React from 'react';

export function SectionHeader({ number, eyebrow, title, description, align='left', size='md', action, style }) {
  const fs = size === 'lg' ? 'var(--text-h1)' : size === 'sm' ? 'var(--text-h3)' : 'var(--text-h2)';
  return (
    <div style={{ display:'flex', flexDirection:'column', gap:'var(--space-3)', textAlign:align, alignItems: align === 'center' ? 'center' : 'stretch', ...style }}>
      {(number || eyebrow) && (
        <div style={{ display:'flex', gap:12, alignItems:'center', justifyContent: align === 'center' ? 'center' : 'flex-start', fontFamily:'var(--font-mono)', fontSize:'var(--text-label)', letterSpacing:'var(--tracking-label)', textTransform:'uppercase', color:'var(--text-muted)' }}>
          {number && <span style={{ color:'var(--text-accent)' }}>§ {number}</span>}
          {eyebrow && <span>{eyebrow}</span>}
        </div>
      )}
      <div style={{ display:'flex', alignItems:'flex-end', justifyContent:'space-between', gap:'var(--space-5)' }}>
        <h2 style={{ fontFamily:'var(--font-display)', fontWeight:400, fontSize:fs, lineHeight:'var(--lh-heading)', letterSpacing:'var(--tracking-display)', margin:0, color:'var(--text-primary)', textWrap:'balance', flex:1 }}>{title}</h2>
        {action}
      </div>
      {description && <p style={{ margin:0, fontSize:'var(--text-lead)', lineHeight:1.5, color:'var(--text-secondary)', maxWidth:'var(--measure)', textWrap:'pretty', marginInline: align === 'center' ? 'auto' : undefined }}>{description}</p>}
    </div>
  );
}

```

### components/core/Button.jsx

```jsx
import React, { useState } from 'react';

const SIZES = { sm:{ h:34, px:14, fs:15 }, md:{ h:42, px:20, fs:16.5 }, lg:{ h:52, px:26, fs:18 } };

export function Button({ variant='primary', size='md', disabled=false, href, iconLeft, iconRight, fullWidth=false, children, onClick, type='button', style, ...rest }) {
  const [hover, setHover] = useState(false);
  const [press, setPress] = useState(false);
  const s = SIZES[size] || SIZES.md;
  const v = {
    primary:{ bg: hover ? 'var(--accent-hover)' : 'var(--accent)', fg:'var(--accent-contrast)', bd:'transparent' },
    secondary:{ bg: hover ? 'var(--bg-sunken)' : 'transparent', fg:'var(--text-primary)', bd:'var(--border-strong)' },
    ghost:{ bg: hover ? 'var(--bg-sunken)' : 'transparent', fg:'var(--text-accent)', bd:'transparent' },
    inverse:{ bg: hover ? 'var(--paper-50)' : 'var(--paper-100)', fg:'var(--ink-900)', bd:'transparent' },
  }[variant] || {};
  const Tag = href ? 'a' : 'button';
  return (
    <Tag href={href} type={href ? undefined : type} disabled={!href && disabled} aria-disabled={disabled || undefined}
      onClick={disabled ? undefined : onClick}
      onMouseEnter={() => setHover(true)} onMouseLeave={() => { setHover(false); setPress(false); }}
      onMouseDown={() => setPress(true)} onMouseUp={() => setPress(false)}
      style={{ display:'inline-flex', alignItems:'center', justifyContent:'center', gap:8, height:s.h, padding:`0 ${s.px}px`,
        width: fullWidth ? '100%' : undefined, boxSizing:'border-box',
        fontFamily:'var(--font-text)', fontSize:s.fs, fontWeight:500, letterSpacing:'0.005em', lineHeight:1, textDecoration:'none', whiteSpace:'nowrap',
        background:v.bg, color:v.fg, border:`1px solid ${v.bd}`, borderRadius:'var(--radius-sm)',
        cursor: disabled ? 'not-allowed' : 'pointer', opacity: disabled ? 0.45 : 1,
        transform: press && !disabled ? 'translateY(1px)' : 'none',
        transition:'background var(--dur-fast) var(--ease-out), transform var(--dur-fast) var(--ease-out)', ...style }} {...rest}>
      {iconLeft && <span style={{ display:'inline-flex' }}>{iconLeft}</span>}
      <span>{children}</span>
      {iconRight && <span style={{ display:'inline-flex', transition:'transform var(--dur-base) var(--ease-out)', transform: hover ? 'translateX(2px)' : 'none' }}>{iconRight}</span>}
    </Tag>
  );
}

```

### components/core/Card.jsx

```jsx
import React, { useState } from 'react';

export function Card({ tone='surface', padding='md', interactive=false, onClick, children, style }) {
  const [hover, setHover] = useState(false);
  const pad = { none:0, sm:'var(--space-4)', md:'var(--space-5)', lg:'var(--space-6)' }[padding];
  const bg = { surface:'var(--bg-surface)', sunken:'var(--bg-sunken)', inverse:'var(--bg-inverse)', plain:'transparent' }[tone];
  const lift = interactive && hover;
  return (
    <div onClick={onClick} onMouseEnter={() => setHover(true)} onMouseLeave={() => setHover(false)}
      style={{ background:bg, color: tone === 'inverse' ? 'var(--text-inverse)' : 'var(--text-primary)', padding:pad,
        border: tone === 'inverse' ? '1px solid transparent' : `1px solid ${lift ? 'var(--border-default)' : 'var(--border-subtle)'}`,
        borderRadius:'var(--radius-md)', boxShadow: lift ? 'var(--shadow-md)' : tone === 'surface' ? 'var(--shadow-sm)' : 'none',
        transform: lift ? 'translateY(-2px)' : 'none', cursor: interactive ? 'pointer' : 'default',
        transition:'box-shadow var(--dur-base) var(--ease-out), transform var(--dur-base) var(--ease-out), border-color var(--dur-base) var(--ease-out)', ...style }}>
      {children}
    </div>
  );
}

```

### components/core/Divider.jsx

```jsx
import React from 'react';

export function Divider({ variant='hairline', glyph='§', label, spacing='var(--space-6)', style }) {
  const line = { flex:1, height:0, borderTop:'1px solid var(--border-default)' };
  const wrap = { margin:`${spacing} 0`, ...style };
  if (variant === 'double') return <div role="separator" style={{ ...wrap, borderTop:'1px solid var(--border-strong)', borderBottom:'1px solid var(--border-strong)', height:3 }}></div>;
  if (variant === 'ornament' || variant === 'label') return (
    <div role="separator" style={{ ...wrap, display:'flex', alignItems:'center', gap:'var(--space-4)' }}>
      <span style={line}></span>
      {variant === 'ornament'
        ? <span style={{ fontFamily:'var(--font-display)', fontSize:22, color:'var(--text-accent)', lineHeight:1 }}>{glyph}</span>
        : <span style={{ fontFamily:'var(--font-mono)', fontSize:'var(--text-label)', letterSpacing:'var(--tracking-label)', textTransform:'uppercase', color:'var(--text-muted)' }}>{label}</span>}
      <span style={line}></span>
    </div>
  );
  return <hr style={{ ...wrap, border:0, borderTop:'1px solid var(--border-subtle)' }} />;
}

```

### components/core/Tag.jsx

```jsx
import React from 'react';

const TONES = {
  neutral:['var(--bg-sunken)','var(--text-secondary)','var(--border-default)'],
  terracotta:['var(--terracotta-100)','var(--terracotta-700)','var(--terracotta-500)'],
  olive:['var(--olive-100)','var(--olive-700)','var(--olive-500)'],
  ochre:['var(--ochre-100)','var(--ochre-700)','var(--ochre-500)'],
  oxblood:['var(--oxblood-100)','var(--oxblood-700)','var(--oxblood-600)'],
};

export function Tag({ tone='neutral', variant='soft', size='md', children, onClick, selected=false, style }) {
  const [bg, fg, bd] = TONES[tone] || TONES.neutral;
  const outline = variant === 'outline' && !selected;
  return (
    <span onClick={onClick} role={onClick ? 'button' : undefined}
      style={{ display:'inline-flex', alignItems:'center', gap:6, height: size === 'sm' ? 22 : 26, padding: size === 'sm' ? '0 8px' : '0 11px',
        fontFamily:'var(--font-mono)', fontSize: size === 'sm' ? 10.5 : 11.5, fontWeight:500, letterSpacing:'0.08em', textTransform:'uppercase', lineHeight:1, whiteSpace:'nowrap',
        background: selected ? 'var(--ink-900)' : outline ? 'transparent' : bg, color: selected ? 'var(--paper-50)' : fg,
        border:`1px solid ${selected ? 'var(--ink-900)' : outline ? bd : 'transparent'}`, borderRadius:'var(--radius-pill)',
        cursor: onClick ? 'pointer' : 'default', transition:'background var(--dur-fast) var(--ease-out)', ...style }}>
      {children}
    </span>
  );
}

```

### components/feedback/Dialog.jsx

```jsx
import React, { useEffect } from 'react';

export function Dialog({ open, onClose, title, eyebrow, children, footer, width=560 }) {
  useEffect(() => {
    if (!open) return;
    const k = (e) => { if (e.key === 'Escape' && onClose) onClose(); };
    window.addEventListener('keydown', k); return () => window.removeEventListener('keydown', k);
  }, [open, onClose]);
  if (!open) return null;
  return (
    <div onClick={onClose} style={{ position:'fixed', inset:0, zIndex:100, background:'var(--bg-overlay)', backdropFilter:'blur(3px)', WebkitBackdropFilter:'blur(3px)', display:'flex', alignItems:'center', justifyContent:'center', padding:'var(--space-5)' }}>
      <div role="dialog" aria-modal="true" onClick={(e) => e.stopPropagation()}
        style={{ width:'100%', maxWidth:width, background:'var(--bg-surface)', border:'1px solid var(--border-subtle)', borderRadius:'var(--radius-lg)', boxShadow:'var(--shadow-lg)', overflow:'hidden' }}>
        <div style={{ display:'flex', alignItems:'flex-start', justifyContent:'space-between', gap:16, padding:'var(--space-5) var(--space-5) var(--space-3)' }}>
          <div>
            {eyebrow && <div style={{ fontFamily:'var(--font-mono)', fontSize:'var(--text-label)', letterSpacing:'var(--tracking-label)', textTransform:'uppercase', color:'var(--text-accent)', marginBottom:6 }}>{eyebrow}</div>}
            <h3 style={{ margin:0, fontFamily:'var(--font-display)', fontWeight:400, fontSize:'var(--text-h3)', lineHeight:1.15, color:'var(--text-primary)' }}>{title}</h3>
          </div>
          <button aria-label="Close" onClick={onClose} style={{ appearance:'none', border:0, background:'none', cursor:'pointer', fontSize:22, lineHeight:1, color:'var(--text-muted)', padding:4 }}>×</button>
        </div>
        <div style={{ padding:'0 var(--space-5) var(--space-5)', fontSize:'var(--text-small)', color:'var(--text-secondary)', lineHeight:1.6 }}>{children}</div>
        {footer && <div style={{ display:'flex', justifyContent:'flex-end', gap:'var(--space-3)', padding:'var(--space-4) var(--space-5)', borderTop:'1px solid var(--border-subtle)', background:'var(--bg-page)' }}>{footer}</div>}
      </div>
    </div>
  );
}

```

### components/feedback/Tooltip.jsx

```jsx
import React, { useState } from 'react';

export function Tooltip({ content, children, placement='top', style }) {
  const [show, setShow] = useState(false);
  const top = placement === 'top';
  return (
    <span onMouseEnter={() => setShow(true)} onMouseLeave={() => setShow(false)} onFocus={() => setShow(true)} onBlur={() => setShow(false)}
      style={{ position:'relative', display:'inline-block', ...style }}>
      {children}
      <span role="tooltip" style={{ position:'absolute', left:'50%', [top ? 'bottom' : 'top']:'calc(100% + 8px)', transform:`translateX(-50%) translateY(${show ? 0 : (top ? 4 : -4)}px)`,
        opacity: show ? 1 : 0, pointerEvents:'none', transition:'opacity var(--dur-base) var(--ease-out), transform var(--dur-base) var(--ease-out)',
        background:'var(--walnut-800)', color:'var(--paper-100)', fontFamily:'var(--font-text)', fontSize:14, fontStyle:'normal', fontWeight:400, lineHeight:1.45,
        padding:'8px 12px', borderRadius:'var(--radius-sm)', boxShadow:'var(--shadow-md)', width:'max-content', maxWidth:280, zIndex:50, textAlign:'left' }}>
        {content}
      </span>
    </span>
  );
}

export function Footnote({ n, children }) {
  return <Tooltip content={children}><sup style={{ fontFamily:'var(--font-mono)', fontSize:'0.62em', color:'var(--text-accent)', cursor:'help', padding:'0 1px' }}>{n}</sup></Tooltip>;
}

```

### components/forms/Input.jsx

```jsx
import React, { useState } from 'react';

export function Input({ label, hint, error, multiline=false, rows=4, value, defaultValue, onChange, placeholder, type='text', disabled=false, name, style }) {
  const [focus, setFocus] = useState(false);
  const El = multiline ? 'textarea' : 'input';
  const bd = error ? 'var(--status-danger)' : focus ? 'var(--accent)' : 'var(--border-default)';
  return (
    <label style={{ display:'flex', flexDirection:'column', gap:8, ...style }}>
      {label && <span style={{ fontFamily:'var(--font-mono)', fontSize:'var(--text-label)', letterSpacing:'var(--tracking-label)', textTransform:'uppercase', color:'var(--text-secondary)' }}>{label}</span>}
      <El name={name} type={multiline ? undefined : type} rows={multiline ? rows : undefined} value={value} defaultValue={defaultValue} placeholder={placeholder} disabled={disabled}
        onChange={(e) => onChange && onChange(e.target.value, e)} onFocus={() => setFocus(true)} onBlur={() => setFocus(false)}
        style={{ fontFamily:'var(--font-text)', fontSize:17, color:'var(--text-primary)', background: disabled ? 'var(--bg-sunken)' : 'var(--bg-surface)',
          border:`1px solid ${bd}`, borderRadius:'var(--radius-sm)', padding: multiline ? '12px 14px' : '0 14px', height: multiline ? undefined : 44,
          boxShadow: focus ? '0 0 0 3px var(--focus-ring)' : 'var(--shadow-inset)', outline:'none', resize:'vertical', boxSizing:'border-box', width:'100%',
          lineHeight: multiline ? 1.55 : undefined, opacity: disabled ? 0.6 : 1, transition:'border-color var(--dur-fast) var(--ease-out), box-shadow var(--dur-fast) var(--ease-out)' }} />
      {(error || hint) && <span style={{ fontFamily:'var(--font-text)', fontSize:'var(--text-caption)', fontStyle:'italic', color: error ? 'var(--status-danger)' : 'var(--text-muted)' }}>{error || hint}</span>}
    </label>
  );
}

```

### components/forms/Select.jsx

```jsx
import React, { useState } from 'react';

export function Select({ label, options=[], value, defaultValue, onChange, hint, disabled=false, style }) {
  const [focus, setFocus] = useState(false);
  return (
    <label style={{ display:'flex', flexDirection:'column', gap:8, ...style }}>
      {label && <span style={{ fontFamily:'var(--font-mono)', fontSize:'var(--text-label)', letterSpacing:'var(--tracking-label)', textTransform:'uppercase', color:'var(--text-secondary)' }}>{label}</span>}
      <span style={{ position:'relative', display:'block' }}>
        <select value={value} defaultValue={defaultValue} disabled={disabled} onChange={(e) => onChange && onChange(e.target.value, e)}
          onFocus={() => setFocus(true)} onBlur={() => setFocus(false)}
          style={{ appearance:'none', WebkitAppearance:'none', width:'100%', height:44, padding:'0 40px 0 14px', boxSizing:'border-box',
            fontFamily:'var(--font-text)', fontSize:17, color:'var(--text-primary)', background:'var(--bg-surface)', cursor:'pointer',
            border:`1px solid ${focus ? 'var(--accent)' : 'var(--border-default)'}`, borderRadius:'var(--radius-sm)', outline:'none',
            boxShadow: focus ? '0 0 0 3px var(--focus-ring)' : 'var(--shadow-inset)', opacity: disabled ? 0.6 : 1 }}>
          {options.map((o) => { const opt = typeof o === 'string' ? { value:o, label:o } : o; return <option key={opt.value} value={opt.value}>{opt.label}</option>; })}
        </select>
        <span aria-hidden="true" style={{ position:'absolute', right:14, top:'50%', transform:'translateY(-50%)', pointerEvents:'none', color:'var(--text-muted)', fontSize:13 }}>▾</span>
      </span>
      {hint && <span style={{ fontSize:'var(--text-caption)', fontStyle:'italic', color:'var(--text-muted)' }}>{hint}</span>}
    </label>
  );
}

```

### components/navigation/NavBar.jsx

```jsx
import React, { useState } from 'react';

function NavLink({ item, active, onSelect }) {
  const [hover, setHover] = useState(false);
  return (
    <a href={item.href || '#'} onClick={(e) => { if (onSelect) { e.preventDefault(); onSelect(item.id); } }}
      onMouseEnter={() => setHover(true)} onMouseLeave={() => setHover(false)}
      style={{ position:'relative', fontFamily:'var(--font-text)', fontSize:16.5, color: active ? 'var(--text-primary)' : hover ? 'var(--text-primary)' : 'var(--text-secondary)',
        fontStyle: active ? 'italic' : 'normal', textDecoration:'none', padding:'6px 0', transition:'color var(--dur-fast) var(--ease-out)' }}>
      {item.label}
      <span style={{ position:'absolute', left:0, right:0, bottom:0, height:1.5, background:'var(--accent)', transformOrigin:'left',
        transform: active || hover ? 'scaleX(1)' : 'scaleX(0)', opacity: active ? 1 : 0.5, transition:'transform var(--dur-base) var(--ease-out)' }}></span>
    </a>
  );
}

export function NavBar({ brand='Your Name', subtitle, items=[], active, onSelect, onBrandClick, right, sticky=true, style }) {
  return (
    <header style={{ position: sticky ? 'sticky' : 'relative', top:0, zIndex:20, background:'color-mix(in srgb, var(--bg-page) 88%, transparent)',
      backdropFilter:'blur(8px)', WebkitBackdropFilter:'blur(8px)', borderBottom:'1px solid var(--border-subtle)', ...style }}>
      <div style={{ maxWidth:'var(--container)', margin:'0 auto', padding:'0 var(--gutter)', height:68, display:'flex', alignItems:'center', justifyContent:'space-between', gap:'var(--space-5)' }}>
        <a href="#" onClick={(e) => { if (onBrandClick) { e.preventDefault(); onBrandClick(); } }} style={{ display:'flex', alignItems:'baseline', gap:10, textDecoration:'none', color:'var(--text-primary)' }}>
          <span style={{ fontFamily:'var(--font-display)', fontSize:26, lineHeight:1, letterSpacing:'-0.01em' }}>{brand}</span>
          {subtitle && <span style={{ fontFamily:'var(--font-mono)', fontSize:11, letterSpacing:'0.12em', textTransform:'uppercase', color:'var(--text-muted)' }}>{subtitle}</span>}
        </a>
        <nav style={{ display:'flex', alignItems:'center', gap:'var(--space-5)', flexWrap:'wrap' }}>
          {items.map((it) => <NavLink key={it.id} item={it} active={it.id === active} onSelect={onSelect} />)}
          {right}
        </nav>
      </div>
    </header>
  );
}

```

### components/navigation/Tabs.jsx

```jsx
import React, { useState } from 'react';

function Tab({ item, active, onClick }) {
  const [hover, setHover] = useState(false);
  return (
    <button role="tab" aria-selected={active} onClick={onClick} onMouseEnter={() => setHover(true)} onMouseLeave={() => setHover(false)}
      style={{ appearance:'none', background:'none', border:0, borderBottom:`2px solid ${active ? 'var(--accent)' : 'transparent'}`, marginBottom:-1,
        padding:'10px 2px 12px', cursor:'pointer', display:'inline-flex', alignItems:'baseline', gap:8,
        fontFamily:'var(--font-text)', fontSize:17, fontStyle: active ? 'italic' : 'normal', color: active || hover ? 'var(--text-primary)' : 'var(--text-muted)',
        transition:'color var(--dur-fast) var(--ease-out), border-color var(--dur-base) var(--ease-out)' }}>
      {item.label}
      {item.count != null && <span style={{ fontFamily:'var(--font-mono)', fontSize:11, fontStyle:'normal', color: active ? 'var(--text-accent)' : 'var(--text-disabled)' }}>{String(item.count).padStart(2,'0')}</span>}
    </button>
  );
}

export function Tabs({ items=[], value, onChange, style }) {
  return (
    <div role="tablist" style={{ display:'flex', gap:'var(--space-6)', borderBottom:'1px solid var(--border-subtle)', flexWrap:'wrap', ...style }}>
      {items.map((it) => <Tab key={it.id} item={it} active={it.id === value} onClick={() => onChange && onChange(it.id)} />)}
    </div>
  );
}

```

## Website UI kit

# Personal website UI kit

Click-through recreation of the personal academic site (no source site existed — this is the reference design built from the system).

- `index.html` — app shell + router (localStorage `wa_route`), BibTeX cite Dialog
- `data.js` — placeholder content (papers, CV, posts). **All names/institutions are fictional placeholders.**
- `Shell.jsx` — SiteFooter (walnut band), Page wrapper, image Placeholder
- `HomeScreen.jsx` — hero statement + portrait, selected papers, writing cards
- `ResearchScreen.jsx` — Tabs by stage + field filter chips, PaperItem list
- `CVScreen.jsx` — numbered CV blocks of CVEntry
- `WritingScreen.jsx` — WritingScreen index + PostScreen essay with Footnotes
- `AboutScreen.jsx` — bio + contact form (validation + sent state)

### ui_kits/website/index.html

```html
<!-- @dsCard group="Personal Website" viewport="1280x900" name="Personal website" subtitle="Home, Research, CV, Writing, About — click-through" -->
<!doctype html><html><head><meta charset="utf-8"><meta name="viewport" content="width=device-width,initial-scale=1"><title>Jordan Ellis — Economics</title>
<link rel="stylesheet" href="../../styles.css">
<style>@keyframes fadeUp{from{opacity:0;transform:translateY(6px)}to{opacity:1;transform:none}}</style>
<script src="https://unpkg.com/react@18.3.1/umd/react.development.js" integrity="sha384-hD6/rw4ppMLGNu3tX5cjIb+uRZ7UkRJ6BPkLpg4hAu/6onKUg4lLsHAs9EBPT82L" crossorigin="anonymous"></script>
<script src="https://unpkg.com/react-dom@18.3.1/umd/react-dom.development.js" integrity="sha384-u6aeetuaXnQ38mYT8rp6sbXaQe3NL9t+IBXmnYxwkUI2Hw4bsp2Wvmx4yRQF1uAm" crossorigin="anonymous"></script>
<script src="https://unpkg.com/@babel/standalone@7.29.0/babel.min.js" integrity="sha384-m08KidiNqLdpJqLq95G/LEi8Qvjl/xUYll3QILypMoQ65QorJ9Lvtp2RXYGBFj1y" crossorigin="anonymous"></script>
<script src="../../_ds_bundle.js"></script>
<script src="data.js"></script>
</head><body><div id="root"></div>
<script type="text/babel" src="Shell.jsx"></script>
<script type="text/babel" src="HomeScreen.jsx"></script>
<script type="text/babel" src="ResearchScreen.jsx"></script>
<script type="text/babel" src="CVScreen.jsx"></script>
<script type="text/babel" src="WritingScreen.jsx"></script>
<script type="text/babel" src="AboutScreen.jsx"></script>
<script type="text/babel">
const { NavBar, Button, Dialog } = window.WarmAcademiaDesignSystem_c88413;
function App() {
  const [route, setRoute] = React.useState(() => localStorage.getItem('wa_route') || 'home');
  const [cite, setCite] = React.useState(null);
  const [copied, setCopied] = React.useState(false);
  const nav = (r) => { setRoute(r); localStorage.setItem('wa_route', r); window.scrollTo(0, 0); };
  const base = route.split(':')[0];
  const key = cite ? 'ellis' + cite.year.slice(0,4) + cite.id : '';
  const bib = cite ? `@techreport{${key},\n  author = {Ellis, Jordan},\n  title  = {${cite.title}},\n  year   = {${cite.year.slice(0,4)}},\n  type   = {${cite.status}}\n}` : '';
  return (
    <>
      <NavBar brand={window.SITE.name} subtitle="Economics" active={base === 'post' ? 'writing' : base} onSelect={nav} onBrandClick={() => nav('home')}
        items={[{id:'research',label:'Research'},{id:'cv',label:'CV'},{id:'writing',label:'Writing'},{id:'about',label:'About'}]}
        right={<Button size="sm" variant="secondary" iconRight="↗">CV</Button>} />
      <div key={route}>
        {base === 'home' && <HomeScreen onNav={nav} onCite={setCite} />}
        {base === 'research' && <ResearchScreen onCite={setCite} />}
        {base === 'cv' && <CVScreen />}
        {base === 'writing' && <WritingScreen onNav={nav} />}
        {base === 'post' && <PostScreen id={route.split(':')[1]} onNav={nav} />}
        {base === 'about' && <AboutScreen />}
      </div>
      <SiteFooter onNav={nav} />
      <Dialog open={!!cite} onClose={() => { setCite(null); setCopied(false); }} eyebrow="Cite this paper" title={cite ? cite.title : ''}
        footer={<><Button size="sm" variant="ghost" onClick={() => setCite(null)}>Close</Button><Button size="sm" onClick={() => { navigator.clipboard && navigator.clipboard.writeText(bib); setCopied(true); }}>{copied ? 'Copied ✓' : 'Copy BibTeX'}</Button></>}>
        <pre style={{ margin:0, fontFamily:'var(--font-mono)', fontSize:12.5, lineHeight:1.6, background:'var(--bg-sunken)', padding:16, borderRadius:'var(--radius-sm)', whiteSpace:'pre-wrap', color:'var(--text-primary)' }}>{bib}</pre>
      </Dialog>
    </>
  );
}
ReactDOM.createRoot(document.getElementById('root')).render(<App />);
</script></body></html>
```

### ui_kits/website/data.js

```js
window.SITE = {
  name:'Jordan Ellis', role:'Research Assistant in Economics',
  papers:[
    {id:'bnpl',year:'2026',status:'Working paper',statusTone:'ochre',title:'Buy Now, Pay Later and the Payday Cycle',authors:'with M. Okafor',tags:[{label:'Household finance',tone:'terracotta'}],abstract:'Using linked bank-transaction data for 180,000 households, I show that BNPL take-up spikes in the ten days before payday and is concentrated among households with less than one week of liquid savings. Take-up is followed by a 4% rise in overdraft fees over the next quarter.',links:[{label:'PDF'},{label:'Slides'}],group:'wp'},
    {id:'medicaid',year:'2025',status:'Senior thesis',statusTone:'olive',title:'Medicaid Unwinding and Medical Debt in Collections',authors:'Sole-authored',venue:'Honors thesis, Economics',tags:[{label:'Health',tone:'olive'},{label:'Household finance',tone:'terracotta'}],abstract:'Exploiting state variation in the timing of post-pandemic Medicaid redeterminations, I estimate that disenrollment raised the probability of new medical collections by 1.8 percentage points within a year.',links:[{label:'PDF'}],group:'wp'},
    {id:'pharm',year:'2026',status:'Work in progress',statusTone:'ochre',title:'Pharmacy Closures and Prescription Adherence',authors:'with R. Patel and L. Chen',tags:[{label:'Health',tone:'olive'},{label:'Applied micro',tone:'ochre'}],abstract:'We use a stacked event-study around 2,400 retail pharmacy closures to measure changes in chronic-medication fills among nearby Medicare Part D enrollees.',links:[],group:'wip'},
    {id:'min',year:'2026',status:'Work in progress',statusTone:'ochre',title:'Minimum Wages and Household Savings Buffers',authors:'with J. Alvarez',tags:[{label:'Applied micro',tone:'ochre'}],abstract:'Early-stage project linking county minimum-wage changes to emergency-savings measures in the SHED.',links:[],group:'wip'},
    {id:'ra1',year:'2024–',status:'RA project',statusTone:'neutral',title:'Consumer Credit Panel: Pandemic-era forbearance',authors:'For Dr. A. Rivera',tags:[{label:'Household finance',tone:'terracotta'}],links:[],group:'ra'},
  ],
  cv:{
    education:[{period:'2021 — 2025',title:'B.A. Economics & Mathematics, summa cum laude',org:'Whitlock College',detail:'Thesis: “Medicaid Unwinding and Medical Debt in Collections.” Advisor: Prof. S. Nakamura.'}],
    positions:[{period:'2025 — present',title:'Research Assistant',org:'Center for Household Economics',location:'Chicago, IL',bullets:['Build and maintain a 2M-record consumer credit panel in Python and Stata','Draft figures and literature reviews for two working papers']},{period:'2023 — 2024',title:'Undergraduate Research Fellow',org:'Whitlock College Health Policy Lab',bullets:['Cleaned hospital price-transparency files across 400 hospitals']}],
    awards:[{period:'2025',title:'Departmental Prize for Best Senior Thesis'},{period:'2024',title:'Summer Research Fellowship'}],
    skills:[{period:'Programming',title:'Stata, R, Python (pandas, statsmodels), SQL, LaTeX'},{period:'Data',title:'CPS, SHED, MEPS, CFPB Consumer Credit Panel, Medicare claims'}],
  },
  posts:[
    {id:'cps',date:'Sep 2026',title:'What I learned cleaning 40 years of CPS data',excerpt:'Variable names change, top-codes move, and the 1994 redesign is its own adventure. A field guide for new RAs.',readingTime:'7 min read',tag:'Methods',tagTone:'ochre'},
    {id:'why',date:'Jul 2026',title:'Why household finance is a health question',excerpt:'Medical debt, missed prescriptions, and the stress of an overdraft all show up in the same people. Notes toward a research agenda.',readingTime:'5 min read',tag:'Essay',tagTone:'terracotta'},
    {id:'grad',date:'May 2026',title:'Reading list: my first year as an RA',excerpt:'Twelve papers that changed how I think about identification, with a sentence on each.',readingTime:'4 min read',tag:'Reading',tagTone:'olive'},
  ],
};

```

### ui_kits/website/Shell.jsx

```jsx
const { NavBar, Button, Divider } = window.WarmAcademiaDesignSystem_c88413;

function SiteFooter({ onNav }) {
  const lk = { color:'var(--paper-100)', textDecoration:'none', fontSize:16 };
  return (
    <footer style={{ background:'var(--bg-inverse)', color:'var(--text-inverse)', marginTop:'var(--space-9)' }}>
      <div style={{ maxWidth:'var(--container)', margin:'0 auto', padding:'var(--space-8) var(--gutter) var(--space-6)', display:'grid', gridTemplateColumns:'minmax(0,1.4fr) minmax(0,1fr) minmax(0,1fr)', gap:'var(--space-6)' }}>
        <div>
          <div style={{ fontFamily:'var(--font-display)', fontSize:38, lineHeight:1.1 }}>Let’s talk about <em style={{ color:'var(--ochre-500)' }}>households</em>.</div>
          <p style={{ color:'var(--text-inverse-muted)', fontSize:16, margin:'12px 0 20px', maxWidth:380 }}>I’m applying to PhD programs for Fall 2027. Always happy to hear about research, data, or good papers.</p>
          <Button variant="inverse" size="sm" iconRight="→" onClick={() => onNav('about')}>Get in touch</Button>
        </div>
        {[['Site',[['Research','research'],['CV','cv'],['Writing','writing'],['About','about']]],['Elsewhere',[['Google Scholar ↗'],['GitHub ↗'],['Email ↗']]]].map(([h, ls]) => (
          <div key={h}>
            <div style={{ fontFamily:'var(--font-mono)', fontSize:11, letterSpacing:'.14em', textTransform:'uppercase', color:'var(--text-inverse-muted)', marginBottom:14 }}>{h}</div>
            <div style={{ display:'flex', flexDirection:'column', gap:8 }}>{ls.map(([l, id]) => <a key={l} href="#" style={lk} onClick={(e) => { e.preventDefault(); id && onNav(id); }}>{l}</a>)}</div>
          </div>
        ))}
      </div>
      <div style={{ maxWidth:'var(--container)', margin:'0 auto', padding:'0 var(--gutter) var(--space-6)' }}>
        <div style={{ borderTop:'1px solid var(--walnut-700)', paddingTop:16, display:'flex', justifyContent:'space-between', fontFamily:'var(--font-mono)', fontSize:11.5, color:'var(--text-inverse-muted)' }}>
          <span>© 2026 {window.SITE.name}</span><span>Set in Instrument Serif & Newsreader</span>
        </div>
      </div>
    </footer>
  );
}

function Page({ children, narrow }) {
  return <main style={{ maxWidth: narrow ? 'var(--container-narrow)' : 'var(--container)', margin:'0 auto', padding:'var(--space-8) var(--gutter) 0', animation:'fadeUp var(--dur-slow) var(--ease-out)' }}>{children}</main>;
}

function Placeholder({ label, ratio='4 / 5', style }) {
  return <div style={{ aspectRatio:ratio, borderRadius:'var(--radius-md)', background:'repeating-linear-gradient(135deg,var(--paper-200) 0 12px,var(--paper-300) 12px 13px)', border:'1px solid var(--border-subtle)', display:'flex', alignItems:'center', justifyContent:'center', fontFamily:'var(--font-mono)', fontSize:11, letterSpacing:'.12em', textTransform:'uppercase', color:'var(--text-muted)', textAlign:'center', padding:12, ...style }}>{label}</div>;
}

Object.assign(window, { SiteFooter, Page, Placeholder });

```

### ui_kits/website/HomeScreen.jsx

```jsx
const { SectionHeader, PaperItem, PostCard, Button, Tag } = window.WarmAcademiaDesignSystem_c88413;

function HomeScreen({ onNav, onCite }) {
  const S = window.SITE;
  return (
    <Page>
      <section style={{ display:'grid', gridTemplateColumns:'minmax(0,1.7fr) minmax(0,1fr)', gap:'var(--space-8)', alignItems:'end', paddingBottom:'var(--space-8)', borderBottom:'1px solid var(--border-strong)' }}>
        <div>
          <div style={{ fontFamily:'var(--font-mono)', fontSize:'var(--text-label)', letterSpacing:'var(--tracking-label)', textTransform:'uppercase', color:'var(--text-accent)', marginBottom:20 }}>{S.role}</div>
          <h1 style={{ fontSize:'var(--text-display)', lineHeight:'var(--lh-display)', margin:0 }}>I study how households <em style={{ color:'var(--text-accent)' }}>borrow, save,</em> and stay healthy.</h1>
          <p style={{ fontSize:'var(--text-lead)', lineHeight:1.5, color:'var(--text-secondary)', maxWidth:560, margin:'28px 0 32px' }}>I’m an RA at the Center for Household Economics, working in applied micro at the intersection of household finance and health. I’m applying to PhD programs for Fall 2027.</p>
          <div style={{ display:'flex', gap:12, flexWrap:'wrap' }}>
            <Button iconRight="→" onClick={() => onNav('research')}>See my research</Button>
            <Button variant="secondary" iconRight="↗">Download CV</Button>
          </div>
        </div>
        <div style={{ display:'flex', flexDirection:'column', gap:12 }}>
          <Placeholder label="Portrait · 4:5" />
          <div style={{ display:'flex', gap:6, flexWrap:'wrap' }}><Tag tone="terracotta" size="sm">Household finance</Tag><Tag tone="olive" size="sm">Health</Tag><Tag tone="ochre" size="sm">Applied micro</Tag></div>
        </div>
      </section>
      <section style={{ paddingTop:'var(--space-9)' }}>
        <SectionHeader number="01" eyebrow="Selected research" title={<>Recent <em>papers</em></>} action={<Button variant="ghost" size="sm" iconRight="→" onClick={() => onNav('research')}>All research</Button>} />
        <div style={{ marginTop:'var(--space-6)', borderBottom:'1px solid var(--border-subtle)' }}>
          {S.papers.slice(0,2).map((p) => <PaperItem key={p.id} {...p} onCite={() => onCite(p)} />)}
        </div>
      </section>
      <section style={{ paddingTop:'var(--space-9)' }}>
        <SectionHeader number="02" eyebrow="Writing" title={<>Notes from the <em>data</em></>} action={<Button variant="ghost" size="sm" iconRight="→" onClick={() => onNav('writing')}>All writing</Button>} />
        <div style={{ marginTop:'var(--space-6)', display:'grid', gridTemplateColumns:'repeat(auto-fit,minmax(240px,1fr))', gap:'var(--space-5)' }}>
          {S.posts.map((p) => <PostCard key={p.id} layout="card" {...p} onClick={() => onNav('post:' + p.id)} />)}
        </div>
      </section>
    </Page>
  );
}
window.HomeScreen = HomeScreen;

```

### ui_kits/website/ResearchScreen.jsx

```jsx
const { SectionHeader, PaperItem, Tabs, Tag, Divider } = window.WarmAcademiaDesignSystem_c88413;

function ResearchScreen({ onCite }) {
  const S = window.SITE;
  const [tab, setTab] = React.useState('wp');
  const [field, setField] = React.useState(null);
  const fields = ['Household finance','Health','Applied micro'];
  const list = S.papers.filter((p) => p.group === tab && (!field || p.tags.some((t) => t.label === field)));
  const count = (g) => S.papers.filter((p) => p.group === g).length;
  return (
    <Page>
      <SectionHeader size="lg" number="01" eyebrow="Research" title={<>Papers &amp; <em>works in progress</em></>} description="Applied micro questions about how households manage money when health, income, or policy shifts under them." />
      <Divider variant="double" spacing="var(--space-7)" />
      <div style={{ display:'flex', justifyContent:'space-between', alignItems:'flex-end', gap:24, flexWrap:'wrap' }}>
        <Tabs value={tab} onChange={setTab} style={{ borderBottom:0 }} items={[{id:'wp',label:'Working papers',count:count('wp')},{id:'wip',label:'In progress',count:count('wip')},{id:'ra',label:'RA projects',count:count('ra')}]} />
        <div style={{ display:'flex', gap:8, paddingBottom:12, flexWrap:'wrap' }}>{fields.map((f) => <Tag key={f} variant="outline" selected={field === f} onClick={() => setField(field === f ? null : f)}>{f}</Tag>)}</div>
      </div>
      <div style={{ borderBottom:'1px solid var(--border-subtle)' }}>
        {list.map((p) => <PaperItem key={p.id + tab} {...p} onCite={p.group === 'wp' ? () => onCite(p) : undefined} />)}
        {list.length === 0 && <p style={{ padding:'var(--space-6) 0', margin:0, fontStyle:'italic', color:'var(--text-muted)', borderTop:'1px solid var(--border-subtle)' }}>Nothing here under that filter — yet.</p>}
      </div>
    </Page>
  );
}
window.ResearchScreen = ResearchScreen;

```

### ui_kits/website/CVScreen.jsx

```jsx
const { SectionHeader, CVEntry, Button, Divider } = window.WarmAcademiaDesignSystem_c88413;

function CVScreen() {
  const cv = window.SITE.cv;
  const Block = ({ n, title, rows }) => (
    <section style={{ display:'grid', gridTemplateColumns:'200px minmax(0,1fr)', gap:'var(--space-5)', padding:'var(--space-6) 0', borderTop:'1px solid var(--border-subtle)' }}>
      <div style={{ fontFamily:'var(--font-display)', fontSize:'var(--text-h3)', lineHeight:1.1 }}><span style={{ display:'block', fontFamily:'var(--font-mono)', fontSize:11, letterSpacing:'.14em', color:'var(--text-accent)', marginBottom:6 }}>§ {n}</span>{title}</div>
      <div>{rows.map((r, i) => <CVEntry key={i} {...r} style={{ paddingTop: i ? undefined : 0 }} />)}</div>
    </section>
  );
  return (
    <Page>
      <SectionHeader size="lg" eyebrow="Curriculum vitae" title={<>Jordan <em>Ellis</em></>} description="Updated September 2026." action={<Button variant="secondary" iconRight="↗">PDF</Button>} />
      <Divider variant="double" spacing="var(--space-7)" />
      <Block n="01" title="Education" rows={cv.education} />
      <Block n="02" title="Positions" rows={cv.positions} />
      <Block n="03" title="Awards" rows={cv.awards} />
      <Block n="04" title="Skills" rows={cv.skills} />
    </Page>
  );
}
window.CVScreen = CVScreen;

```

### ui_kits/website/WritingScreen.jsx

```jsx
const { SectionHeader, PostCard, Divider, Footnote, Tag, Button } = window.WarmAcademiaDesignSystem_c88413;

function WritingScreen({ onNav }) {
  return (
    <Page narrow>
      <SectionHeader size="lg" eyebrow="Writing" title={<>Notes, essays &amp; <em>reading lists</em></>} description="Shorter thoughts on methods, data, and the questions I want to spend a PhD on." />
      <div style={{ marginTop:'var(--space-7)', borderBottom:'1px solid var(--border-subtle)' }}>
        {window.SITE.posts.map((p) => <PostCard key={p.id} {...p} onClick={() => onNav('post:' + p.id)} />)}
      </div>
    </Page>
  );
}

function PostScreen({ id, onNav }) {
  const p = window.SITE.posts.find((x) => x.id === id) || window.SITE.posts[0];
  const para = { fontSize:19, lineHeight:1.7, margin:'0 0 22px', textWrap:'pretty' };
  return (
    <Page narrow>
      <Button variant="ghost" size="sm" iconLeft="←" onClick={() => onNav('writing')} style={{ marginLeft:-14 }}>All writing</Button>
      <div style={{ display:'flex', gap:12, alignItems:'center', margin:'var(--space-6) 0 16px', fontFamily:'var(--font-mono)', fontSize:12.5, color:'var(--text-muted)' }}><Tag size="sm" tone={p.tagTone}>{p.tag}</Tag>{p.date} · {p.readingTime}</div>
      <h1 style={{ fontSize:'var(--text-h1)', margin:0 }}>{p.title}</h1>
      <Divider variant="double" spacing="var(--space-6)" />
      <p style={{ ...para, fontSize:'var(--text-lead)', color:'var(--text-secondary)' }}>{p.excerpt}</p>
      <p style={para}>When I started as an RA, the first dataset I touched was the Current Population Survey. It looks tidy from a distance: one row per person, a few hundred variables. Up close, the variable definitions drift across decades, and income top-codes change almost every year<Footnote n={1}>The Census Bureau switched to rank-proximity swapping for top-coded earnings in 2011.</Footnote>.</p>
      <blockquote style={{ margin:'var(--space-6) 0', padding:0, fontFamily:'var(--font-display)', fontSize:34, lineHeight:1.2, color:'var(--text-primary)' }}>“Every clean dataset is a stack of <em style={{ color:'var(--text-accent)' }}>decisions</em> someone wrote down — or didn’t.”</blockquote>
      <p style={para}>The practical lesson: keep a log. Every recode, every dropped observation, every judgment call goes in a plain-text file next to the do-file. Future you — and your advisor — will thank you<Footnote n={2}>Mine is a markdown file called decisions.md. It’s now 900 lines long.</Footnote>.</p>
      <Divider variant="ornament" glyph="❦" spacing="var(--space-7)" />
    </Page>
  );
}
Object.assign(window, { WritingScreen, PostScreen });

```

### ui_kits/website/AboutScreen.jsx

```jsx
const { SectionHeader, Input, Select, Button, Card } = window.WarmAcademiaDesignSystem_c88413;

function AboutScreen() {
  const [sent, setSent] = React.useState(false);
  const [email, setEmail] = React.useState('');
  const bad = email && !/.+@.+\..+/.test(email);
  return (
    <Page>
      <div style={{ display:'grid', gridTemplateColumns:'minmax(0,1fr) minmax(0,1.3fr)', gap:'var(--space-8)', alignItems:'start' }}>
        <div style={{ display:'flex', flexDirection:'column', gap:'var(--space-5)' }}>
          <Placeholder label="Photo · desk or library" ratio="4 / 3" />
          <SectionHeader size="md" eyebrow="About" title={<>Hi, I’m <em>Jordan</em>.</>} />
          <p style={{ margin:0, color:'var(--text-secondary)', fontSize:'var(--text-body)' }}>I grew up hearing my parents talk through which bill to pay first. That’s most of why I study household finance. Before my RA job I wrote a senior thesis on medical debt, and I’ve been hooked on the overlap between money and health ever since.</p>
          <p style={{ margin:0, color:'var(--text-secondary)' }}>Outside of work: long walks, used bookshops, and too many sourdough experiments.</p>
        </div>
        <Card padding="lg">
          {sent ? (
            <div style={{ padding:'var(--space-7) 0', textAlign:'center' }}>
              <div style={{ fontFamily:'var(--font-display)', fontSize:'var(--text-h2)' }}>Thank <em>you</em>.</div>
              <p style={{ color:'var(--text-secondary)', margin:'8px 0 20px' }}>I’ll reply within a few days.</p>
              <Button variant="secondary" size="sm" onClick={() => { setSent(false); setEmail(''); }}>Send another</Button>
            </div>
          ) : (
            <form onSubmit={(e) => { e.preventDefault(); if (!bad && email) setSent(true); }} style={{ display:'flex', flexDirection:'column', gap:'var(--space-5)' }}>
              <SectionHeader size="sm" number="✉" eyebrow="Contact" title="Write to me" />
              <div style={{ display:'grid', gridTemplateColumns:'1fr 1fr', gap:'var(--space-4)' }}>
                <Input label="Name" placeholder="Your name" />
                <Input label="Email" placeholder="name@university.edu" value={email} onChange={setEmail} error={bad ? 'That doesn’t look like an email.' : undefined} />
              </div>
              <Select label="Reason" options={['Research question','Collaboration','Just saying hi']} />
              <Input label="Message" multiline rows={5} hint="I usually reply within a few days." />
              <div><Button type="submit" iconRight="→">Send message</Button></div>
            </form>
          )}
        </Card>
      </div>
    </Page>
  );
}
window.AboutScreen = AboutScreen;

```

