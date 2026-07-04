# Memento Walkthrough

This is a sanitized, fictional example. Maya and Ken are invented people, the night market is invented, and the file names below are illustrative project paths, not real photos or personal data.

## Setup

User request:

```text
Use $memento for these photos of Maya and Ken eating snacks at a night market. Make a short Dreamina film from it.
```

Fictional source paths recorded as referenced-in-place:

| Source ID | Path | Handling | Notes |
|---|---|---|---|
| `src01` | `sources/night-market-wide-fictional.jpg` | referenced | wide crowd and stall-light context |
| `src02` | `sources/maya-ken-stall-fictional.jpg` | referenced | clear identity, wardrobe, and side order for Maya and Ken |
| `src03` | `sources/paper-lantern-bag-fictional.jpg` | referenced | close view of the small paper snack bag |

## S1 Inventory

| Kind | Candidate | Source evidence | Distinguishing anchors | Environment / light / mood | Proposed role | Raw photo vs render | Reason / risk |
|---|---|---|---|---|---|---|---|
| Person | Maya | `src02` | frame-left friend, visible face, jacket sleeve, tote strap | warm stall light, crowded aisle, casual smile | identity and wardrobe anchor | raw photo | identity and wardrobe already match the memory; rendering would add drift |
| Person | Ken | `src02` | frame-right friend, visible face, short sleeve cuff, paper cup | same stall light and aisle | identity and wardrobe anchor | raw photo | identity and wardrobe are clear in the same source photo |
| Item | paper snack bag | `src03` | small folded top, printed lantern mark, oil-darkened bottom edge | tabletop under neon and grill light | shared prop across both clips | render item sheet | prop must stay recognizable during the handoff and bite |
| Place | night-market lane | `src01`, `src02` | stall counter frame-left, red lantern string overhead, vendor sign blur frame-right | mixed neon, grill smoke, wet pavement reflections | environment reference | render clean plate | source photos are crowded; people-free plate helps Dreamina preserve the walking path |
| Frame | opening composition | `src02` plus `src01` | Maya frame-left, Ken frame-right, stall counter left, lantern string overhead | warm handheld night-market feel | first-frame pin for Clip 1 | render base frame | stronger body placement and side law than raw photo alone |
| Frame | bag handoff close-up | `src03` plus sleeve anchors from `src02` | Maya's jacket sleeve enters from lower-left, Ken's cuff enters from lower-right, bag centered | anonymous market blur behind hands | match frame between clips | render match frame | no-face hinge can chain clips while protecting identity continuity |

Inventory confirmation:

```text
User confirms: Maya stays frame-left, Ken stays frame-right, the paper snack bag is the linking prop, and the film should stay wordless.
```

## S2 Interview

Question batch:

1. What happened in this memory: key beats, when/where, and who matters? Recommendation: keep it to 3 visible beats and name only the people or objects Dreamina must preserve.
2. Should the film be faithful, or an idealized dream version? Recommendation: use faithful if the photos already match; use dream version if the feeling matters more than literal accuracy. Also name the must-happen beat and final emotion.
3. What format fits the story? Recommendation: one beat becomes 1 clip; a journey becomes 2-3 clips chained by match frames; use 16:9 by default; use Seedance 2.0 for proven 15s clips.
4. What is the one visual anchor and audio direction? Recommendation: choose handheld night vlog for these photos; use diegetic-only, wordless, no score by default.
5. Would you rather say "surprise me"? Recommendation: choose this if you want memento to propose the full treatment from the photos, then you can correct it before any rendering or Dreamina prompt work.

User answers:

1. Maya and Ken found the lantern stall, shared one paper bag of skewers, and laughed after the first bite.
2. Faithful, but cleaner than the photos. The must-happen beat is the bag handoff. The final feeling should be calm and funny.
3. Two 15-second clips in 16:9, chained by a close-up match frame.
4. Warm handheld night-market travel diary. Wordless, diegetic sound only, no score.
5. Do not use surprise me; use the answers above.

Treatment summary:

```text
Two wordless Seedance 2.0 clips. Clip 1 starts at the stall and ends on a no-face match frame of both hands holding the paper snack bag. Clip 2 starts on that same match frame and lands on Maya and Ken sharing the first bite under the lanterns. Maya remains frame-left, Ken remains frame-right, and the paper snack bag bridges both clips.
```

## S3 Sheet List

| Asset ID | File | Type | Decision | Source IDs | Role | Approval |
|---|---|---|---|---|---|---|
| `asset01` | `sources/maya-ken-stall-fictional.jpg` | raw photo | use raw | `src02` | identity and wardrobe reference for Maya and Ken | approved |
| `asset02` | `sheets/item-paper-snack-bag-v01.png` | item sheet | render | `src03` | clean prop reference for the folded snack bag and lantern mark | approved |
| `asset03` | `sheets/env-night-market-lane-v01.png` | environment sheet | render | `src01`, `src02` | people-free lane plate with stall counter, lanterns, wet pavement | approved |
| `asset04` | `sheets/base-frame-clip01-v01.png` | base frame | render | `src01`, `src02`, `src03` | opening composition for Clip 1 | approved |
| `asset05` | `sheets/match-frame-bag-handoff-v01.png` | match frame | render | `src02`, `src03` | shared last frame of Clip 1 and first frame of Clip 2 | approved |

Adaptive notes:

- Raw photo beats character sheet for Maya and Ken because identity, wardrobe, and side order are already clear.
- The item sheet is worth rendering because the paper snack bag must stay recognizable while hands move.
- The environment sheet is worth rendering because the source lane is crowded and Dreamina needs a clean walking path.
- The match frame avoids face drift at the clip boundary by using sleeves, hands, and the centered bag as anchors.

## Final `dreamina_prompts.md` Sample

# Maya and Ken Night Market

Concept: two friends share a paper snack bag at a fictional night market, moving from stall discovery to the first bite.

Shoot order:

- [ ] Generate Clip 1 first.
- [ ] Save the approved final frame as `sheets/match-frame-bag-handoff-v01.png` if Dreamina needs a fresh extracted pin.
- [ ] Generate Clip 2 with the same match-frame file as its first-frame pin.

Settings: `Seedance 2.0 - All-in Reference - 16:9 - 15s`

## Clip 1 - Lantern Stall Handoff

Upload references:

| Tag | File | Role |
|---|---|---|
| `@Image1` | `sources/maya-ken-stall-fictional.jpg` | identity and wardrobe reference for Maya frame-left and Ken frame-right |
| `@Image2` | `sheets/env-night-market-lane-v01.png` | environment plate for the stall counter, lantern string, wet pavement, and crowd spacing |
| `@Image3` | `sheets/item-paper-snack-bag-v01.png` | prop reference for the folded paper snack bag |
| `@Image4` | `sheets/base-frame-clip01-v01.png` | first-frame pin for the opening stall composition |
| `@Image5` | `sheets/match-frame-bag-handoff-v01.png` | last-frame pin for the handoff match frame |

Prompt:

```text
Use @Image1 as the identity and wardrobe reference for Maya on frame-left and Ken on frame-right. Use @Image2 as the night-market lane layout. Use @Image3 as the paper snack bag prop. Start exactly on @Image4 as the first frame: Maya stands frame-left near the stall counter, Ken stands frame-right, lanterns hang above them. End exactly on @Image5 as the last frame: Maya's sleeve enters from lower-left, Ken's cuff enters from lower-right, and both hands hold the centered paper snack bag.

Style: warm handheld night-market travel diary, medium-close phone-vlog framing, available stall light, soft grain, gentle handheld sway. Strictly adhere to facial details, maximum facial consistency.

Medium handheld follow, one continuous shot, no cuts, no zoom. Maya stays frame-left and lifts the bag from the counter; Ken stays frame-right and steadies the folded top. Maya glances at Ken, Ken lowers his eyes to the bag, and both hands meet at frame center for the pinned handoff. Each person appears only once in the whole frame; do not generate duplicate or identical-looking people.

Audio diegetic only: paper crinkles under their hands, oil snaps on the grill, vendors murmur behind the camera; no score.
```

Characters: 1,208

## Clip 2 - First Bite Under Lanterns

Upload references:

| Tag | File | Role |
|---|---|---|
| `@Image1` | `sheets/match-frame-bag-handoff-v01.png` | first-frame pin for the shared bag handoff |
| `@Image2` | `sources/maya-ken-stall-fictional.jpg` | identity and wardrobe reference for Maya frame-left and Ken frame-right |
| `@Image3` | `sheets/env-night-market-lane-v01.png` | environment plate for the lantern lane and wet pavement |
| `@Image4` | `sheets/item-paper-snack-bag-v01.png` | prop reference for the folded paper snack bag |

Prompt:

```text
Start exactly on @Image1 as the first frame: Maya's sleeve enters from lower-left, Ken's cuff enters from lower-right, and both hands hold the centered paper snack bag. Use @Image2 as the identity and wardrobe reference for Maya on frame-left and Ken on frame-right. Use @Image3 as the night-market lane layout. Use @Image4 as the paper snack bag prop.

Style: warm handheld night-market travel diary, medium-close phone-vlog framing, available stall light, soft grain, gentle handheld sway. Strictly adhere to facial details, maximum facial consistency.

Medium-close handheld follow, one continuous shot, no cuts, no zoom. Maya stays frame-left and pinches one skewer from the bag. Ken stays frame-right and keeps the bag steady at chest height. Maya takes the first bite, lowers her shoulders, and covers a small laugh with her free hand. Ken looks at the bag, then at Maya, and smiles without stepping across the center line. Each person appears only once in the whole frame; do not generate duplicate or identical-looking people.

Audio diegetic only: skewer paper rustles in the foreground, nearby grill oil snaps, a stall fan rattles above the counter; no score.
```

Characters: 1,169

## Notes

- Dreamina prompt text hard cap: 2000 characters. memento target: 1500 characters or fewer per paste block.
- Seedance 2.0 reference videos, if used, must be 15 seconds or shorter; this example uses images only.
- Spatial law: Maya stays frame-left, Ken stays frame-right, and the paper snack bag bridges both clips.
- Frame pin law: Clip 1 ends exactly on `@Image5`; Clip 2 starts exactly on the same file as `@Image1`.
- Wordless rule: no dialogue, no voice-over, no laughter track, and no score.
- Smallest reroll lever: if the side order drifts, strengthen the frame-left/frame-right sentence; if the bag changes shape, tighten only the `@Image4` role sentence.
