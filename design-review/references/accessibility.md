# Accessibility supplements

These checks supplement the book rather than quote it. They cover selected visual and interaction concerns, not a full WCAG audit. W3C sources below were checked on 2026-10-24; use the applicable standard and its exceptions when making a conformance claim.

## Measure before declaring failure

For web content, prefer computed foreground/background colors, font size and weight, and actual CSS target bounds. Account for opacity, backgrounds, and states. Screenshot estimates can identify concerns but do not establish exact values or hidden behavior. Never round a failing contrast ratio up to the threshold.

- **Text:** WCAG 2.2 AA SC 1.4.3 requires at least 4.5:1, or 3:1 for large text (at least 18pt, or 14pt bold; approximately 24 CSS px or 18.67 CSS px bold). Placeholder and secondary text are not automatically exempt. Inactive controls, logos, and incidental text have specific exceptions. See [W3C: Contrast (Minimum)](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html).
- **Meaningful non-text cues:** SC 1.4.11 requires 3:1 against adjacent colors for visual information needed to identify controls, their states, and meaningful graphics, with stated exceptions. This does not mean every decorative border needs 3:1, or that two nonadjacent states must contrast 3:1 with each other. See [W3C: Non-text Contrast](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html).
- **Pointer targets:** SC 2.5.8 generally calls for 24 by 24 CSS pixels, with spacing, equivalent-control, inline, user-agent, and essential exceptions. Measure the actual hit area, not only the glyph. Larger targets may improve usability even when the minimum is met. See [W3C: Target Size (Minimum)](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html).
- **Hover/focus content:** SC 1.4.13 addresses dismissibility, pointer access to the revealed content, and persistence until the trigger is removed, the content is dismissed, or the information is invalid. It includes exceptions, such as unmodified browser-controlled content. A timed custom tooltip can violate persistence. See [W3C: Content on Hover or Focus](https://www.w3.org/WAI/WCAG22/Understanding/content-on-hover-or-focus.html).

## Other review checks

When a running interface is available, inspect visible keyboard focus, meaningful control names, non-color state cues, content reflow, zoom, and access to errors or recovery actions. Treat these as usability checks unless the corresponding criteria have been verified. For native apps, also use the relevant platform guidance rather than assuming CSS measurements transfer directly.

Report exactly what was inspected. A static design can show a proposed focus state or target specification, but cannot demonstrate implemented keyboard operation or screen-reader behavior.
