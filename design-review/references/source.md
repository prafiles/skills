# Source and adaptation notes

Primary source: **Design for Developers**, by **Adrian Twarog and George Moller**, supplied by the user as `dark-version-updated.pdf` (220 PDF pages). The cover and authors are on PDF p. 1. The PDF's metadata records creation in July 2023; no edition or publication date is inferred from that metadata.

All page references in this skill are **1-based PDF page positions**. The book's contents uses different numbering; for example, its “Color” section starts at contents page 8 but PDF page 5. Use the PDF position when locating a cited passage.

## Topic map

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

## Interpretation

The references are an original operational synthesis, not a transcript or a reproduction of the book. The PDF and extracted text or artwork are not included. Routine use does not depend on access to the source file, external libraries, or a particular UI framework.

The book combines general principles with prescriptive examples, some internally inconsistent. For example, PDF p. 30 allows all-caps buttons, while p. 73 discourages them. Resolve such advice through the product's readability, task, and conventions. Do not enforce every “do” or “don't” as a universal rule.

The skill deliberately treats font families and sizes, spacing units, grid columns, color proportions, button placement, icon styles, avatar shapes, component dimensions, and Flowbite usage as contextual choices. It preserves the intent of hierarchy and consistency without forcing the book's example aesthetics onto every product.

Specific adaptations include checking dark-mode colors individually instead of merely inverting weights (p. 21), preserving link discoverability despite the underline advice (p. 29), avoiding automatic mobile body-text reduction (p. 34), retaining readable secondary content, and reviewing notification timing according to the information's importance (p. 79). Tooltip persistence (p. 93) and numerical accessibility checks are supplemented by the W3C sources in [accessibility.md](accessibility.md).

Evidence capture, severity labels, verification steps, and the review-versus-implementation boundary are workflow additions. Do not attribute them to the authors. When a recommendation comes from a supplement or from the product's own design system, identify that basis rather than presenting it as a book requirement.
