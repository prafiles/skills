# Motion and animation review

Based on Rachel Nabors' *Animation at Work*. All book pages below are 1-based PDF positions in the supplied 88-page file; see [source.md](source.md). Interruption, input, and verification checks extend the book into a review workflow.

## Establish the purpose before changing the effect

Book: PDF pp. 12-22, 24-40.

Describe what the user learns from the animation in one sentence. Use the book's five patterns to identify its role; an animation can serve more than one:

| Pattern | Review question |
| --- | --- |
| Transition | Does it explain a change of location or task and preserve orientation? |
| Supplement | Does it explain content entering, leaving, or updating within the same task? |
| Feedback | Does it connect an action to acknowledgement, progress, or outcome? |
| Demonstration | Does it explain a relationship or process more clearly than the available static explanation? |
| Decoration | Does its brand or expressive value justify the attention and implementation cost? |

Look for abrupt context changes, unexplained insertion or removal, and actions without feedback. These are candidates for motion, not proof that motion is required. Compare with a clearer static state or simpler content change. Do not replace ordinary navigation architecture merely to enable page transitions.

Motion attracts attention, including outside the user's current focus. Check whether peripheral loops, repeated bounces, or simultaneous effects compete with reading or the primary action. Decoration is not automatically a defect, and unnoticed motion is not proof of reduced cognitive load. Treat perceptual benefits as hypotheses to verify with the task and audience.

Prioritize expected task benefit against implementation effort and dependencies. Separate inexpensive useful feedback from larger navigation investments; prototype uncertain, costly changes before recommending broad adoption. Keep this effort assessment separate from finding severity.

## Intuitive motion and customer delight

These review priorities extend the book with the user's emphasis on cognitive burden and delight. Apply the design-preservation and confirmation boundary in [SKILL.md](../SKILL.md); adding motion does not authorize replacing the product's interaction model.

Make cause and effect easy to follow. A panel can emerge from its trigger, an item can visibly join the collection it belongs to, and a reordered row can retain its identity as its position changes. Preserve familiar direction, origin, and destination; use motion to answer where something went or what changed without demanding explanation. Avoid moving the action target away while the user is trying to activate it.

Choreograph attention toward the next useful state. Keep the relevant content stable, acknowledge input promptly, and let secondary effects settle without delaying reading or the next action. Several simultaneous movements or a long entrance sequence can cost more attention than the change they explain. Use established motion patterns and test whether the relationship is understandable on first use.

Seek delight in responsiveness, reassurance, and a satisfying sense of completion. A subtle saved-state acknowledgement or a smooth expansion that preserves reading position may be more appropriate than a bounce or celebration. Match expressiveness to the brand, task frequency, and emotional context; allow restraint for repetitive work and serious tasks. Do not signal success before it is confirmed.

Evaluate both first-time and repeated use. Ask what the motion helps the target user notice or understand, whether it stays pleasant when repeated, and whether a simpler effect works as well. Compare the normal and reduced-motion experiences: both must communicate the outcome and support the same task. Keep novelty optional and do not claim delight without user evidence.

## Timing, easing, and choreography

Book: PDF pp. 42-49, 51-57.

Record the trigger, changed properties, start/end states, duration, delay, and easing when those values are available. Reuse existing motion tokens or named patterns before inventing new ones. Compare equivalent actions across the product; consistent meaning matters more than identical durations for different travel distances.

Immediate user feedback should feel connected to the action. Deceleration can support a quick response that settles; acceleration can introduce an unsolicited change more gently; an ease-in-out can connect positions. These are starting points, not mandatory mappings. Check the actual curve and effect rather than assuming a keyword ensures the right feel.

Judge total waiting time, including delay and stagger, not only one element's duration. The book's 100/300/400/700 ms scale is illustrative; distance, scale, task frequency, and audience affect appropriate timing. Do not automatically quarter production timings or enforce a single duration on every animation. Frequent actions should not wait for decorative sequences to complete.

For a proposed handoff, pair a small before/during/after storyboard with values and rationale; add a playable example when timing or choreography needs evaluation. A GIF alone does not specify exact implementation values, and a storyboard alone cannot demonstrate the motion's feel. Create these artifacts only when useful to the requested scope.

## Continuity, interruption, and loading

Book: PDF pp. 63-67; interruption and recovery checks are workflow extensions.

- Check both entrance and exit. Direction and origin should support the same spatial model. Abrupt disappearance deserves investigation when it breaks that model; an immediate exit can be appropriate for responsiveness or reduced motion.
- Try reversal, rapid repeated activation, navigation away, and dismissal where safe. Look for queued obsolete animations, snapping to a stale start state, invisible elements retaining focus or pointer interception, and UI state that diverges from the completed action. Do not delay logical completion or trap focus solely to finish an exit effect.
- Inspect fast, slow, failed, and cancelled loading paths where available. Avoid empty-content flashes, stale content reappearing during exit, or brief loading indicators after content is ready. Preserve context while showing accurate progress and recovery.
- Loading effects should explain a real wait. Do not add artificial delays to exhibit a spinner or leave usable server-rendered content hidden until JavaScript animates it. A skeleton, static status, or direct update may suit the task better than a looping shimmer.

## Performance and user control

Book: PDF pp. 49, 67-75. Use [accessibility.md](accessibility.md) for current standards and reduced-motion checks.

Observe frame pacing and responsiveness on relevant devices, including while scrolling or loading. Inspect rendering evidence before blaming an animated property. Consider transform or opacity alternatives where layout or paint work is costly, but do not promise GPU acceleration or smoothness from the property name alone. Record the environment and measured result; a screenshot or encoded recording does not prove runtime frame rate. Do not treat 60 FPS as a universal perceptual limit or automatically add blur or throttle frame rates.

Check reduced-motion behavior for large translations, zooms, parallax, and repeated effects. Preserve essential information and task completion using a static result or restrained alternative; merely speeding up or slowing down the same motion may not address the problem. Verify that skipping animation does not prevent completion callbacks, status updates, or focus restoration. Do not assume fades suit every user or that a preference toggle alone proves accessible behavior.
