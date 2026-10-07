---
name: review-game-trailer
description: Plan, audit, or revise an indie game's announcement, Steam, demo, launch, or short-form trailer using authentic gameplay, readable pacing, truthful feature evidence, competent play, and clean audio. Use for trailer-first vertical slices, shot lists, timecoded reviews, or edit decisions; do not use to write public voiceover or title cards or to generate key art.
---

# Review Game Trailer

A trailer is compressed proof of the game's fantasy, genre, loop, variety, and
payoff. It is also a production test: if an important promise cannot be shown
with compelling authentic gameplay, the build may not be ready to market.

## Human-authorship invariant

Never draft, rewrite, or polish original-language voiceover, title cards,
captions, video titles, descriptions, calls to action, or other audience-facing
words. Ask the developer for exact text or exact recorded human narration and
preserve it. Verbatim transcription and caption timing are allowed because the
words originate with a human. Flag errors and ask the human to revise or
rerecord.

Translation is an explicit exception: when the developer supplies or approves
human-authored source copy and asks for localization, the agent may translate
that copy into the requested languages. Preserve the source meaning, claims,
tone, placeholders, and intended reading length; do not add new claims or
silently rewrite the English source. The translated text should be treated as
localized human-authored copy, not as permission to invent new public wording.

Do not generate capsule art, key art, fake gameplay, or synthetic visual scenes
to fill gaps. Use authentic current-build gameplay and properly licensed
human-made materials. Mechanical editing, compositing, grading, captions,
sound mixing, and export are allowed.

The lifecycle skill's narrow exception for factual privacy, consent, and
telemetry boilerplate does not permit agent-written trailer wording.

## Select the trailer's job

Identify whether this is an announcement, primary Steam trailer, demo trailer,
festival cut, launch trailer, press asset, or vertical social video. State the
audience, desired action, required aspect ratio, maximum duration, delivery
specifications, and whether the viewer already knows the game.

For preproduction, read
[references/trailer-first-development.md](references/trailer-first-development.md).
For an existing cut, read
[references/shot-audit.md](references/shot-audit.md).

## Plan from beats to footage

Create a visual beat sheet before a timeline. Each beat must have:

- the player-facing idea being proved;
- authentic footage that proves it;
- the visible action or change the viewer should notice;
- enough duration to understand that action;
- a reason for its position in the escalation; and
- a build requirement or capture scenario if the footage does not exist.

Do not cover an implementation gap with public copy. Put the missing proof back
into the vertical-slice or capture backlog.

Before recording each shot, wait until its required assets are loaded, decoded,
uploaded to the renderer, and fully visible. Include scenery such as coral and
terrain details, ships, city art, portraits, fonts, and assets needed along the
planned camera movement. A generic game-ready flag or fixed delay is not proof.
Use unrecorded warm-up renders to confirm the intended asset set is complete
across consecutive frames, keeping the gameplay clock paused so staged actions
do not advance. Bound the wait and fail an unready capture rather than recording
placeholders or asset pop-in. This applies to archival builds as well.

## Review the rendered video

Inspect the actual master frame by frame around every cut and overlay boundary,
with sound. Check native dimensions, aspect ratio, frame rate, codecs, duration,
audio peaks, silence, caption boundaries, and delivery size.
Inspect each shot's opening frames and camera/scene changes for assets appearing
late; reject and recapture shots with loading pop-in.

Return a timecoded table with issue, evidence, impact, and edit instruction.
Do not provide replacement public wording. Distinguish a bad source capture
from a bad edit so the root cause is fixed.

## Authorization boundary

Rendering and local review do not authorize uploading, scheduling, publishing,
replacing, or deleting a public video. Obtain explicit confirmation immediately
before each external action.
