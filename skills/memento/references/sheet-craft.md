# Sheet Craft

## Table of Contents

- [Purpose](#purpose)
- [Reference Budget](#reference-budget)
- [Character Sheet](#character-sheet)
- [Item Sheet](#item-sheet)
- [Environment Sheet](#environment-sheet)
- [Base / Match Frame](#base--match-frame)
- [Adaptive Decision Rules](#adaptive-decision-rules)
- [Revision Loop](#revision-loop)
- [Prompt Hygiene](#prompt-hygiene)
- [Closing Self-Check](#closing-self-check)

## Purpose

Use image sheets only when they reduce Dreamina drift.
Prefer the user's raw photo when it already carries identity, wardrobe, object, or place.
Treat every rendered sheet as a bridge, not as a replacement for the memory.
Ask before sending selected photos to any image-generation system.
Render only the smallest asset that unlocks the next prompt.
Show each result before using it downstream.
Record approval, rejection, and revision notes in the memory state file.
Keep public plugin craft free of source-project names, private story facts, and tool-specific lore.

## Reference Budget

Plan each Dreamina generation around a small set of direct references.
Stay within the current platform upload cap recorded in the platform reference.
Compress repeated roles into approved sheets only when that improves control.
Use raw photos for the strongest identity anchor whenever possible.
Use sheets to solve one clear problem: drift, occlusion, missing angle, wardrobe change, or style transfer.
Name each rendered asset by role and version, such as `char-maya-v01.png`.

## Character Sheet

Run a character sheet as an edit operation from the user's photo.
Use the photo as the identity source.
Never re-describe the face when the user's photo is attached.
Let the face ride the photo reference.
Describe only the renderable changes that the photo does not already solve.
Use a photoreal four-panel model sheet.
Include full-body front view.
Include full-body side view.
Include full-body back view.
Include one head-and-shoulders portrait.
Place all panels on a plain seamless neutral backdrop.
Use soft even studio light.
Keep head-to-toe visibility in the three full-body panels.
Keep the same identity across all panels.
Keep the same body, hairstyle, age presentation, wardrobe, and accessories across all panels.
Use a relaxed neutral stance with arms slightly away from the torso.
Remove text, labels, panel numbers, arrows, and UI markings from the output.
Use the prose aspect cue `Landscape sheet.`
Add a preservation line in the first prompt and every revision prompt.
Write the preservation line in this form:
`Preserve exactly: facial structure, hairstyle, build, age presentation, skin tone, distinctive accessories, and the approved outfit.`
Adjust the anchors in that line to match the user's facts.
Repeat the preservation line in every revision round.
Change only one thing per revision round.
Regenerate a single panel when only that panel drifts.
Reject any result that beautifies, de-ages, slims, changes ethnicity, changes hairstyle, or invents makeup.
Use the user's words for relationship and role, but avoid private backstory in the prompt.
Use a memory-themed micro-example:
`Create a photoreal character model sheet from the attached reunion photo. Keep the same person and cardigan; change only the shoes to clean white sneakers.`

## Item Sheet

Render an item sheet for a key object that must stay recognizable across clips.
Use it for heirlooms, tickets, cups, toys, bags, watches, letters, or shared props.
Keep the object alone on a neutral backdrop.
Use clean product-style lighting.
Show multiple useful angles.
Include front, side, back, and one detail close-up when the object has meaningful wear.
Keep scale cues only when they are simple and non-distracting.
Preserve distinctive wear, dents, scratches, stains, faded edges, labels, handwriting, stickers, and tape marks.
Preserve readable text only when the user confirms it should remain visible.
Avoid inventing brand marks, serial numbers, signatures, or dates.
Describe material, color, shape, size, and condition.
Use one object per sheet unless the objects function as a paired keepsake.
Remove hands, people, tables, props, and packaging unless they are part of the memory anchor.
Use a memory-themed micro-example:
`Clean product-style reference sheet of the old blue thermos from the attached picnic photo; show front, side, back, and a close-up of the worn sticker.`

## Environment Sheet

Render an environment sheet as a clean plate.
Keep people out of the image.
Name the time of day.
Name the main light source.
Name the light direction.
Keep one light logic across the whole plate.
Avoid mixing sunrise, noon, neon, candlelight, and moonlight unless the memory truly requires it.
Include two or three spatial anchors.
Use anchors such as a doorway, window, bench, stair, tree, sign, counter, shoreline, or parked car.
State where the anchors sit in the frame.
Prefer a clean wide or medium-wide plate over a decorative postcard.
Keep the path of movement clear when the clip needs walking, dancing, driving, or a reveal.
Keep weather simple and compatible with the user's memory.
Do not over-style the place into a fantasy location.
Use a memory-themed micro-example:
`Clean empty plate of a grandparents' kitchen at late afternoon, window light entering from frame-left, round table center, sink frame-right, hallway door in the back.`

## Base / Match Frame

Use a base frame as the composed anchor still for one clip.
Use a match frame as the shared last frame of one clip and first frame of the next.
Build base and match frames only when continuity needs a fixed visual pin.
Use labeled fields for base-frame prompts.
Keep field values compact and renderable.
Use this field order for a person from a photo:
`Identity:`
`Outfit:`
`Position:`
`Setting:`
`Lighting:`
`Shot:`
Let identity ride the photo reference.
Omit facial structure from text.
Use `Identity:` for role, age presentation when needed, relationship to the memory, and current situation.
Use `Outfit:` for garments, condition, accessories, and carried items.
Use `Position:` for body placement, pose, frame side, gesture, and micro-action.
Use `Setting:` for immediate surroundings and two or three spatial anchors.
Use `Lighting:` for main light source, direction, color temperature, contrast, and mood.
Use `Shot:` for aspect, camera height, angle, lens feel, distance, and photoreal finish.
Keep one light logic.
Use a match frame when two clips need to hide a location, time, or action swap.
Design match frames without faces.
Use hands, sleeves, watches, rings, bags, cups, shoes, silhouettes, or shared props as identity anchors.
Choose two or three identity anchors.
State the spatial law explicitly.
Keep the spatial law constant across all linked clips.
Write who stays frame-left and who stays frame-right.
Write which hand, sleeve, watch, or prop belongs to whom.
Keep about 90 percent of the match frame anonymous background when the location must swap invisibly.
Keep the shared prop centered when it carries the match.
Make the end frame of clip N equal the first frame of clip N+1.
Tell the video prompt to start or end exactly on the approved match frame.
Use a memory-themed micro-example:
`Low-angle match frame with two hands holding the same birthday candle lighter; red sweater sleeve enters from bottom-left, denim jacket sleeve enters from bottom-right, the flame centered, background mostly dark cake-table blur.`

## Adaptive Decision Rules

Default to the raw photo as the Dreamina identity reference.
Treat the raw photo as the strongest anchor.
Treat the raw photo as the zero-drift choice when identity and wardrobe are clear.
Render a character sheet only for a wardrobe change.
Render a character sheet only when several people are entangled in one photo.
Render a character sheet only when the body is partial, cropped, or occluded.
Render a character sheet only when photo quality is too poor for reliable identity.
Render a character sheet only when the user requests stylization.
Render an item sheet only when the object must remain recognizable or readable.
Render an environment sheet only when the place needs a clean people-free plate.
Render a base frame only when composition, first-frame pinning, or body placement needs stronger control than a raw photo.
Render a match frame only when clip chaining requires a shared visual hinge.
Skip rendering when the user wants a loose impression rather than continuity.
Skip rendering when the existing photo already contains the exact look, object, and place.
Ask the user before replacing a raw memory anchor with a generated sheet.

## Revision Loop

Diagnose the smallest failing unit.
Revise one instruction at a time.
Keep every approved anchor unchanged.
Repeat preservation lines in every character-sheet revision.
Use direct replacement language such as `Change only the shoes to black loafers.`
Avoid broad rewrite requests such as `make it better.`
Regenerate one panel, one object angle, one plate, or one frame when possible.
Stop after repeated drift and return to the raw photo if it is more faithful.
Record the accepted prompt and the accepted image path.

## Prompt Hygiene

Keep prompts concise.
Prefer concrete visible facts.
Avoid private story references.
Avoid named source projects.
Avoid sexually framed or exploitative presentation.
Avoid tool-specific identity systems or vendor-only jargon.
Use positive instructions such as `plain neutral backdrop` instead of long exclusion lists.
Use `no text, no watermark, no added graphics` when the output must stay clean.
Keep aspect cues in prose only when the rendering interface needs them.
Use exact file paths only in workspace notes, not inside image prompts.

## Closing Self-Check

- Confirm that a raw photo would not be a stronger reference.
- Confirm that rendering consent is recorded.
- Confirm that the sheet solves one named continuity risk.
- Confirm that every person from a photo uses the photo as identity source.
- Confirm that character prompts do not re-describe the face.
- Confirm that every character revision repeats `Preserve exactly:`.
- Confirm that environment sheets state time of day, light source, light direction, and spatial anchors.
- Confirm that base frames use Identity, Outfit, Position, Setting, Lighting, and Shot fields.
- Confirm that match frames state identity anchors and spatial law.
- Confirm that linked clips share the exact same match frame.
- Confirm that public-facing text contains no private project references.
- Confirm that the approved asset path and role are recorded before Dreamina prompt writing.
