---
name: naiss-lab-design
description: Use this skill to generate well-branded interfaces and assets for NAISS Lab (Networked AI Systems and Security Lab, HKU DASE), either for production or throwaway prototypes/mocks/etc. Contains essential design guidelines, colors, type, fonts, assets, and slide-layout components for academic research presentations and lab artifacts.
user-invocable: true
---

Read the README.md file within this skill, and explore the other available files.

If creating visual artifacts (slides, mocks, throwaway prototypes, etc), copy assets out and create static HTML files for the user to view. If working on production code, you can copy assets and read the rules here to become an expert in designing with this brand.

If the user invokes this skill without any other guidance, ask them what they want to build or design, ask some questions, and act as an expert designer who outputs HTML artifacts _or_ production code, depending on the need.

Key files:
- `README.md` — brand context, content fundamentals, visual foundations, iconography
- `colors_and_type.css` — CSS custom properties (colors, type, spacing, radii, shadows) and base type utilities
- `fonts/` — Inter (variable), IBM Plex Serif (400/600), IBM Plex Mono (400/500)
- `assets/` — logos (NAISS Lab, HKU, netml.io), arrow primitives, figure placeholder
- `slides/index.html` — 10 reference slide layouts built against the system
- `preview/` — small cards visualising tokens and components

Quick design rules for this brand:
- Warm-paper background (`#FAFAF7`), near-black text (`#111110`), HKU green (`#006B37`) as the single accent.
- Serif display (IBM Plex Serif), sans body (Inter), mono for citations (IBM Plex Mono).
- Titles end in a period. First person plural ("we / our"). Sentence case.
- Citations in `[CONF'YY]` form, bracketed, mono, small.
- Hairline borders (1px), small radii (3–6px), minimal shadows.
- No gradients, no emoji in research content, no dark mode.
