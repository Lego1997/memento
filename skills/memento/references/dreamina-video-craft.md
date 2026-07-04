# Dreamina Video Craft

## Table of Contents

- [1. Use This Role](#1-use-this-role)
- [2. Shape The Prompt Sheet](#2-shape-the-prompt-sheet)
- [3. Build Upload Tables](#3-build-upload-tables)
- [4. Write Director's Shorthand](#4-write-directors-shorthand)
- [5. Keep One Style Anchor](#5-keep-one-style-anchor)
- [6. Anchor, Then Add Only State](#6-anchor-then-add-only-state)
- [7. Pin First And Last Frames](#7-pin-first-and-last-frames)
- [8. Order Action And Camera](#8-order-action-and-camera)
- [9. Guard People And Physicalize Emotion](#9-guard-people-and-physicalize-emotion)
- [10. Layer Diegetic Audio](#10-layer-diegetic-audio)
- [11. Control Adjectives And AI Cliches](#11-control-adjectives-and-ai-cliches)
- [12. Keep Clips Stateless, Short, And Untimed](#12-keep-clips-stateless-short-and-untimed)
- [13. Write Notes For Rerolls](#13-write-notes-for-rerolls)
- [Closing Self-Check](#closing-self-check)

Use this reference when writing paste-ready Dreamina Seedance 2.0 or 2.5 video prompts for personal memories. Treat each clip as a small filmed event carried by user-approved photos, videos, audio, sheets, or frame pins. Preserve memory truth first; use prompt prose only to add motion, light, camera, state, and sound.

## 1. Use This Role

Write for the Codex agent executing the memento skill, not for a general reader.
Turn interview decisions and approved assets into Dreamina-ready prompt blocks.
Keep the craft public, generic, and memory-focused.
Keep examples ordinary, consented, personal, and independent of private workflow context.
Use English only in files, notes, prompts, and examples unless the user explicitly asks for a spoken non-English line.

Positive micro-example:
Two friends leave a night market with one paper bag of skewers, and the clip follows the handoff, laugh, and shared glance.

Negative micro-example:
Two friends continue the previous clip in the same place, with the same feelings, without restating the uploads or action.

## 2. Shape The Prompt Sheet

Start the Markdown sheet with a title, one concept line, a shoot-order checklist, and a settings line.
Use this settings shape: `Seedance 2.0 or 2.5 - All-in Reference - ratio - duration`.
For each clip, write one upload table and one fenced `text` prompt block.
Report the character count near each prompt block and keep it at 1500 characters or fewer.
Close the sheet with a Notes section for platform caps, spatial law, frame pins, wordless rules, and reroll guidance.
Keep Dreamina UI settings outside the prompt body when possible.

Positive micro-example:
`Clip 1 - Night Market Exit` has an upload table, one prompt block, `Characters: 1,238`, and a note that the green tote bag must stay frame-right.

Negative micro-example:
`Clip 1` says "use the same uploads as above" and hides the duration, ratio, and frame-pin rule in loose prose.

## 3. Build Upload Tables

Use the convention `Tag -> File -> Role` for every clip.
List uploads in the exact order the user should add them to Dreamina.
Give each role a specific job, not a vague label.
Use @Image tags for identity, wardrobe, prop, environment, base-frame, first-frame, last-frame, or match-frame roles.
Use @Video tags for environment motion, camera feel, crowd flow, weather, or other visible motion references.
Use @Audio tags for real diegetic tracks or ambient recordings the prompt should follow.
Repeat role sentences inside the prompt block so Dreamina knows what each tag owns.

Positive micro-example:
`| @Image2 | friend-left.png | identity reference for the friend who stays on frame-left |`

Negative micro-example:
`| @Image2 | friend-left.png | nice picture |`

## 4. Write Director's Shorthand

Write present tense, concrete verbs, and visible subject-verb relationships.
Put the load-bearing fact first in each paragraph or line.
Give every sentence a subject, especially when two or more people appear.
Use one visible event per sentence when the action could confuse the model.
Prefer verbs like lifts, braces, turns, passes, lowers, leans, steadies, drifts, taps, and folds.
Avoid screenplay prose, memory essays, and abstract feeling labels.

Positive micro-example:
The friend on frame-left lifts the paper bag between them; the friend on frame-right pinches one skewer and grins without turning away.

Negative micro-example:
Warm memories unfold beautifully as the atmosphere becomes deeply nostalgic and emotionally resonant.

## 5. Keep One Style Anchor

Choose one style anchor for the whole memory film: one film title, one director, one documentary format, or one approved camera reference.
Repeat that anchor in each clip because Dreamina treats clips independently.
Do not stack anchors or combine several famous looks.
Add three or four executable craft details after the anchor: shot size habit, camera movement habit, light logic, color grade, or edit rhythm.
Append this exact face-lock line to each prompt that contains uploaded faces: `Strictly adhere to facial details, maximum facial consistency.`

Positive micro-example:
Style: one warm handheld travel-diary anchor, medium-close phone-vlog framing, available night-market light, soft film grain, gentle handheld sway. Strictly adhere to facial details, maximum facial consistency.

Negative micro-example:
Style: a stunning mix of three famous films for the friends' night-market walk, luxury commercial lighting, epic cinematic texture, gorgeous emotional atmosphere.

## 6. Anchor, Then Add Only State

Let uploaded references own identity, appearance, wardrobe, prop shape, and fixed spatial layout.
Write only the state increment: posture, hand placement, temporary lighting, breath, motion, new prop relationship, or new environmental condition.
Do not restate face shape, hair, body, age, clothing, or accessories already visible in the reference.
Name the person or item only to clarify action.
Use one explicit role sentence for each tag, then stop describing its appearance.
Preserve exact filenames and paths from the approved asset list.

Positive micro-example:
Use @Image1 as the identity reference for the friend on frame-left. The friend on frame-left holds the tote strap tight and keeps the receipt folded in one hand.

Negative micro-example:
Use @Image1 for the pretty friend with shoulder-length dark hair, bright eyes, a slim build, and the same jacket shown in the photo.

## 7. Pin First And Last Frames

Use first-frame pins when the clip must start from an approved composition.
Use last-frame pins when the clip must land on a match frame or a specific closing image.
Write the pin as a direct command using the uploaded tag.
State what must match: body sides, shared prop, hand position, camera angle, or skyline placement.
Avoid describing the pinned frame in a way that fights the image.

Positive micro-example:
Start exactly on @Image1 as the first frame: both friends' hands hold the same paper cup at the bottom edge of frame, market lights blurred behind them.

Negative micro-example:
Begin with something like the previous ending, but brighter, and let the model decide where their hands are.

## 8. Order Action And Camera

Write actions in shot order: opening state, build, turn, and closing state.
Use named shot sizes: wide, full, medium, medium-close, close-up, or big close-up.
Give one main camera move per shot.
Use standard moves: static hold, push in, pull back, pan, tilt, track, follow, crane, half-orbit, or handheld follow.
Separate camera direction from character action when clarity matters.
For one-take clips, add this exact camera-negation line: `one continuous shot, no cuts, no zoom`.
For multi-shot clips, number shots as `Shot 1`, `Shot 2`, and never force per-second timings.

Positive micro-example:
Medium-close handheld follow, one continuous shot, no cuts, no zoom. The friend on frame-left walks beside the stall lights; the friend on frame-right keeps pace and passes the cup back.

Negative micro-example:
The camera zooms, cuts, orbits, cranes, and switches angles while the friends somehow walk, dance, buy food, and reach the ending in three seconds.

## 9. Guard People And Physicalize Emotion

Physicalize emotion as body action, breath, eye line, hand pressure, posture, and silence.
Write "her shoulders drop" instead of "she feels relieved."
Write "his fingers tighten around the ticket" instead of "he is anxious."
Rename the acting subject after any switch between people.
For two or more people, add a duplicate guard sentence.
Use this guard: `Each person appears only once in the whole frame; do not generate duplicate or identical-looking people.`
Keep side rules explicit when continuity depends on them.

Positive micro-example:
The friend on frame-right looks down at the last coin, closes his palm around it, then slides it into the friend on frame-left's hand.

Negative micro-example:
They are emotional, nostalgic, and connected, with a powerful bond visible everywhere.

## 10. Layer Diegetic Audio

Write two or three diegetic sound layers with visible or plausible sources.
Order layers from foreground to background.
Tie contact sounds to visible action when possible.
Use @Audio role sentences when uploaded audio should lead the mix.
When the clip is wordless, close the audio line with `; no score`.
Avoid "X makes a Y sound" laundry lists.
When dialogue is allowed, keep voices clear and foregrounded, and keep ambient sound lower.

Positive micro-example:
Audio diegetic only: follow @Audio1 as the stall speaker track, oil snapping on the grill, coins clicking into the vendor's tray; no score.

Negative micro-example:
Audio: the market makes market sounds, the people make talking sounds, the food makes cooking sounds, emotional music rises.

## 11. Control Adjectives And AI Cliches

Hard-ban praise words and quality claims: stunning, breathtaking, gorgeous, masterpiece, 8K, ultra-HD, premium, blockbuster, epic.
Break vague mood words into observable light, color, texture, and motion.
Keep observable state words when they attach to a visible fact: quiet, tense, crowded, backlit, windblown, wet, empty, overlit, underlit.
Use the One Test: keep a word only if a camera, light meter, microphone, or stopwatch could observe it.
Run an AI-cliche self-scan before delivery.
Cut parallel boilerplate, connective pile-ups, filler adverbs, weak-verb shells, and purple stock phrases.
Watch for not-only-but-also, however, therefore, moreover, in conclusion, really, very, seamlessly, effortlessly, tapestry, testament, realm, symphony of, and dance of.

Positive micro-example:
The alley is quiet except for one fan rattling above the noodle stall; green neon reflects in puddles under their shoes.

Negative micro-example:
The night-market memory is breathtakingly cinematic, a gorgeous tapestry of nostalgia and premium emotional immersion.

## 12. Keep Clips Stateless, Short, And Untimed

Treat every clip as self-contained because Dreamina does not remember another generation.
Restate the style anchor, tag roles, identity roles, prop roles, frame pins, spatial law, action, and audio in every clip.
Never write "same as Clip 1," "as before," "again," "once more," "this time," "back to," or "like the opening."
Keep each prompt block at 1500 characters or fewer; treat 2000 characters as the hard web cap.
Compress by cutting repeated reference descriptions, adjectives, secondary actions, and extra camera moves.
Do not write per-second timings in the prompt body.
Keep duration and ratio in the settings line or Dreamina controls.

Positive micro-example:
Clip 2 restates that @Image3 is the match-frame first pin, @Image4 is the tote-bag prop, and the friend on frame-left remains frame-left.

Negative micro-example:
Clip 2 says "continue from Clip 1, same people and same bag, then at 0-3s they walk and at 3-6s they laugh again."

## 13. Write Notes For Rerolls

End the prompt sheet with concise Notes that help the user reroll failures without rewriting the whole film.
Name the platform cap: Dreamina prompt text hard cap is 2000 characters; memento target is 1500 characters or fewer.
Name the spatial law: who stays on which side, what prop bridges clips, and which frame pins are exact.
Name the wordless rule when used: no dialogue, no laughter, no voice-over, and `; no score`.
Recommend the smallest reroll lever: tighten a reference role, clarify one verb, change one camera move, strengthen a frame pin, or reduce prompt length.
Do not add private implementation notes to the user-facing prompt sheet.

Positive micro-example:
Notes: if the tote switches hands, reroll only Clip 1 with a stronger frame-right tote rule and the same uploads.

Negative micro-example:
Notes: if anything fails, rewrite every clip with more adjectives, more references, and a longer prompt.

## Closing Self-Check

- [ ] Confirm the sheet has a title, concept line, shoot-order checklist, settings line, per-clip upload tables, prompt blocks, character counts, and Notes.
- [ ] Confirm each upload table uses `Tag -> File -> Role` and each @Image, @Video, and @Audio tag has an explicit role sentence in the prompt.
- [ ] Confirm each clip uses one style anchor and no stacked film, director, actor, or character likeness anchors.
- [ ] Confirm each face-bearing prompt includes `Strictly adhere to facial details, maximum facial consistency.`
- [ ] Confirm uploaded references own identity, appearance, wardrobe, prop shape, and fixed layout; prompt prose adds only state increments.
- [ ] Confirm first-frame and last-frame pins say `Start exactly on @Image...` or `End exactly on @Image...` when used.
- [ ] Confirm every action sentence has a subject and every subject switch renames the person.
- [ ] Confirm each shot names a shot size and uses one main camera move.
- [ ] Confirm every one-take prompt includes `one continuous shot, no cuts, no zoom`.
- [ ] Confirm no prompt body uses per-second timings.
- [ ] Confirm clips with two or more people include the duplicate guard.
- [ ] Confirm emotion is physicalized through posture, hands, breath, eye line, or silence.
- [ ] Confirm audio has two or three diegetic layers with sources, and wordless clips close with `; no score`.
- [ ] Confirm every clip is self-contained and avoids "same as above," "as before," "again," "once more," and "this time."
- [ ] Confirm every prompt is 1500 characters or fewer and never exceeds the 2000-character Dreamina cap.
- [ ] Confirm hard-ban praise words are absent, vague mood words are broken into observables, and state words are filmable.
- [ ] Confirm the AI-cliche scan removes boilerplate, connective pile-ups, filler adverbs, weak verbs, and stock purple phrases.
- [ ] Confirm the guide and prompt sheet stay English-only, public, personal-memory focused, and free of private workflow references.
