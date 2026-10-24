# Comparing proposals and applied changes

Use the baseline and quality checks in every review to identify useful enhancements, comparison checks for visual proposals, and applied-result checks when implementing authorized refinements. This workflow extends the book-derived criteria with lessons from implementation reviews. Scale the checks to the affected interface; it does not create a new approval requirement or authorize unrelated configuration, CI, or deployment work.

## Establish a comparable baseline

Record the original route, viewport, content, theme, language, scroll position, and interaction state that matter to the change. Wait for fonts and data to load. Identify what already works: composition, typography, palette, density, primary content position, and useful existing motion.

The baseline is evidence for comparison, not a preservation requirement. Changes to density, page length, focal position, visual language, or familiar motion can improve the result. Evaluate the proposed direction against the user's goals and actual task access rather than treating every departure from the original as a regression.

Compare original and proposed views under equivalent conditions. Different data, selected states, scroll positions, or loading phases can make a layout appear improved or broken for the wrong reason. Distinguish intentional state differences. Inspect at actual usable size as well as side by side; a shrunken full-page screenshot can conceal illegible type and excessive scrolling.

For a multi-app review, retain a baseline and result for each app. A shared implementation pattern does not prove that every consumer has the same composition or needs the same treatment.

## Evaluate the result on three fronts

| Quality | Acceptance question |
| --- | --- |
| Task clarity | Can the target user understand and perform the task with clear content, usable controls, essential information, and truthful state? |
| Visual craft | Does the result strengthen beauty, composition, color, typography, proportions, imagery, depth, and character, evolving the design system where it improves the experience within scope? |
| Motion and delight | Does the full default treatment deliver beautiful, expressive, responsive animation with intentional choreography and satisfying detail, while providing a complete alternative when reduced motion is requested? |

Evaluate these qualities together in the actual experience. When a functional addition looks worse, refine its presentation before calling the work complete. Beauty and delight are valid improvements independently of task-efficiency gains. Do not accept a result merely because it is simpler, quieter, more neutral, or closer to the original; compare the craft and feel of the finished experience.

Inspect the complete page composition and the local component contract: nested padding, header and section height, label/control baselines, metric and table rhythm, wrapping, icon alignment, border weight, and remaining chart or map area. Check where the primary task lands in the viewport. Choose local or shared improvements according to their effect on the composition, and inspect affected consumers when evolving tokens or patterns.

Check relevant wide and narrow views, including the smallest supported width affected by the change. Exercise long labels and meaningful data; include applicable themes, reading direction, and expanded or selected states. Preserve essential values and context, usable controls, grouping, and scroll continuity. Check representative consumers of shared changes.

## Make motion reviewable

For each existing or proposed motion treatment being evaluated, make its trigger, expressive contribution, visible change, choreography, timing/easing, and settled state concrete. Show the full-motion default in a playable implementation or recording when feel or choreography is part of the decision. Separately show the alternative with reduced motion explicitly requested. Do not substitute a written promise or static screenshot for an observable effect.

In the applied UI, verify that the full treatment runs without an opt-in or reduction request, including under `no-preference`. Exercise rapid repeated input or reversal, navigation/cleanup, an initial reduction request, and preference changes in both directions where applicable. Confirm that subsequent interactions regain full motion when the reduction request is removed. Check focus and result visibility, and confirm that logical state and real save/error outcomes remain correct when animation is cancelled or unavailable. Evaluate expressive feel as well as runtime behavior. Record only what was actually checked; do not infer smoothness, delight, or accessibility from a successful build.

## Verify the applied result and handoff

After transferring an approved proposal, inspect the actual target worktree. Compare its rendered composition and interactions with the approved view. Keep temporary fixture data, forced dates, auth mocks, and preview-only configuration out of the product patch unless separately required and authorized. Describe material demo or fallback conditions in the review evidence; retain concise product labels when users need that distinction.

Capture evidence from the final applied source and record the revision when available. Label original, earlier implementation, proposed, and applied artifacts distinctly. Refresh screenshots, recordings or runtime evidence, and links after changes; an old preview is not proof of the current implementation.

Run checks appropriate to the changed source, alongside visual and task verification. In a PR handoff, link the applied visual evidence and motion checks to the reviewed commit. Distinguish local checks, CI on that commit, merge status, and any deployment status; success at one stage does not establish another. Keep the summary minimal: what changed for the target user, what was verified, and material gaps.
