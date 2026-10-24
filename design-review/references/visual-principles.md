# Visual review criteria

These are review questions and adaptations of *Design for Developers*. Page references use the supplied PDF's **1-based page index**, not the larger numbers in its contents. See [source.md](source.md) for provenance and interpretation limits.

## Hierarchy and reading order

Book: PDF pp. 114-140, 173-174.

Identify what should be noticed first, understood next, and acted on. Compare that intended order with the strongest visual signals: size, weight, contrast, position, density, and surrounding space. A large illustration, bright secondary button, or heavy border can accidentally outrank the task.

Look for a clear primary action within each task group, a meaningful distinction from secondary actions, and a recognizable relationship between heading, supporting explanation, and controls. Repeated primary actions can be appropriate in separate contexts; do not impose one button on an entire application.

The book's F and Z scanning patterns are useful hypotheses for some left-to-right layouts, not universal eye-tracking results. Account for reading direction, page density, and task. Prefer observable relationships over claims about where every user will look.

**Useful correction:** reduce the competing emphasis of a secondary action, bring the primary action closer to its related inputs, or strengthen the heading/body distinction before adding more decorative effects.

## Proximity, spacing, and alignment

Book: PDF pp. 41-43, 141-151, 159-164.

Related elements should read as a group: heading with its paragraph, label with its input, price with its product, and control with its result. Internal gaps should generally be smaller than gaps between unrelated groups. Extra whitespace is harmful if it makes related elements look disconnected.

Check consistent container edges, gutters, baselines, and padding. Look for unexplained alignment changes between navigation, page content, and sections. Use top alignment for differently sized content blocks when it improves scanning; center alignment may fit compact items such as a logo and navigation row. Respect intentional asymmetry.

Prefer the existing spacing scale. The book illustrates 4- and 5-unit scales and 12-column layouts; none is a mandatory replacement for a working system. Fix arbitrary drift and ambiguous grouping, not every non-multiple or optical adjustment. Dense operational interfaces can require less space than marketing pages.

Check that text and controls have breathing room inside containers and that increased spacing does not bury related actions. On narrow screens, preserve task grouping and usable gutters without forcing desktop columns or introducing accidental overflow.

**Useful correction:** apply a shared container token, reduce a label-to-field gap, and increase the gap before the next field group. Avoid recommending only “add more whitespace.”

## Typography

Book: PDF pp. 25-39, 118-120, 154, 182, 191.

Check whether text roles have a coherent scale and consistent family, size, weight, line height, and tracking. Headings should be distinguishable from body text; metadata should be subordinate while remaining readable. Excessive bold, italics, all caps, or competing families can erase emphasis.

Evaluate actual legibility at the intended viewport, reading distance, and content density. Long passages, tiny thin text, crowded lines, or text over a busy image deserve attention. Inspect wrapping with real headings and labels rather than enforcing single-line headings.

The book offers roughly 16px body text and 1.5 body line height as starting points, with tighter leading for large headings. Use the product's actual typeface and content to choose values. Do not mechanically shrink body text on phones, impose serif headings, reject a single-family system, or treat illustrative font sizes as accessibility thresholds. Preserve meaningful links and their discoverability rather than removing underlines as a blanket style rule.

**Useful correction:** consolidate inconsistent section headings into one existing text style, adjust leading for a wrapped heading, or strengthen a faint caption without making it compete with the title.

## Color, contrast, and themes

Book: PDF pp. 11-23, 127-140, 153, 170, 181, 189.

Identify the roles of neutral surfaces, primary actions, secondary content, accents, and semantic states. Similar meanings should have consistent treatment, while success, warning, and destructive actions should be understandable through text or symbols as well as color.

Look for uncontrolled saturation, competing accents, indistinct foreground/background combinations, and color applied without a clear role. The monochromatic, analogous, complementary, and triadic examples are palette-building options; a palette is not wrong merely because it uses a different relationship. Cultural color associations need context.

The book's 60/30/10 ratio suggests a dominant, supporting, and accent balance. Use it to reason about visual weight, not to calculate a pass/fail percentage. A small accent can communicate more clearly than an entire high-saturation section.

Review light and dark themes as separate compositions. Reassign semantic surface/text/border roles and verify their combinations; simply reversing a shade scale does not guarantee readable dark mode. Muted text, placeholders, hover styles, focus indicators, and selected states still need appropriate visibility. Use [accessibility.md](accessibility.md) for measured checks.

**Useful correction:** use a neutral surface for a large panel, reserve the accent for its primary action, and map status labels to semantic tokens consistently.

## Borders, depth, imagery, and visual balance

Book: PDF pp. 45-49, 105-113, 165-174, 183, 187, 193-194.

Check whether borders and shadows clarify grouping, interaction, or depth. Heavy outlines around every region can compete with content; excessive shadows can make every card appear elevated. Prefer a small, consistent vocabulary. Do not remove a boundary needed to recognize a control merely to reduce decoration.

Evaluate the composition as a whole: size, color, density, images, and whitespace distribute visual weight. Symmetry can support order, asymmetry can balance a dominant visual, and a central focal point can organize surrounding content. None is mandatory. Avoid making every section identical if variation supports the story, or varying layout so much that repeated tasks become unpredictable.

Check image crops, focal subjects, text overlays, logo proportions, and icon style and optical alignment. Images should support the message without overpowering it. Scale icon artwork separately from its interaction target. Preserve familiar meanings and add clear labels where an icon's meaning is uncertain.

## Consistency and the design process

Book: PDF pp. 152-158, 175-185, 195-211.

Compare repeated actions, vocabulary, navigation placement, typography, and component states across the inspected screens. Reuse should help users transfer understanding between tasks. When repeated defects originate in one token or component, propose fixing that source and checking its consumers.

For wireframes, prioritize content organization, component recognition, relative proportions, and task flow; unfinished color and imagery are not automatically defects. For mature interfaces, check that the style guide covers tokens, component variants, interaction states, and responsive behavior. Recommend only the missing conventions that solve observed problems. The book's Flowbite walkthrough demonstrates reuse; it does not require adopting Flowbite, Tailwind, or Figma.
