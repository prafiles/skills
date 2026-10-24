# Visual review criteria

These are review questions and adaptations of *Design for Developers*. Page references use the supplied PDF's **1-based page index**, not the larger numbers in its contents. See [source.md](source.md) for provenance and interpretation limits.

Apply these criteria to proactively pursue visual excellence in every review while respecting the requested scope in [SKILL.md](../SKILL.md). Use existing tokens and components where they serve the result; evolve palette, typography, themes, layout, and component treatments when that improves the experience. Beauty, character, and emotional appeal are independent design goals. Neutrality, minimalism, low saturation, sparse decoration, and small changes have no automatic preference over expressive alternatives.

## Hierarchy and reading order

Book: PDF pp. 114-140, 173-174.

Identify what should be noticed first, understood next, and acted on. Compare that intended order with the strongest visual signals: size, weight, contrast, position, density, and surrounding space. A large illustration, bright action, or bold frame can intentionally lead the composition. Assess whether the resulting hierarchy supports the intended experience and makes relevant actions discoverable.

Look for a clear primary action within each task group, a meaningful distinction from secondary actions, and a recognizable relationship between heading, supporting explanation, and controls. Repeated primary actions can be appropriate in separate contexts; do not impose one button on an entire application.

The book's F and Z scanning patterns are useful hypotheses for some left-to-right layouts, not universal eye-tracking results. Account for reading direction, page density, and task. Prefer observable relationships over claims about where every user will look.

**Useful enhancement:** strengthen a focal heading through expressive scale and typography, use color and depth to connect the primary action to its inputs, and choreograph supporting elements around that focal point. Resolve genuinely competing signals through composition rather than automatically muting the rest of the page.

## Proximity, spacing, and alignment

Book: PDF pp. 41-43, 141-151, 159-164.

Make relationships legible: heading with its paragraph, label with its input, price with its product, and control with its result. Use proximity, alignment, shared surfaces, typography, connecting motifs, or coordinated movement to express those relationships. Generous spacing can create atmosphere and emphasis while other cues maintain grouping; judge the composition rather than imposing a gap ratio.

Check consistent container edges, gutters, baselines, and padding. Look for unexplained alignment changes between navigation, page content, and sections. Use top alignment for differently sized content blocks when it improves scanning; center alignment may fit compact items such as a logo and navigation row. Respect intentional asymmetry.

Use a coherent spacing scale and evolve it when the composition benefits. The book illustrates 4- and 5-unit scales and 12-column layouts; none is mandatory. Allow optical adjustments, dramatic spacing, and distinctive grids when intentional. Dense operational interfaces and expansive storytelling layouts can both be well designed.

Check that text and controls have breathing room inside containers and that increased spacing does not bury related actions. On narrow screens, preserve task grouping and usable gutters without forcing desktop columns or introducing accidental overflow.

Inspect spacing as a system of proportions: page gutter, section gap, card inset, heading-to-content gap, row rhythm, and control baseline. Compare the whole composition before and after a change. Evaluate the role of headers, summaries, framing, and content area together. An expansive introduction or a below-the-fold task can be intentional; flag displacement when it impairs the intended flow rather than treating compactness or above-the-fold placement as universal goals.

Choose density deliberately on phones as well as desktop. Compact grids, spacious cards, full-width features, and editorial sequences are available directions. Develop columns and wrapping from the content and intended composition, keeping values, units, and essential context readable. Check reading order, scrolling, and task access at supported narrow widths without assuming that a shorter page or denser grid is better.

**Useful enhancement:** develop a deliberate rhythm between generous section spacing and closely grouped controls, use a shared container system, and adjust optical alignment. Explain the intended composition rather than recommending only “add more whitespace.”

## Typography

Book: PDF pp. 25-39, 118-120, 154, 182, 191.

Develop text roles through family, scale, weight, line height, tracking, and expressive detail. Explore display type, strong scale contrasts, intentional all caps, variable fonts, and complementary families where they strengthen character. Headings should be distinguishable from body text and metadata should remain readable; diagnose unclear roles rather than treating typographic richness as a defect.

Evaluate actual legibility at the intended viewport, reading distance, and content density. Long-form copy, delicate type, and text over rich imagery can all be successful treatments; inspect whether readers can comfortably follow the real content. Tune scale, leading, contrast, overlays, and wrapping to support the chosen direction rather than automatically shortening copy or simplifying the background.

The book offers roughly 16px body text and 1.5 body line height as starting points, with tighter leading for large headings. Use the product's actual typeface and content to choose values. Do not mechanically shrink body text on phones, impose serif headings, reject a single-family system, or treat illustrative font sizes as accessibility thresholds. Preserve meaningful links and their discoverability rather than removing underlines as a blanket style rule.

**Useful enhancement:** give a key heading a distinctive display treatment, tune leading and wrapping, and develop supporting styles with clear relationships. Evolve shared text styles when the existing scale limits the result.

## Color, contrast, and themes

Book: PDF pp. 11-23, 127-140, 153, 170, 181, 189.

Identify the roles of surface colors, primary actions, secondary content, accents, and semantic states. Similar meanings should have coherent treatment, while success, warning, and destructive actions should be understandable through text or symbols as well as color. Surfaces can be vivid, patterned, illustrated, or neutral according to the artistic direction.

Explore vibrant palettes, gradients, colorful surfaces, atmospheric backgrounds, and expressive accents where they strengthen the composition. Check readable foreground/background combinations and distinguishable semantic states. Diagnose specific hierarchy or legibility problems rather than treating saturation or multiple accents as inherently excessive. The monochromatic, analogous, complementary, and triadic examples are palette-building options; cultural color associations need context.

The book's 60/30/10 ratio suggests one dominant, supporting, and accent balance. Use it as a compositional option rather than a pass/fail percentage or a reason to restrict color. A vivid full surface or a concentrated accent can both create a strong focal point.

Review light and dark themes as separate compositions. Reassign semantic surface/text/border roles and verify their combinations; simply reversing a shade scale does not guarantee readable dark mode. Muted text, placeholders, hover styles, focus indicators, and selected states still need appropriate visibility. Use [accessibility.md](accessibility.md) for measured checks.

**Useful enhancement:** build a distinctive surface and accent palette, introduce a gradient or tonal depth where it improves the composition, and map status labels to semantic tokens consistently. Check readability in each state.

## Borders, depth, imagery, and visual balance

Book: PDF pp. 45-49, 105-113, 165-174, 183, 187, 193-194.

Use borders, layered shadows, highlights, textures, and dimensional surfaces to develop depth and character as well as grouping and interaction. Make their relationships coherent and controls recognizable. If depth becomes ambiguous, improve the elevation hierarchy; do not flatten the interface merely to reduce decoration.

Evaluate the composition as a whole: size, color, density, images, and whitespace distribute visual weight. Symmetry can support order, asymmetry can balance a dominant visual, and a central focal point can organize surrounding content. None is mandatory. Avoid making every section identical if variation supports the story, or varying layout so much that repeated tasks become unpredictable.

Check image crops, focal subjects, text overlays, logo proportions, and icon style and optical alignment. Imagery and illustration can lead the composition, tell the story, or provide atmosphere; arrange readable content and usable controls around that direction. Scale icon artwork separately from its interaction target. Preserve familiar meanings and add clear labels where an icon's meaning is uncertain.

## Consistency and the design process

Book: PDF pp. 152-158, 175-185, 195-211.

Compare repeated actions, vocabulary, navigation placement, typography, and component states across the inspected screens. Reuse should help users transfer understanding between tasks. When repeated defects originate in one token or component, propose fixing that source and checking its consumers.

For wireframes, prioritize content organization, component recognition, relative proportions, and task flow; unfinished color and imagery are not automatically defects. For mature interfaces, develop tokens, component variants, interaction states, responsive behavior, and an expressive visual and motion language. Recommend new conventions when they improve coherence or creative range, including opportunities beyond existing defects. The book's Flowbite walkthrough demonstrates reuse; it does not require adopting Flowbite, Tailwind, or Figma.
