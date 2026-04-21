# NAISS Lab Design System

A design system for **NAISS Lab** (Networked AI Systems and Security Lab) at the University of Hong Kong (HKU), Department of Data and Systems Engineering. Directed by Prof. Shinan Liu.

This system is derived from a research talk deck titled *"The Promise of Generative Synthetic Data for Networked Intelligent Systems"* (delivered at the Harvard AI and Robotics Seminar / HKU DASE), which the user provided as the style reference. It targets **academic research presentations, seminar slides, and lab-branded artifacts** — clean, minimal, reference-grade academic design.

## Sources

- **Primary style reference:** `uploads/HarvardSharable.pdf` — a 47-slide academic deck by Prof. Shinan Liu. Visual foundations (type, color, layout, diagram conventions, citation style) are derived from this deck.
- **Institutional context:** University of Hong Kong (HKU), Department of Data and Systems Engineering (DASE). HKU's official colour is deep green (Pantone 349 / approx. `#006B37`), commonly used by HKU-affiliated academic materials.
- **Lab context:** NAISS Lab — research focus on networking, AI/ML systems, and security. Flagship work: NetDiffusion, NetSSM, NetGuard, deep generative compression for network traces. Lab website: `https://www.shinan.info/naiss-lab/` (not accessed during build).

## Caveat: PDF visual render unavailable

The attached PDF's visual pages could not be rendered to raster in this environment (the in-browser pdf.js worker timed out repeatedly). The visual foundations below are derived from:
1. The full text extract of the 47-slide deck (slide titles, body copy, diagram labels, table values, citation markers, slide counter positions).
2. The structural conventions of academic seminar slides in this subfield (networking/systems research).
3. HKU institutional brand guidance.

**→ Please spot-check the slide templates against the source PDF. If the real accent colour is different, flag it and I'll retune `colors_and_type.css`.**

## Index

- `README.md` — this file
- `colors_and_type.css` — CSS custom properties for colors, type, spacing, radii, shadows
- `fonts/` — web fonts (Inter, IBM Plex Serif, IBM Plex Mono — see note on substitutions)
- `assets/` — logos, iconography, placeholder imagery
- `preview/` — small HTML cards rendered in the Design System tab
- `slides/` — deck slide templates (`index.html` + per-layout JSX)
- `SKILL.md` — agent skill manifest

## Products covered

This is a **single-surface** system: academic/research slide decks and static artifacts. There is no app or marketing-site product. Accordingly, there is no `ui_kits/` directory — the equivalent is the `slides/` directory, which contains reusable slide-layout components (title slide, section header, diagram slide, comparison table, quote slide, thanks slide, etc.).

### Manifest

| Path | Contents |
|---|---|
| `README.md` | This file — context, content fundamentals, visual foundations, iconography |
| `colors_and_type.css` | CSS custom properties for the whole system + base type utilities |
| `fonts/` | Inter (variable), IBM Plex Serif (400/600), IBM Plex Mono (400/500) |
| `assets/` | NAISS Lab logo, HKU seal, netml.io mark, arrow primitives, figure placeholder |
| `preview/` | Small cards visualising tokens/components for the Design System tab |
| `slides/index.html` | 10 reference slide layouts (title, agenda, section, compare, diagram, table, big-stat, quote, thanks, Q&A) |
| `SKILL.md` | Agent Skill manifest — lets Claude Code or other agents load this as a skill |

---

## Content Fundamentals

Copy in this system comes from academic research presentations. The voice is **declarative, confident, and compact** — typical of a researcher summarising their own work to a peer audience. It is NOT marketing copy and should never read like it.

### Voice & tone
- **Declarative statements end slides.** Titles are full sentences ending in a period: *"AI for operational data is a challenging problem.", "Synthetic data is a promising solution.", "It largely reduces the cost in adaptation."* Never end a slide title with a colon unless it introduces a labelled example (*"Example: AI for operations inside networks.", "Use case 1: non-ML analytics and testing"*).
- **First person plural — "we", "our".** The lab speaks as a collective. *"Our approach: a text-to-traffic synthesis paradigm", "Our work", "Our solution: let model be the data proxy."* Second person ("you") is avoided. First person singular ("I") appears only on title/bio/vision slides.
- **Problem → approach → result structure.** Slide sequences follow: *Pain point → Insight → Our approach → Evaluation → Impact.* Titles carry the narrative; body content elaborates.
- **Evaluative phrases for results.** *"The smaller distance value, the better.", "The higher Δ Accuracy, the better.", "It reduces the storage cost by 82% compared to Gzip."* State the direction of the metric before showing the table.

### Casing
- **Sentence case** throughout. Titles: *"Traffic generators are promising."*, not *"Traffic Generators Are Promising."*
- **Acronyms and model/system names are ALL CAPS or CamelCase.** NetDiffusion, NetSSM, NetGuard, JITI, CATO, ServeFlow, NAISS, HKU, DASE, pcap, GAN, SSM.
- **Conference citations are small, bracketed, with curly apostrophe:** `[SIGCOMM'24]`, `[HotNets'23]`, `[CoNEXT'26]`. Always placed as a small footnote-style line, not inline.

### Tone and vibe
- **Sober, not flashy.** No exclamation marks in slide copy. Emoji are not used in the body of slides; a single trophy 🏆 may appear in a CV/awards context, never in research content.
- **Specific numerics, always.** *"96% of Web Traffic is Encrypted", "175 Zettabytes (10²¹ bytes)", "1.8 Billion Years", "reduces storage cost by 82%".* Always show the unit. Always cite the source (*"Data retrieved from Google transparency report"*) in small caption type below the stat.
- **Humility and attribution.** Student leaders, collaborators, and advisors are named on dedicated slides (*"Shout out to my collaborators!", "Student leaders"*). Names always appear with affiliation (*"Andrew Chu @ UChicago"*).
- **"I" vs "you":** the audience is referenced as "the reader" or implicit; never addressed as "you". Calls-to-action are intellectual questions, not imperatives: *"How to create synthetic data with high utility?", "What's still missing in NetDiffusion?"*

### Typography rules for copy
- Body copy wraps to 2–3 lines max on a content slide. Titles are 1 line, rarely 2.
- Bullet points use an en-dash or bullet (·) — avoid heavy disc bullets. The source deck frequently uses implicit bullets (line breaks) over glyphs.
- Mathematical notation and units stay inline in body text (no LaTeX rendering required for slides).

### Example copy in this voice

> **Title:** "Existing generators either can't capture real-world complexity or are too coarse-grained."
> **Body (left column):** Pros — Fine-grained, Highly controllable. Cons — Can't simulate real-world complexity.
> **Body (right column):** Pros — Learnt complexity. Cons — Coarse-grained output. No protocol constraints.
> **Footer citation:** `[SIGCOMM NAIC'24] Chu et al. Feasibility of State Space Models for Network Traffic Generation`

---

## Visual Foundations

A sparse, reference-grade academic aesthetic. Think *journal figure* more than *marketing deck*. The design gets out of the way so the research reads.

### Color
- **Primary accent: HKU Green (`#006B37`).** Used for: accent words in titles, one underline per slide, primary data series in charts, winning-row highlight in result tables, logo. Never as a full-bleed background (HKU green at 100% is heavy).
- **Tint: `#E6F1EC`** for row stripes in tables, callout boxes, and winning-row backgrounds.
- **Secondary accent: Gold (`#C9A24E`)** — sparingly, for a second comparison series or awards/notable-mention chips.
- **Coral `#D9534F`** for the "worse" / warning row in comparison tables (e.g. the baseline losing to our method).
- **Blue `#2F6FB5`** — third color when diagrams need a cool contrast to green (architecture diagrams, data flow arrows).
- **Warm paper neutrals.** Slide background is `--ink-50` (`#FAFAF7`), not pure white — a whisper of warmth to reduce glare. Text is `#111110`, near-black but slightly off. Cards and chips sit on pure white (`--ink-0`).

### Typography
- **Serif for display — IBM Plex Serif SemiBold.** Used for slide titles and the title slide's display type. Serif gives the deck its scholarly register.
- **Sans for body — Inter.** Used for body copy, captions, axis labels, table content. Crisp, highly legible at presentation distance.
- **Mono for citations and technical strings — IBM Plex Mono.** Used for conference-citation footers, inline `pcap`/`PCAP` references, file-type labels in Wireshark-style tables.
- **Size system** lives in `colors_and_type.css` — a compressed scale from `--fs-meta (14px)` up to `--fs-display (64px)`.

### Backgrounds
- **Flat warm paper (`--ink-50`).** No gradients, no hand-drawn textures, no repeating patterns. Occasional section-header slides invert to a solid HKU-green background with white serif title, but this is used sparingly (1–2 per deck).
- **No full-bleed imagery.** Images and figures sit inside the content area with generous margins; never bleed to slide edges.

### Animation
- **None or near-none.** This deck style is static. If a slide build is needed (e.g. revealing bullet points one by one), use simple fades at 200ms with `ease-out`. No bounces, no slides-in-from-direction, no staggered complex choreography.
- Transitions between slides: instant, no fade.

### Interaction states (for any web renditions)
- **Hover:** text links and buttons darken by one step on the green ramp (`--naiss-green` → `--naiss-green-600`). Icons gain a thin underline on hover; no color change.
- **Press:** 2% darken and no transform (no shrink, no scale). Academic restraint.
- **Focus:** 2px outline in `--naiss-green` offset 2px. Never remove.

### Borders, cards, elevation
- **Hairline borders over shadows.** The default card is 1px solid `--border-1` with no shadow. Shadows are reserved for `--sh-2` on elevated callouts; `--sh-3` for modals/dialogs in any web rendition.
- **Corner radius is small.** `--r-md (6px)` for cards, `--r-sm (3px)` for chips and table cells, `--r-pill` only for small tag/citation chips. No heavily rounded cards; the deck's visual DNA is rectilinear.
- **Dividers:** 1px `--border-1` horizontals between slide title and content, and below tables.

### Layout rules
- **Page padding** is `--slide-pad-x (72px)` horizontal, `--slide-pad-y (56px)` vertical on a 1280×720 canvas.
- **Slide number is bottom-left, small, `--fg-4`.** Sometimes accompanied by a conference-citation line to its right in mono.
- **Title bar** sits in the top 100–120px of the slide; content begins below a subtle hairline divider.
- **Content column is wide-single or 2/3 + 1/3 split.** Full-width diagrams break the column rule when needed. 3-column splits only on direct comparison slides.

### Transparency & blur
- **Avoided.** No glassmorphism, no backdrop blur, no alpha overlays. Flat colors only. The only use of transparency is in shadow values (`rgba(17,17,16, 0.06–0.10)`).

### Imagery vibe
- **Cool-neutral, journal-figure style.** Bar charts with solid fills (green for us, grey for baseline, coral for worst). Architecture diagrams in black line-art with tasteful green fills. Headshots of collaborators are square-cropped, matte, color (not desaturated). No grain, no warmth overlay, no cinematic treatment.

### What to avoid
- Gradients (especially bluish-purple).
- Rounded-corner cards with colored left-border accents.
- Emoji in research content.
- Drop-shadow-heavy material design.
- Dark-mode default (light backgrounds only — decks are shown in lit rooms and projectors).
- Hand-drawn SVG illustrations of abstract concepts.

---

## Iconography

The source deck uses iconography sparingly. Icons appear primarily in **architecture diagrams** (boxes with labels, connected by arrows) rather than as decorative UI glyphs.

### Iconography approach
- **Lucide icons** are used as a substitute set in this system, loaded from CDN (`https://unpkg.com/lucide@latest`). They match the deck's stroke-based, minimal aesthetic: 1.5px stroke weight, rounded-square line terminals, monoline.
- **FLAG — substitution:** the original deck uses PowerPoint shape-primitives (rectangles, arrows) rather than a named icon set. Lucide is a close-in-spirit match. If a specific icon set is desired (e.g. Heroicons, Academicons), flag and I'll swap.
- **Emoji are NOT used** in slide content. The only place emoji appear is in CV-adjacent context (a single 🏆 for awards), and even then it's optional.
- **Unicode typographic characters** ARE used for light structure: `·` (middle dot) as bullet; `→` (rightwards arrow) in section flow; `—` (em dash) for pauses; `[ ]` square brackets for citations.
- **No custom icon font.** No SVG sprite sheet. Architecture diagrams are built with CSS boxes + SVG connectors/arrows, not icon glyphs.

### Logos and marks
- `assets/naiss-lab-logo.svg` — a typographic NAISS Lab wordmark in HKU green.
- `assets/hku-seal.svg` — a simple circular HKU seal placeholder.
- `assets/netml-logo.svg` — the `netml.io` wordmark used in the deck's "NetSSM on GitHub" slide.

### Diagram primitives (in `assets/`)
- `arrow-right.svg` — a filled right-arrow for flow diagrams.
- `arrow-curve.svg` — a gently curved connector for multi-stage pipelines.
- `placeholder-figure.svg` — a generic "figure goes here" placeholder at 4:3 and 16:9.

---
