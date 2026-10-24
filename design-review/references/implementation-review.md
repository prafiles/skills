# Comparing proposals and applied changes

Use this workflow when producing a visual proposal or implementing authorized refinements. It extends the book-derived criteria with lessons from implementation reviews. Scale the checks to the affected interface; it does not create a new approval requirement or authorize unrelated configuration, CI, or deployment work.

## Establish a comparable baseline

Record the original route, viewport, content, theme, language, scroll position, and interaction state that matter to the change. Wait for fonts and data to load. Identify what already works: composition, typography, palette, density, primary content position, and useful existing motion.

Compare original and proposed views under equivalent conditions. Different data, selected states, scroll positions, or loading phases can make a layout appear improved or broken for the wrong reason. Distinguish intentional state differences. Inspect at actual usable size as well as side by side; a shrunken full-page screenshot can conceal illegible type and excessive scrolling.

For a multi-app review, retain a baseline and result for each app. A shared implementation pattern does not prove that every consumer has the same composition or needs the same treatment.

## Evaluate the result on three fronts

| Quality | Acceptance question |
| --- | --- |
| Task clarity | Does the target user search, remember, interpret, or decide less, while retaining essential information and truthful state? |
| Visual craft | Are spacing, alignment, hierarchy, typography, proportions, density, and component detail coherent with the established design? |
| Motion and delight | Does the requested behavior visibly connect action and result, feel responsive and intentional, and preserve a complete reduced-motion experience? |

An improvement on one front does not excuse a regression on another. When a functional addition looks worse, refine its presentation before calling the work complete. Prefer integrating feedback into the existing component over adding explanatory copy or another panel.

Inspect the complete page composition and the local component contract: nested padding, header and section height, label/control baselines, metric and table rhythm, wrapping, icon alignment, border weight, and remaining chart or map area. Check where the primary task lands in the viewport. Repair a local spacing mismatch before changing shared tokens or adding global overrides.

Check relevant wide and narrow views, including the smallest supported width affected by the change. Exercise long labels and meaningful data; include applicable themes, reading direction, and expanded or selected states. Preserve essential values and context, usable controls, grouping, and scroll continuity. Check representative consumers of shared changes.

## Make motion reviewable

For each requested motion treatment, make its trigger, visible change, timing/easing, settled state, and reduced-motion alternative concrete. Use a playable implementation or recording when the feel or choreography is part of the decision. Do not substitute a written promise or static screenshot for an observable effect.

In the applied UI, exercise normal motion, rapid repeated input or reversal, navigation/cleanup, and initial and live reduced-motion preferences where applicable. Check focus and result visibility, and confirm that logical state and real save/error outcomes remain correct when animation is cancelled or unavailable. Use runtime observations for properties a recording cannot establish. Record only what was actually checked; do not infer smoothness or accessibility from a successful build.

## Verify the applied result and handoff

After transferring an approved proposal, inspect the actual target worktree. Compare its rendered composition and interactions with the approved view. Keep temporary fixture data, forced dates, auth mocks, and preview-only configuration out of the product patch unless separately required and authorized. Describe material demo or fallback conditions in the review evidence; retain concise product labels when users need that distinction.

Capture evidence from the final applied source and record the revision when available. Label original, earlier implementation, proposed, and applied artifacts distinctly. Refresh screenshots, recordings or runtime evidence, and links after changes; an old preview is not proof of the current implementation.

Run checks appropriate to the changed source, alongside visual and task verification. In a PR handoff, link the applied visual evidence and motion checks to the reviewed commit. Distinguish local checks, CI on that commit, merge status, and any deployment status; success at one stage does not establish another. Keep the summary minimal: what changed for the target user, what was verified, and material gaps.
