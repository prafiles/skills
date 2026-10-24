# Accessibility supplements

These checks supplement the books rather than quote them. They cover selected visual and interaction concerns, not a full WCAG audit. W3C sources below were checked on 2026-10-24; use the applicable standard and its exceptions when making a conformance claim.

## Measure before declaring failure

For web content, prefer computed foreground/background colors, font size and weight, and actual CSS target bounds. Account for opacity, backgrounds, and states. Screenshot estimates can identify concerns but do not establish exact values or hidden behavior. Never round a failing contrast ratio up to the threshold.

- **Text:** WCAG 2.2 AA SC 1.4.3 requires at least 4.5:1, or 3:1 for large text (at least 18pt, or 14pt bold; approximately 24 CSS px or 18.67 CSS px bold). Placeholder and secondary text are not automatically exempt. Inactive controls, logos, and incidental text have specific exceptions. See [W3C: Contrast (Minimum)](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html).
- **Meaningful non-text cues:** SC 1.4.11 requires 3:1 against adjacent colors for visual information needed to identify controls, their states, and meaningful graphics, with stated exceptions. This does not mean every decorative border needs 3:1, or that two nonadjacent states must contrast 3:1 with each other. See [W3C: Non-text Contrast](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html).
- **Pointer targets:** SC 2.5.8 generally calls for 24 by 24 CSS pixels, with spacing, equivalent-control, inline, user-agent, and essential exceptions. Measure the actual hit area, not only the glyph. Larger targets may improve usability even when the minimum is met. See [W3C: Target Size (Minimum)](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html).
- **Hover/focus content:** SC 1.4.13 addresses dismissibility, pointer access to the revealed content, and persistence until the trigger is removed, the content is dismissed, or the information is invalid. It includes exceptions, such as unmodified browser-controlled content. A timed custom tooltip can violate persistence. See [W3C: Content on Hover or Focus](https://www.w3.org/WAI/WCAG22/Understanding/content-on-hover-or-focus.html).

## Motion and changing content

- **Reduced motion:** check `prefers-reduced-motion: reduce` and any product setting with the relevant interactions, preserving status information and completion. The media feature indicates a request to minimize nonessential motion; `no-preference` is not an explicit request for animation. See [W3C: prefers-reduced-motion](https://www.w3.org/TR/mediaqueries-5/#prefers-reduced-motion). Check actual CSS and scripted effects rather than assuming one stylesheet covers every animation.
- **Interaction-triggered motion:** WCAG 2.2 SC 2.3.3 is **AAA** and requires that motion animation triggered by interaction can be disabled unless essential to functionality or information. Recommend accommodation without misreporting this criterion as an AA requirement. See [W3C: Animation from Interactions](https://www.w3.org/WAI/WCAG22/Understanding/animation-from-interactions.html).
- **Ongoing movement and updates:** SC 2.2.2 (**A**) requires a pause, stop, or hide mechanism for automatically starting moving, blinking, or scrolling information lasting over five seconds and presented alongside other content, unless essential. Auto-updating information has a related control requirement, including control of update frequency, without the five-second condition. Apply the full criterion and exceptions. See [W3C: Pause, Stop, Hide](https://www.w3.org/WAI/WCAG22/Understanding/pause-stop-hide.html).
- **Flashing:** SC 2.3.1 (**A**) allows no more than three flashes in any one-second period, or flashing below the general and red-flash thresholds. Avoid flashing where possible; do not use the book's twice-per-second description as the standard. A stop button does not excuse a threshold violation. Inspect evidence or use appropriate analysis rather than certifying safety by eye. See [W3C: Three Flashes or Below Threshold](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold.html).

## Other review checks

When a running interface is available, inspect visible keyboard focus, meaningful control names, non-color state cues, content reflow, zoom, and access to errors or recovery actions. Treat these as usability checks unless the corresponding criteria have been verified. For native apps, also use the relevant platform guidance rather than assuming CSS measurements transfer directly.

Report exactly what was inspected. A static design can show a proposed focus state or target specification, but cannot demonstrate implemented keyboard operation or screen-reader behavior.
