# Interview Guide

## Host Note

- Use this guide during S2 before sheet planning or Dreamina prompt writing.
- Ask at most five questions as one numbered batch in chat.
- Remember that Codex has no structured-question widget.
- Ask in normal chat and wait for the user's answer.
- Skip anything the user already stated.
- Give every question a recommended answer or practical default.
- Keep the batch short enough for the user to answer casually.
- Include a "surprise me" option when the user wants to delegate the treatment.
- Treat "surprise me" as permission to propose a complete treatment from the photos alone.
- Do not invent private facts that are not visible in photos or supplied by the user.

## Adaptive Ladder

- Cover the missing pieces in this order.
- Collapse questions when the user already gave enough context.
- Stop before five questions when the missing decisions are resolved.
- Prefer concrete choices over abstract taste questions.
- Translate the user's answers into memory, clip, style, and audio decisions.

## Q1 Memory

- Ask what happened in the memory.
- Ask for the visible beats that must appear.
- Ask when and where it happened when that is not already clear.
- Ask who matters most in the moment.
- Recommend naming only the people, places, and objects that should affect the film.
- Recommend a compact answer such as: "arrive at the night market, find the neon stall, laugh over the first bite."
- Skip Q1 when the user already gave the beats, setting, and people.

## Q2 Intent

- Ask whether the film should be faithful or an idealized dream version.
- Ask for any must-happen beats that cannot be dropped.
- Ask for the emotional landing the final frame should leave.
- Recommend faithful recreation when the photos already carry the memory clearly.
- Recommend an idealized dream version when the photos are partial, messy, or emotionally bigger than the literal scene.
- Recommend one emotional landing, such as tender, funny, triumphant, uncanny, wistful, or calm.
- Preserve the user's stated identity, wardrobe, relationships, props, and place facts.

## Q3 Format

- Ask for clip count and duration only after reading the story shape.
- Recommend one clip for one beat or one continuous gesture.
- Recommend two or three clips for a journey, location change, reveal, before-after arc, or emotional turn.
- Recommend match frames when two or three clips must feel continuous.
- Recommend 16:9 as the default aspect ratio unless the source story clearly needs another frame.
- Recommend Seedance 2.0 for the proven default and up to 15 seconds per clip.
- Recommend Seedance 2.5 for 30-second single-pass clips or many references when the UI exposes it.
- Keep aspect ratio and duration as Dreamina settings, not prompt-body text.

## Q4 Style

- Ask for exactly one visual anchor.
- Offer concrete anchors such as handheld night vlog, warm family camcorder, quiet observational documentary, or a named film.
- Recommend the anchor that best matches the source photos and story mood.
- Avoid stacking multiple directors, eras, formats, and lenses.
- Ask for audio direction only as a practical default unless the memory depends on sound.
- Recommend diegetic-only audio by default.
- Recommend wordless audio by default.
- Recommend no score by default.
- Keep music, lyrics, or dialogue out unless the user explicitly asks for them.

## Q5 Boundaries

- Ask only if needed for safety, consent, or factual accuracy.
- Ask whether any person, place, logo, prop, or relationship must be softened or excluded.
- Ask whether any participant's likeness should not be rendered into new images.
- Recommend raw-photo reference use when identity matters and consent is clear.
- Recommend skipping rendered sheets when consent or comfort is uncertain.
- Keep this question out of the batch when boundaries are already obvious.

## Surprise Me

- Offer "surprise me" as an escape hatch in the same numbered batch.
- Explain that the agent will propose a complete treatment from the photos alone.
- Infer only visible facts: people, setting, wardrobe, objects, light, mood, and plausible action.
- Choose a conservative emotional arc that fits the evidence.
- Propose clip count, duration, aspect ratio, model, style anchor, and audio default.
- Present the proposed treatment for confirmation before rendering sheets or writing final prompts.
- Invite corrections to identity, relationships, timeline, and must-happen beats.

## Batch Template

- Use this template after deleting already answered items:

1. What happened in this memory: key beats, when/where, and who matters? Recommendation: keep it to 3 visible beats and name only the people or objects Dreamina must preserve.
2. Should the film be faithful, or an idealized dream version? Recommendation: use faithful if the photos already match; use dream version if the feeling matters more than literal accuracy. Also name the must-happen beat and final emotion.
3. What format fits the story? Recommendation: one beat becomes 1 clip; a journey becomes 2-3 clips chained by match frames; use 16:9 by default; use Seedance 2.0 for proven 15s clips or Seedance 2.5 for longer single-pass/more references.
4. What is the one visual anchor and audio direction? Recommendation: choose one anchor such as handheld night vlog or a named film; use diegetic-only, wordless, no score by default.
5. Would you rather say "surprise me"? Recommendation: choose this if you want me to propose the full treatment from the photos, then you can correct it before any rendering or Dreamina prompt work.

## After The Answer

- Summarize the chosen treatment in one short paragraph.
- Record the story beats, intent, format, style anchor, audio default, and boundaries in state.
- Move to S3 only after the user confirms or corrects the treatment.
