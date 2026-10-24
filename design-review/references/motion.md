# Motion and animation review

Based on Rachel Nabors' *Animation at Work*, extended by the user's preference for more beautiful, expressive animation by default. All book pages below are 1-based PDF positions in the supplied 88-page file; see [source.md](source.md). The default creative direction and the interruption, input, and verification checks are adaptations rather than book requirements.

## Develop a rich motion language

Book: PDF pp. 12-22, 24-40.

Actively seek opportunities to add and improve animation across the experience. Describe its intended experiential contribution: beauty, atmosphere, character, delight, continuity, or feedback. An animation does not have to teach something or reduce cognitive burden to be worthwhile. Use the book's five patterns to explore its role; an animation can serve more than one:

| Pattern | Review question |
| --- | --- |
| Transition | How can movement make a change of location or task fluid, expressive, and easy to follow? |
| Supplement | How can content enter, leave, or update with visual continuity and character? |
| Feedback | How can acknowledgement, progress, or outcome feel responsive and satisfying? |
| Demonstration | How can animation make a relationship or process engaging and understandable? |
| Decoration | How can motion enrich beauty, atmosphere, brand expression, or emotional appeal? |

Treat static or underdeveloped moments, abrupt context changes, content insertion or removal, and actions without feedback as opportunities for expressive motion. Preserve and elevate successful existing effects. Develop coordinated page transitions, reveals, animated illustrations, moving selection indicators, responsive controls, and celebratory outcomes where they suit the product. Work within the requested scope described in [SKILL.md](../SKILL.md).

Motion attracts attention; use choreography, rhythm, layering, and a clear focal point to compose that attention. Loops, bounces, springs, parallax, and simultaneous effects are creative tools. Assess their actual execution with readable content and usable controls. Recommend reducing or removing an effect only for a concrete problem or an explicit user request; first consider improving its timing, path, layering, or trigger.

Prioritize by the user's goals and the quality of the resulting experience, including aesthetic and emotional value. Prototype choreography when seeing it in motion will help choose a direction. Discuss implementation cost when it affects an actual project constraint; do not assume that the cheapest or simplest effect is the best design.

## Expressive motion and customer delight

These review priorities apply without waiting for a separate animation request. Deliver the full, expressive motion treatment by default. Reduced motion is a preference-based alternative for users who request it through their operating system, browser, or an explicit product setting; users without that request receive the full experience. Existing motion conventions are a starting point that can evolve with the design.

Make cause and effect easy to follow. A panel can emerge from its trigger, an item can visibly join the collection it belongs to, and a reordered row can retain its identity as its position changes. Preserve familiar direction, origin, and destination; use motion to answer where something went or what changed without demanding explanation. Avoid moving the action target away while the user is trying to activate it.

Choreograph attention through the whole scene. Explore layered entrances, staggered reveals, shared-element transitions, flowing layout changes, and coordinated primary and secondary motion. Acknowledge input promptly and let people continue interacting while animation progresses. Give the sequence a deliberate visual rhythm and test it in the real page composition.

Seek delight through expressive responsiveness, playful detail, anticipation, follow-through, and a satisfying sense of completion. Consider tactile press responses, spring-driven expansion, icon morphs, animated illustrations, and confident celebration as well as smooth continuity. Match the artistic direction to the brand and emotional context without assuming that professional or frequently used software must be visually subdued. Success feedback must correspond to a confirmed outcome.

Evaluate both first-time and repeated use for beauty, feel, continuity, responsiveness, and control. Refine triggers, rhythm, and variation when repetition reveals a specific problem. Evaluate the full-motion experience on its own merits, then explicitly request reduced motion and verify that the alternative communicates the same outcomes and supports the same tasks. Distinguish intended delight from measured user response.

Inventory useful existing motion before changing it. For a proposed or implemented enhancement, describe the trigger, visible relationship, transition, and settled result. Consider a travelling selected indicator, a springing disclosure, coordinated map/list selection, a shared-element detail view, a staged hero reveal, a dimensional card response, or an illustrated success sequence. Develop a coherent motion language across these moments, evolving shared patterns and tokens as needed. These examples suggest creative range rather than an effect checklist.

Make first render and live updates engaging and accurate. Use entrances, count-ups, animated changes, and ongoing ambient treatments with deliberate triggers and stable identity. Unrelated rerenders should not accidentally restart a sequence. A user-triggered filter change can visibly reorganize results; a passive data change can animate the values that actually changed. A save acknowledgement belongs to confirmed persistence, not a queued request. Preserve access to real values and keep the settled state understandable after an effect ends or is skipped.

## Timing, easing, and choreography

Book: PDF pp. 42-49, 51-57.

Record the trigger, changed properties, start/end states, duration, delay, and easing when those values are available. Develop or evolve motion tokens and named patterns that express the intended visual language. Compare equivalent actions across the product; consistent meaning matters more than identical durations for different travel distances.

Immediate user feedback should feel connected to the action. Explore deceleration, acceleration, expressive easing curves, spring dynamics, anticipation, overshoot, and follow-through to give movement weight and character. Tune related effects together; a curve name alone does not establish the feel.

Judge total sequence timing, including delay and stagger, as well as each element's duration. The book's 100/300/400/700 ms scale is illustrative; distance, scale, visual rhythm, and the intended feeling affect timing. Give expressive transitions enough time to be perceived and enjoyed. Do not automatically shorten production timings or enforce a single duration. Keep controls usable and logical completion independent of decorative sequences.

For a proposed handoff, pair a small before/during/after storyboard with values and rationale; add a playable example when timing or choreography needs evaluation. A GIF alone does not specify exact implementation values, and a storyboard alone cannot demonstrate the motion's feel. Create these artifacts only when useful to the requested scope.

## Continuity, interruption, and loading

Book: PDF pp. 63-67; interruption and recovery checks are workflow extensions.

- Check both entrance and exit. Direction and origin should support the same spatial model. Abrupt disappearance deserves investigation when it breaks that model; an immediate exit can be appropriate for responsiveness or reduced motion.
- Try reversal, rapid repeated activation, navigation away, and dismissal where safe. Look for queued obsolete animations, snapping to a stale start state, invisible elements retaining focus or pointer interception, and UI state that diverges from the completed action. Do not delay logical completion or trap focus solely to finish an exit effect.
- Retarget from the currently displayed position or measured size when reversing an in-flight effect; cancel obsolete effects and clean them up on navigation or unmount. Preserve the used control, reading position, URL state, and relevant selection. Reveal or focus an offscreen result when the task requires it; motion within a clipped or distant region is not sufficient feedback.
- Inspect fast, slow, failed, and cancelled loading paths where available. Avoid empty-content flashes, stale content reappearing during exit, or brief loading indicators after content is ready. Preserve context while showing accurate progress and recovery.
- Make real waits visually engaging through animated skeletons, progress choreography, shimmer, or branded loading sequences. Keep progress truthful, show ready content promptly, and transition beautifully into the loaded state. The animation should adapt to the real wait rather than adding an artificial delay to finish its sequence.

## Performance and user control

Book: PDF pp. 49, 67-75. Use [accessibility.md](accessibility.md) for current standards and reduced-motion checks.

Observe frame pacing and responsiveness on relevant devices, including while scrolling or loading. Inspect rendering evidence before blaming an animated property. Consider transform or opacity alternatives where layout or paint work is costly, but do not promise GPU acceleration or smoothness from the property name alone. Record the environment and measured result; a screenshot or encoded recording does not prove runtime frame rate. Do not treat 60 FPS as a universal perceptual limit or automatically add blur or throttle frame rates.

When performance needs improvement, optimize rendering, assets, scheduling, and animation execution while preserving the intended visual richness. Do not silently replace the full treatment with a reduced-motion aesthetic based on assumed device limits or task frequency. Provide pause or stop controls for ongoing content where required; such controls let users manage motion without suppressing it by default. Follow the flashing limits in [accessibility.md](accessibility.md) in every mode.

Activate reduced motion only for a user request such as `prefers-reduced-motion: reduce` or an explicit in-product preference. In its absence, including `no-preference`, retain the full treatment. With reduction requested, adapt large translations, zooms, parallax, and repeated effects using a static result or a suitable alternative. Preserve essential information and task completion; merely changing the speed of the same movement may not address the request. Verify that skipping animation does not prevent completion callbacks, status updates, or focus restoration. Do not assume fades suit every user or that a preference toggle alone proves accessible behavior.

Check the full-motion default, an initial reduced-motion request, and preference changes in both directions during a running transition. When reduction is requested, active effects should cancel or adapt and settle into the correct current state. When the request is removed, subsequent interactions should use the full treatment again. Where an animation API is unavailable, preserve working interaction and completion through capability fallback. Verify these behaviors in the applied UI rather than inferring them from a media query or helper name.
