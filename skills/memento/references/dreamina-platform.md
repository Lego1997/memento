# Dreamina Platform Facts

## Version

- Treat this sheet as the single source for Dreamina web-app facts inside memento.
- Mark all facts as last verified in-app on 2026-07-04.
- Re-check visible controls before promising an option to the user.
- Assume the Dreamina UI evolves, especially during Seedance 2.5 rollout.
- Keep prompt prose in English, while preserving required UI strings exactly.

## All-In Reference Mode

- Use Dreamina (Jianying/Jimeng, UI name: 即梦) web app for final video generation.
- Select All-in Reference mode when combining people, place, props, frames, video, or audio.
- Map uploaded images to `@Image1`, `@Image2`, and onward.
- Map uploaded videos to `@Video1`, `@Video2`, and onward.
- Map uploaded audio to `@Audio1`, `@Audio2`, and onward.
- Recognize Chinese UI equivalents: `@图1`, `@视频1`, and `@音频1`.
- Include the tag that Dreamina shows in the upload table and paste block.
- Give every uploaded asset an explicit role sentence in the prompt.
- Write roles as functional instructions, not captions.
- Use examples such as "`@Image1` is the identity reference for Lina; preserve her face, hair, and glasses."
- Omit any asset that does not carry a clear role in the current clip.
- Prefer fewer strong references over a crowded prompt with vague references.

## Frame Pinning

- Pin an image as the first frame when the opening composition must be exact.
- Pin an image as the last frame when a clip must land on a planned match frame.
- Chain clips by reusing the end frame of clip N as the first frame of clip N+1.
- State the pin role in the upload table and in the prompt body.
- Keep pinned-frame instructions concise so the prompt stays under target length.
- Use no-face identity anchors in match frames when continuity matters.
- Record spatial law with the frame, such as who stays frame-left or frame-right.

## Reference Caps

- For Seedance 2.0, plan around up to 12 total reference assets.
- Respect Seedance 2.0 lane caps of up to 9 images, 3 videos, and 3 audio files.
- Keep each Seedance 2.0 reference video at 15 seconds or shorter.
- Keep each Seedance 2.0 reference audio file at 15 seconds or shorter.
- For Seedance 2.5, expect roughly 50 reference assets when the UI exposes the option.
- Treat Seedance 2.5 as reference-to-video capable when the current UI exposes R2V.
- Verify the active model's upload counter before finalizing the upload table.
- Reduce references before shortening story beats when the UI rejects uploads.

## Prompt Box

- Treat the Dreamina prompt box as having a hard cap of 2000 characters.
- Preserve the exact over-limit error string: `文字描述超过了2000字`.
- Keep memento paste blocks at 1500 characters or fewer as the working target.
- Count the clip paste block only, not the surrounding Markdown notes.
- Compress by removing soft adjectives, redundant scene facts, and repeated roles.
- Keep load-bearing identity, action, camera, continuity, and audio instructions.
- Do not rely on Dreamina remembering prior clips.
- Make every clip prompt self-contained.

## Clip Lengths

- Use Seedance 2.0 for clips up to 15 seconds.
- Use Seedance 2.5 for 30-second standard single-pass clips when available.
- Use Seedance 2.5 180-second beta only when the UI visibly exposes it and the user accepts beta risk.
- Recommend multiple linked 2.0 clips for proven continuity and controllable rerolls.
- Recommend one 2.5 clip when the memory needs longer single-pass motion or many references.
- Match duration choice to story shape before writing the final prompt.

## Web Settings

- Set aspect ratio in the Dreamina web-app controls.
- Set clip duration in the Dreamina web-app controls.
- Never put aspect ratio in the prompt body.
- Never put duration in the prompt body.
- Put model, mode, aspect ratio, and duration in the Markdown settings line.
- Keep the paste block focused on reference roles, action, camera, continuity, and audio.

## Timing Language

- Avoid per-second timings in the prompt body.
- Use shot ordering instead of timestamps.
- Write "Start with...", "then...", and "end on..." when sequencing matters.
- Keep one clear camera move per shot.
- Avoid dense beat lists that read like an edit decision list.

## Model Choice

- Choose Seedance 2.0 as the proven default.
- Choose Seedance 2.0 when the user wants reliable 15-second reroll units.
- Choose Seedance 2.0 when references fit within the 12-asset planning envelope.
- Choose Seedance 2.5 when the user needs a longer single-pass clip.
- Choose Seedance 2.5 when the user needs many more references.
- Ask the user before switching models after prompts are drafted.

## Honesty And Moderation

- Report Dreamina refusals plainly to the user.
- Adjust the treatment with the user when moderation blocks a generation.
- Never silently swap a person's identity.
- Never silently change wardrobe, props, relationships, or place facts.
- Offer safer wording, fewer sensitive details, or a different framing only with user visibility.
- Preserve user intent while respecting the current platform boundary.
