# Micro-edit Loop

## Table of Contents

- [1. Detect Cowart](#1-detect-cowart)
- [2. When Cowart Is Absent](#2-when-cowart-is-absent)
- [3. Set Up The Canvas](#3-set-up-the-canvas)
- [4. Treat The Screenshot As The Brief](#4-treat-the-screenshot-as-the-brief)
- [5. Regenerate With Memento Guards](#5-regenerate-with-memento-guards)
- [6. Insert The Revision Beside The Anchor](#6-insert-the-revision-beside-the-anchor)
- [7. Iterate](#7-iterate)
- [8. Approval And Export](#8-approval-and-export)

Cowart credit: this workflow integrates behaviorally with [cowart](https://github.com/zhongerxin/cowart), a companion Codex canvas plugin.

Do not vendor, fork, copy, or adapt cowart code into the public memento plugin unless a license grant exists. Use only the plugin boundary, MCP tools, and documented behavior.

## 1. Detect Cowart

Probe before opening S3.5.

1. Confirm the cowart MCP tools are callable: `get_cowart_selection` and `insert_cowart_image`.
2. Confirm the local service is reachable at `http://127.0.0.1:43217`.
3. If Vite selected a fallback port, use the actual session URL, such as `http://127.0.0.1:43218`.
4. Treat cowart data as project-local state; the canvas normally lives under the active project's `canvas/` directory.
5. If the MCP tools exist but the service is down, ask the user to open or start the cowart canvas for this project.
6. If the service is visible but the MCP tools are missing, treat cowart as absent in this conversation.

Do not start the canvas loop from memory or assumption. Probe first, then choose the canvas path or the absent path.

## 2. When Cowart Is Absent

Offer the install in-session before degrading.

```bash
mkdir -p ~/plugins
git clone https://github.com/zhongerxin/cowart ~/plugins/cowart
cd ~/plugins/cowart
npm install && npm run build
codex plugin marketplace add ~
codex plugin add cowart@personal
```

After installing, tell the user to start a new Codex conversation so the cowart skills and MCP tools load cleanly.

If the user declines, switch to chat-based iteration.

1. Ask the user to describe the target region and requested change in words.
2. Keep the same memento guards that the canvas loop would use.
3. For character work, always append the `Preserve exactly:` line.
4. For place, object, light, or base-frame edits, change only what the user names.
5. Do not invent visual annotation evidence that the user did not provide.
6. Explain that chat iteration still works, but it lacks arrow-tip targeting and the side-by-side canvas trail.

## 3. Set Up The Canvas

Place the working image or images on the cowart canvas before asking for micro-edits.

1. Put the current visual under revision on the canvas.
2. If several images are active, arrange them side by side.
3. Use `insert_cowart_image` when an image needs to be added to cowart.
4. Leave open space to the right for future revisions.
5. Never move, hide, or delete originals just to make room.
6. Never remove annotations; they are part of the visible edit history.

When possible, ask the user to select the source image or frame before the round begins. Use `get_cowart_selection` only to identify a placement anchor, not to infer the requested edit.

## 4. Treat The Screenshot As The Brief

The user performs the markup.

1. The user draws arrows and short notes around the target region.
2. The user screenshots the annotated region and sends that screenshot back into the session.
3. Treat that screenshot as the authoritative edit brief for the round.
4. If several screenshots arrive, process them separately unless the user explicitly combines them.
5. The arrow tip, circled area, or marked region defines where a note applies.
6. Read visible labels and nearby notes as the desired change.
7. Ignore editor chrome, toolbars, cursors, blue selection outlines, resize handles, and unrelated neighboring images.
8. If the screenshot is too cropped, obstructed, or low-resolution to serve as a base, ask for a cleaner screenshot or original export of that specific image.

Do not auto-capture cowart and do not scan the whole canvas for intent. The user-supplied screenshot is the edit brief.

## 5. Regenerate With Memento Guards

Use the built-in image flow available in the current Codex environment.

Layer memento's identity and continuity rules on top of cowart's annotation-edit contract.

1. Apply only the changes named by the annotation screenshot.
2. Preserve the source image's composition, subject, aspect ratio, and style unless an annotation asks otherwise.
3. For character edits, always append the `Preserve exactly:` line.
4. Use that line to lock identity-critical details: face, body, hair, wardrobe anchors, pose logic, and approved likeness traits.
5. For environment edits, use anchor-don't-restate: keep the place and camera logic anchored, and change only what the annotation names.
6. For item edits, preserve shape, scale, material logic, and orientation unless the note asks otherwise.
7. For base-frame edits, preserve continuity anchors and the recorded spatial law unless the annotation explicitly updates them.
8. Always strip annotation artifacts from the output.

Annotation artifacts include arrows, labels, circled marks, selection outlines, resize handles, pointer shapes, editor UI, and toolbars. The result must be a clean revised bitmap.

Resolve the actual generated image path before reinserting it. Use a returned image path when available; if checking `$CODEX_HOME/generated_images/`, confirm the file belongs to the current request.

## 6. Insert The Revision Beside The Anchor

Insert the clean revision with `insert_cowart_image`.

1. Anchor on the selected source image or selected source frame when available.
2. Place the revision to the right of the anchor.
3. Use about `40` canvas units of margin.
4. Match the anchor's displayed width and height.
5. If that position overlaps existing content, keep stepping right by the anchor width plus about `40` units.
6. If no anchor is clear, place the revision in a nearby empty area without covering any original or annotation.

Never replace the source image during the loop. Never move, hide, delete, reparent, or reorder the original image, original frame, or annotation shapes. The canvas must keep a visible before/after trail.

When calling `insert_cowart_image`, pass the actual cowart URL, active project directory, generated image path, selected anchor id when known, `placement: "right"`, `margin: 40`, and `matchAnchor: true`.

After insertion, visually confirm that the revision appears beside the source, old annotations remain visible, and the new bitmap contains no markup or editor interface residue.

## 7. Iterate

Repeat until the user approves a revision.

1. Keep every attempt visible on the canvas.
2. Ask the user to annotate the latest relevant image for the next round.
3. Treat each new screenshot as a fresh authoritative brief.
4. Keep character, item, environment, and base-frame guards active on every generation turn.
5. Prefer one specific visual change per round when identity or continuity risk is high.

If annotations conflict, generate the most literal combined interpretation only when it is reasonable; otherwise ask which mark should win.

## 8. Approval And Export

When the user approves a revision, promote that bitmap into the memento memory.

1. Export or move the approved revision into the memory's `sheets/` folder.
2. Use a stable, descriptive filename that matches the asset role.
3. Update `memento.yaml` so the approved sheet path, role, and current state are recorded.
4. Point later Dreamina upload tables at the approved `sheets/` asset.
5. Leave the cowart canvas trail intact as review context.

The approved clean image, not the annotated screenshot, is the sheet asset.
