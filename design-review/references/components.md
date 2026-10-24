# Component review prompts

Use only the sections relevant to the reviewed interface. References are 1-based PDF pages from *Design for Developers*. These prompts paraphrase and adapt the book; keyboard, responsive, and recovery checks extend the visual examples into a usable review workflow. Consult [accessibility.md](accessibility.md) when judging standards compliance.

Review every component for opportunities to improve visual craft and expressive motion as well as function. Develop tactile press states, animated focus and selection, springing switches, icon morphs, fluid menus and disclosures, coordinated list changes, rich card interactions, and satisfying feedback as they fit the design. Treat these as creative possibilities rather than a checklist. Use [motion.md](motion.md) for choreography and the full-motion default; reduced motion is the alternative for users who request it. Component consistency should support a coherent, distinctive visual language rather than freeze existing styling.

## Buttons and actions

Book: PDF pp. 44, 72-74, 121-122, 129-130, 196.

- Does the label describe the outcome in the user's vocabulary? Prefer a specific action over an ambiguous “Submit” when the result is known.
- Are primary, secondary, and destructive actions distinguishable without making secondary actions unreadable or hard to activate?
- Are size, padding, alignment, focus, pressed, disabled, and loading treatments consistent? Does a state change cause a distracting layout shift? A horizontal-to-vertical padding ratio near 2:1 is an example, not a required geometry.
- Is progress communicated after activation? Can users understand completion or failure? Verify duplicate-submission handling only when testing or source inspection supports it.
- Does action placement follow the task, platform, and reading direction? Do not enforce the book's left/right button placement as a universal rule.

## Inputs, textareas, and form grouping

Book: PDF pp. 48, 50-54, 61-64, 123-124, 142, 197.

- Does each input retain an identifiable label after typing? Placeholders should not be the only label. Keep helper text and errors close to their associated field.
- Do field widths and textarea heights signal the expected answer without preventing longer valid input? Use a textarea for multiline responses, and show meaningful limits where applicable.
- Are default, focus, filled, disabled, valid, and invalid states distinguishable? Avoid styling inputs so similarly to buttons that their purpose is unclear. Preserve a visible focus indicator without shifting the layout.
- Is validation actionable and specific? Can users find the affected field and understand how to correct it? Do not rely on a transient toast or a red outline alone.
- Do proximity and group headings clarify related fields? A field's label and help should be more clearly associated with that field than with its neighbor.
- Check long labels, long errors, and filled values where available. The book's 32/40/48px control heights are illustrative sizes, not automatic pass/fail limits.

## Checkboxes, radios, switches, and selects

Book: PDF pp. 55-60, 65-71.

- **Checkbox:** independent or multiple choices; clear checked/unchecked states; an indeterminate parent reflects a partial child selection. The associated label should activate the control. Avoid confusing negative wording.
- **Radio:** mutually exclusive choices with a group label and distinct selection. Defaults should be justified by the task rather than assumed for consequential choices.
- **Switch:** a clearly named binary setting, conventionally applied immediately. If it is staged until Save, assess whether a checkbox or clearer saving model would communicate better.
- **Select:** visible label and selected value, an understandable open state, logically ordered options, and a usable menu. Consider search for long option lists and visible radios for short lists. The book's roughly five-option cutoff is a heuristic, not a rule.
- Inspect target area, keyboard use, wrapping labels, and menu clipping when the implementation permits. Icon size alone does not establish target size.

## Badges, alerts, and toasts

Book: PDF pp. 75-80.

- Does the status label clearly describe its subject? Keep badges adjacent to the object they describe, visually distinct from buttons, and consistent in semantic color and wording.
- If an element is interactive, make that affordance clear rather than presenting it as an inert status badge.
- Do notifications say what happened and what to do next when action is needed? Keep field validation inline; use transient notices for suitable operation feedback.
- Check whether essential information or recovery actions disappear before users can use them. The book's five-second toast timer and two-toast limit are examples, not universal requirements. Review persistence, dismissal, stacking, and access to the result according to importance.

## Navigation: breadcrumbs, tabs, and accordions

Book: PDF pp. 81-83, 98-104, 155.

- **Breadcrumbs:** reflect meaningful content hierarchy, distinguish the current page, and supplement navigation. On narrow screens, preserve useful parent context. Do not substitute browsing history for hierarchy.
- **Tabs:** represent peer views in the same context, with clear labels and a visible active indicator. Inactive tabs must remain readable. Check navigation and focus behavior in a running implementation; a screenshot cannot prove it.
- **Accordions:** clear headings and expansion indicators; the header offers an adequate target. Essential information should not require opening most of the page. Support simultaneous expansion when users need to compare sections; respect legitimate single-section workflows.
- Do not prescribe one caret position or icon shape when the platform already supplies a recognizable, consistent pattern. Keep navigation location predictable across related screens.

## Tables and lists

Book: PDF pp. 84-91.

- Can users identify headers, scan across a row, and distinguish hover, selection, and other states? Develop cell spacing, separators, surface treatments, and zebra striping to support both legibility and visual character. Animate filtering, sorting, selection, and actual data changes with continuity.
- Align text with its reading direction and comparable numbers consistently, often at the end or decimal. Keep header alignment associated with its data.
- Expose relevant search, filtering, sorting, and pagination with clear states when the task needs them. Large datasets may benefit from fixed headers or key columns. Do not add all controls to every table.
- Truncation needs an accessible way to obtain the full value. A mouse-only tooltip is insufficient for essential data.
- On small screens, choose scrolling, prioritized columns, row details, or cards based on the task. A comparison table should not become cards if doing so destroys the comparison; preserve access to necessary data.
- Match ordered lists to sequence or priority; use unordered lists for collections. Indentation and spacing should make nesting clear. Pagination versus progressive loading is a task decision, not an unconditional book rule.

## Tooltips

Book: PDF pp. 92-94.

Keep tooltips concise, adjacent to their trigger, within the viewport, and useful beyond repeating visible text. Do not hide essential instructions or required actions in them. Check keyboard and touch access when applicable. Hover/focus content must allow reading and interaction as described in [accessibility.md](accessibility.md); do not enforce automatic disappearance after a short timer. Rich interactive content may need a different component.

## Cards, icons, and avatars

Book: PDF pp. 95-97, 105-113.

- **Cards:** one coherent subject; clear relationships between image, title, supporting content, and actions; appropriate heading level and padding. Check image crops and content order across viewports. If the whole card is actionable, examine conflicts with nested actions rather than blindly wrapping everything in one link.
- **Icons:** consistent family, visual weight, optical size, and text alignment. Use recognizable meanings and appropriate labels. Prefer scalable assets; a particular icon library or mandatory outline/solid split is not required.
- **Avatars:** consistent identity representation across contexts, appropriate size and crop, and a useful fallback without unsupported gender assumptions. Do not treat a circular shape as mandatory. Status markers must be understandable and not obscure the subject.
