---
name: memento
description: >-
  $memento, memento, memory film, "recreate this memory", "turn these photos
  into a film", personal photos to Dreamina/Seedance video prompts. Use to
  turn a user's own or consented personal-memory photos into a
  resumable per-memory project folder with source references, visual inventory,
  adaptive interview, optional generated sheets or micro-edits, and paste-ready
  Dreamina prompts. Do not use for generic video-prompt writing, fiction
  pipelines, impersonation/deepfake work, or arbitrary image editing outside a
  memory project.
---

# Memento

## Operating Contract

- Treat invocation as natural language, including implicit requests that match the description.
- Prefer the `request_user_input` structured-question tool for every user decision throughout the flow — interview batches, inventory confirmation, consent asks, model/format choices, and sheet approvals; give each question 2–6 options with the recommended answer first, labeled "(Recommended)". Fall back to plain chat questions when the tool is unavailable in the current session, and never ask the same thing twice.
- Keep all durable state in `memento/<slug>/memento.yaml` so any stage can resume or be skipped.
- Reference source photos in place by default; ask explicit consent before any copy into `sources/`.
- Ask explicit consent before sending selected photos to OpenAI image generation.
- State that Dreamina receives whatever the user later uploads there.
- Use the skill only for the user's own memories or consented participants.
- Preserve stated identity, wardrobe, props, relationships, and place facts unless the user changes them.
- Report platform or moderation refusals plainly; never silently swap facts to bypass a refusal.
- Generate English prompts and files unless the user explicitly asks otherwise.
- If a needed reference file is missing, report the exact path and avoid inventing its facts.

## Reference Routing

- Read [references/interview-guide.md](references/interview-guide.md) when entering S2 or when the user asks to revise the interview/treatment.
- Read [references/sheet-craft.md](references/sheet-craft.md) when entering S3, choosing raw photos vs rendered sheets, or writing sheet prompts.
- Read [references/micro-edit-loop.md](references/micro-edit-loop.md) when entering S3.5, using Cowart, or running chat-based micro-edits.
- Read [references/dreamina-video-craft.md](references/dreamina-video-craft.md) when entering S4 or S5 prompt revision.
- Read [references/dreamina-platform.md](references/dreamina-platform.md) when choosing model, mode, reference counts, frame pins, ratio, duration, tags, caps, or moderation guidance.

## State Shape

Use this shape as the minimal manifest; add compact notes only when needed.

```yaml
memory:
  title: ""
  slug: ""
  created_at: ""
  current_stage: "S0"
  status: "in_progress"
  treatment_confirmed: false
privacy:
  copy_sources_consent: false
  render_upload_consent: null
interview:
  treatment: ""
  boundaries: ""
sources:
  - id: "src01"
    path: "/absolute/or/user-provided/path.jpg"
    handling: "referenced"
    notes: ""
assets:
  - id: "asset01"
    type: "raw_photo"
    path: "/absolute/or/project/path.png"
    role: "identity reference for..."
    source_ids: ["src01"]
    approval_state: "proposed"
    dreamina_tag: ""
    prompt_char_count: null
clips:
  - id: "clip01"
    title: ""
    model: "Seedance 2.0"
    ratio: "16:9"
    duration: "15s"
    spatial_law: ""
    first_frame_asset: ""
    last_frame_asset: ""
    prompt_char_count: null
rendering:
  capability_probe:
    session_id: ""
    status: "unknown"
    checked_at: ""
    notes: ""
```

Use `approval_state: proposed | rendered | approved | rejected | skipped`.
Use `type: raw_photo | character_sheet | item_sheet | environment_sheet | base_frame | match_frame | micro_edit`.
Record prompt character counts for sheet prompts when useful and for every Dreamina clip prompt.

## S0 Start

1. Determine whether to start a new memory or resume an existing `memento/<slug>/memento.yaml`.
2. Slug the memory from the user's phrase, folder name, date, or concise title.
3. Use lowercase ASCII, hyphen separators, and a numeric suffix on collision.
4. Scaffold the project in the current workspace:

```text
memento/<slug>/
  memento.yaml
  .gitignore
  sources/
  sheets/
```

5. Create `.gitkeep` files inside `sources/` and `sheets/` when needed.
6. Write `.gitignore`:

```gitignore
sources/*
sheets/*
*.jpg
*.jpeg
*.png
*.heic
*.webp
*.mov
*.mp4
!sources/.gitkeep
!sheets/.gitkeep
!memento.yaml
!dreamina_prompts.md
```

7. Record user-provided media paths in `memento.yaml` with `handling: referenced`.
8. Copy source media into `sources/` only after explicit consent, then update `handling: copied`.
9. Tell the user what was created, which source paths remain referenced in place, and which stage comes next.

## S1 Look

1. Load each source photo with the available visual inspection tool before describing it.
2. Present an inventory table before proposing any generated asset.

| Kind | Candidate | Source evidence | Distinguishing anchors | Environment / light / mood | Proposed role | Raw photo vs render | Reason / risk |
|---|---|---|---|---|---|---|---|

3. Include people, distinguishing anchors, key items, environments, light, mood, and continuity anchors.
4. Propose raw photos as the default identity reference when identity and wardrobe already match.
5. Propose rendered sheets only for a named control problem, user-requested stylization, or missing/entangled visual evidence.
6. Ask the user to confirm or correct the inventory (structured ask: one question per contested row, or one confirm-all question when the table is clean).
7. Update `sources`, `assets`, and `memory.current_stage` in `memento.yaml`.

## S2 Interview

1. Read [references/interview-guide.md](references/interview-guide.md).
2. Ask the batch (at most five questions) through the `request_user_input` tool when available — one call, recommendations as first options; otherwise one numbered batch in chat.
3. Skip anything the user already gave.
4. Include recommendations or practical defaults in each question.
5. Offer "surprise me" when the user wants delegated treatment.
6. Cover only missing decisions: memory beats, intent, must-happen moments, emotional landing, clip count, model, duration, ratio, style anchor, audio direction, and safety/consent boundaries.
7. Recommend scope from story shape: one beat usually means one clip; a journey, reveal, or location change usually means two or three clips chained by match frames.
8. Summarize the proposed treatment and wait for confirmation or correction.
9. Save decisions under `memory`, `clips`, `interview`, and `privacy` in `memento.yaml`.

## S3 Sheets

1. Read [references/sheet-craft.md](references/sheet-craft.md).
2. Open S3 with a once-per-session capability probe before promising rendered sheets.
3. Record the probe under `rendering.capability_probe` with a session identifier, timestamp, status, and notes.
4. Ask for render-upload consent unless already recorded (structured ask when the tool is available).
5. Load the relevant local photo into visual context with `view_image` before any edit or reference render.
6. Treat filesystem paths in prompts as unreliable input by themselves.
7. Use the built-in image generation path as prompt-only: no exposed mask, seed, dimensions, model, or destination path.
8. Do not name an image model; the current runtime does not surface one.
9. Test one small reference-preserving render from a viewed photo when the user consents.
10. Treat text-to-image and multi-image reference as available only after the current-session probe succeeds.
11. For multi-image reference, load every source with `view_image` and label each image's role explicitly in the prompt.
12. Use prose aspect cues such as `wide 16:9 landscape framing`; do not promise exact pixel dimensions.
13. Expect default text-to-image dimensions to vary; the verified runtime rendered about 1536x1024.
14. If rendering is unavailable, fails, or the user declines upload consent, say so plainly and continue with raw photos as Dreamina references.
15. Do not offer a Dreamina web-app fallback for sheet rendering.
16. Choose each asset adaptively: raw photo, character sheet, item sheet, environment sheet, base frame, or match frame.
17. Render only the smallest sheet or frame that solves the next continuity problem.
18. Show every generated result in-session and ask for approval before downstream use.
19. Move only proven outputs into `memento/<slug>/sheets/`.
20. Update `assets`, source ids, roles, approval state, accepted prompt count when relevant, and `memory.current_stage`.

### S3 Output Resolution

Use this procedure for every generated image output.

1. Create a marker file immediately before the render, such as `memento/<slug>/.render-marker`.
2. Run the render only after the marker timestamp exists.
3. Search `${CODEX_HOME:-$HOME/.codex}/generated_images/` with `find ... -newer <marker>`.
4. Treat the directory as cumulative across requests and sessions.
5. Prefer an explicit returned output path when the tool provides one, but still visually verify it.
6. Inspect every candidate newer than the marker by dimensions and visual content.
7. Never pick the newest file blindly.
8. Ask the user only when candidates remain ambiguous after inspection.
9. Move the confirmed output into `sheets/` with a stable role/version name.
10. View the moved file before marking it `approved` or using it in a Dreamina upload table.

## S3.5 Micro-Edit Loop

1. Read [references/micro-edit-loop.md](references/micro-edit-loop.md).
2. Probe Cowart before using it: callable `get_cowart_selection`, callable `insert_cowart_image`, and a reachable local canvas service.
3. If Cowart is present, place working images side by side and keep originals plus annotations visible.
4. If Cowart is absent, offer the companion install described in the reference.
5. If the user declines Cowart, run chat-based iteration with the same identity and continuity guards.
6. Load the source or annotated screenshot into visual context with `view_image` before any edit render.
7. Set expectations before the first edit: the render can preserve composition, framing, and layout, but it re-renders the whole image generatively.
8. Treat detail drift outside the requested region as normal for the current runtime.
9. Compare source and revision side by side instead of promising surgical one-region edits.
10. Iterate one specific visual change at a time when identity or continuity risk is high.
11. Promote only user-approved clean revisions into `sheets/`.
12. Update the relevant asset path, role, approval state, and Dreamina tag in `memento.yaml`.

## S4 Prompts

1. Read [references/dreamina-video-craft.md](references/dreamina-video-craft.md).
2. Read [references/dreamina-platform.md](references/dreamina-platform.md).
3. Write `memento/<slug>/dreamina_prompts.md`.
4. Render the full Markdown in-session with fenced prompt blocks.
5. Include a header with title, concept line, shoot-order checklist, and settings line.
6. Use this settings line shape: `model · All-in Reference · ratio · duration`.
7. For each clip, include an upload table with `Tag -> File -> Role`.
8. Include first-frame and last-frame pins in the upload table when used.
9. Point upload table files only at approved `sheets/` assets or recorded source paths.
10. Write exactly one fenced `text` block per clip.
11. Keep every clip prompt block at 1500 characters or fewer.
12. Report each block's character count next to the block and record it in `memento.yaml`.
13. Include Notes covering platform caps, the film's spatial law, and reroll guidance.
14. Use references as anchors; write prompt prose for state increments, action, camera, atmosphere, and audio.
15. Compress any overlong block before presenting it.

## S5 Iterate

1. Read the prompt and platform references again when changing Dreamina prompt content or upload strategy.
2. Identify the smallest useful fix from the user's reported result.
3. Prefer one targeted action: compress a block, adjust a reference role, regenerate one sheet or panel, re-pin a frame, or clarify the spatial law.
4. Update `dreamina_prompts.md` and `memento.yaml` together.
5. Keep upload tables, asset roles, approval states, and character counts aligned.
6. Report any Dreamina or image-generation refusal plainly.
7. Revise with the user when moderation blocks a generation.
8. Never silently change identity, wardrobe, props, relationships, or scene facts.
9. Ask before rerunning broad stages.
