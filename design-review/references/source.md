# Sources and adaptation notes

The user's review priorities supplement both books: pursue beauty, clarity, character, and delight across the whole experience, with more beautiful, expressive animation by default. Lead with a distinctive artistic direction, make substantial improvements visible in the composition and running interactions, and iterate when the result remains generic or largely static. Aesthetic and emotional value are sufficient reasons for an enhancement; it need not also reduce task effort. Remove blanket preferences for restraint, minimalism, muted styling, subtle effects, or the smallest change. Use purposeful copy and evolve the visual and motion system when it improves the result within the requested scope. Reduced motion is opt-in through the operating system, browser, or an explicit product setting; otherwise deliver the full treatment without an opt-in. These are explicit working preferences, not claims attributed to either book. The operative scope and authorization boundary is in [SKILL.md](../SKILL.md).

## Design for Developers

**Design for Developers**, by **Adrian Twarog and George Moller**, was supplied as `dark-version-updated.pdf` (220 PDF pages). The cover and authors are on PDF p. 1. The PDF's metadata records creation in July 2023; no edition or publication date is inferred from that metadata.

All page references in this skill are **1-based PDF page positions**, identified by book. This book's contents uses different numbering; for example, its “Color” section starts at contents page 8 but PDF page 5. Use the PDF position when locating a cited passage.

### Topic map

| Topic | PDF pages | Use in this skill |
| --- | --- | --- |
| Color | 5-23 | Palette roles, shade scales, contrast, and color meaning |
| Typography | 24-39 | Type roles, scale, emphasis, spacing, and legibility |
| Component design | 40-113 | Spacing systems and component-specific review prompts |
| Visual hierarchy | 114-174 | Reading order, contrast, proximity, alignment, consistency, and harmony |
| Design process | 175-185 | Review fidelity, wireframes, and style guides |
| Implementation example | 186-199 | Documenting tokens, variants, and component states |
| Design systems | 200-219 | Reusable components and shared conventions |
| Final thoughts | 220 | Adapting principles to the product rather than following every example literally |

### Interpretation

The references are an original operational synthesis, not transcripts or reproductions of the books. The PDFs and extracted text or artwork are not included. Routine use does not depend on access to the source files, external libraries, or a particular UI framework.

The book combines general principles with prescriptive examples, some internally inconsistent. For example, PDF p. 30 allows all-caps buttons, while p. 73 discourages them. Resolve such advice through the product's readability, task, and conventions. Do not enforce every “do” or “don't” as a universal rule.

The skill deliberately treats font families and sizes, spacing units, grid columns, color proportions, button placement, icon styles, avatar shapes, component dimensions, and Flowbite usage as contextual choices. It preserves the intent of hierarchy and consistency without forcing the book's example aesthetics onto every product.

Specific adaptations include checking dark-mode colors individually instead of merely inverting weights (p. 21), preserving link discoverability despite the underline advice (p. 29), avoiding automatic mobile body-text reduction (p. 34), retaining readable secondary content, and reviewing notification timing according to the information's importance (p. 79). Tooltip persistence (p. 93) and numerical accessibility checks are supplemented by the W3C sources in [accessibility.md](accessibility.md).

Evidence capture, severity labels, verification steps, and the review-versus-implementation boundary are workflow additions. Do not attribute them to the authors. When a recommendation comes from a supplement or from the product's own design system, identify that basis rather than presenting it as a book requirement.

## Animation at Work

**Animation at Work**, by **Rachel Nabors**, was supplied as `Animation-at-work.pdf` (88 PDF pages). The title and author are on PDF p. 1; the copyright page, PDF p. 3, states 2017. In the main text, PDF p. 7 is printed p. 1; add 6 to a printed page number to locate its PDF position.

| Topic | PDF pages | Use in this skill |
| --- | --- | --- |
| Perception and context | 11-22 | Continuity, attention, and cautious interpretation of perceptual claims |
| Patterns and purpose | 23-40 | Transitions, supplements, feedback, demonstrations, decoration, and prioritization |
| Animation anatomy | 41-49 | Easing, duration, changed properties, reusable timing scales, and performance |
| Communication | 50-60 | Motion language, storyboards, playable examples, and explicit handoff values |
| Practice and accommodation | 61-76 | Entrance/exit consistency, loading sequences, frame pacing, and user control |

These insights are synthesized in [motion.md](motion.md). Keep the 2017 tool references, timing examples, research claims, and browser capabilities in their historical context. In particular, the speculative reduced-motion query discussion (PDF p. 73) is superseded by the current CSS feature, and the flashing-frequency description (PDF p. 71) is not the current WCAG criterion. Use the linked standards in [accessibility.md](accessibility.md). Do not carry over claims that fades are universally safe, that unnoticed animation proves lower cognitive load, or that one frame-rate target guarantees smoothness. The book itself encourages testing and revisiting older research (PDF pp. 75-76).
