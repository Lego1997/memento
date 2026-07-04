# memento

## What is memento

memento turns photos of a real memory into a small, resumable Codex project: it inventories the photos, plans character, item, and environment sheets plus base or match frames when they help, interviews the user for the missing story decisions, and writes paste-ready Dreamina/Seedance prompts for the final clips. The whole workflow lives inside Codex, from source-photo handling and image-generation consent through the final `dreamina_prompts.md`.

## Install

memento is a plain Codex skill — clone the repo and copy the skill folder into your Codex skills directory:

```bash
git clone https://github.com/Lego1997/memento
mkdir -p ~/.agents/skills
cp -R memento/skills/memento ~/.agents/skills/
```

To receive future updates via `git pull`, symlink instead of copying:

```bash
ln -s "$(pwd)/memento/skills/memento" ~/.agents/skills/memento
```

For a single project only, copy the folder into that repo's `.agents/skills/` instead. Then start a fresh Codex conversation and invoke `$memento`, or ask naturally to turn your memory photos into a short Dreamina film.

## Requirements

- A Codex runtime with built-in image generation available. In practice, this means a ChatGPT paid sign-in for image rendering inside Codex.
- A Dreamina account for the final video generations.
- Optional: the bundled `imagegen` skill includes an API script path for some environments; that path needs `OPENAI_API_KEY` if you choose to use it.
- There is deliberately no web-app backup path for sheet rendering. If Codex image generation is unavailable or declined, memento continues with raw photos and approved existing assets as Dreamina references.

## Privacy

Source photos are referenced in place by default, not copied, unless you explicitly consent to copying them into the per-memory project. Each memory project writes a local `.gitignore` that excludes source media, rendered sheets, still images, and video files while allowing `memento.yaml` and `dreamina_prompts.md` to be tracked. Photos you allow Codex to render from are sent to OpenAI, and anything you later upload to Dreamina is sent to ByteDance/Dreamina. Use memento for your own memories and consented participants only; get consent from people in the photos, and do not use it for impersonation, deepfakes, or swapping a real person's identity into a scene they did not agree to.

## Companion: Cowart

Cowart adds a canvas micro-edit loop for S3.5: memento can place source images and revisions side by side, preserve the visible edit trail, and use the user's annotated screenshot as the precise brief for one targeted generative revision at a time. One-command install:

```bash
mkdir -p ~/plugins && git clone https://github.com/zhongerxin/cowart ~/plugins/cowart && cd ~/plugins/cowart && npm install && npm run build && codex plugin marketplace add ~ && codex plugin add cowart@personal
```

Cowart currently has no license, so memento integrates with it behaviorally and vendors none of its code. Credit: https://github.com/zhongerxin/cowart

## Usage

Start with `$memento` and the local paths to the photos for one memory. memento creates or resumes `memento/<slug>/memento.yaml`, inventories the visible evidence, asks one compact interview batch, chooses raw photos versus rendered sheets only where they solve a continuity problem, optionally runs a Cowart or chat micro-edit loop, and writes `memento/<slug>/dreamina_prompts.md` with upload tables and prompt blocks for Dreamina. See the sanitized fictional walkthrough in [examples/walkthrough.md](examples/walkthrough.md).

## Limits

Image turns consume ChatGPT plan usage noticeably faster than text turns. Dreamina's prompt box has a 2000-character hard cap, while memento targets 1500 characters or fewer per paste block; Seedance 2.0 reference videos are capped at 15 seconds. Edit renders are reference-preserving but generative: even a small requested edit re-renders the whole image, so memento treats revisions as reviewable candidates rather than surgical pixel edits.
