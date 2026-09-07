# Indie Game Marketing Skills

Agent skills for planning and auditing the marketing of a small, primarily
Steam-distributed indie game from concept selection through post-launch.

The repository is intentionally opinionated. It treats genre, scope, visual
identity, and the trailer-worthy vertical slice as marketing decisions made
before full production—not cleanup performed after the game is finished.
It also treats announcements, demo launches, festivals, release-date reveals,
and launch as scarce marketing beats that should be prepared and coordinated
rather than allowed to pass quietly.

## Skills

- `plan-indie-game-marketing`: build and maintain the end-to-end roadmap.
- `audit-steam-store-page`: audit positioning, capsules, media, tags,
  localization, and demo presentation.
- `optimize-steam-tags`: build an accurate ordered tag profile around the
  players of the right similar games.
- `review-game-trailer`: plan or review gameplay trailers and map their visual
  promises back to the build.

The lifecycle planner also covers base and regional pricing, early game and
store-page localization, Steam's Personal Calendar and launch visibility, an
official game site with a downloadable press kit, an itch.io demo, and a
browser playtest build whose optional diagnostics feed a privacy-conscious
incident database.

## Install the skills

Clone this repository somewhere that will remain on the machine:

```sh
git clone https://github.com/GarrettPetersen/indie-game-marketing-skills.git /absolute/path/to/indie-game-marketing-skills
```

Each directory under `skills/` is an independent skill. Link the individual
skill directories, not the repository root.

### Use them in one game repository

For one game, link them into that game's `.agents/skills` directory:

```sh
cd /absolute/path/to/game
mkdir -p .agents/skills
ln -s /absolute/path/to/indie-game-marketing-skills/skills/plan-indie-game-marketing .agents/skills/plan-indie-game-marketing
ln -s /absolute/path/to/indie-game-marketing-skills/skills/audit-steam-store-page .agents/skills/audit-steam-store-page
ln -s /absolute/path/to/indie-game-marketing-skills/skills/optimize-steam-tags .agents/skills/optimize-steam-tags
ln -s /absolute/path/to/indie-game-marketing-skills/skills/review-game-trailer .agents/skills/review-game-trailer
```

This is the preferred scope when the skills should apply only while working on
that game. Absolute symlinks are local machine configuration; do not commit
them to the game repository unless every collaborator intentionally uses the
same checkout layout. A team that wants versioned installation should vendor
or submodule this repository instead.

### Use them for every project

To make the skills available globally in Codex, link them into the user's Codex
skills directory:

```sh
mkdir -p ~/.codex/skills
ln -s /absolute/path/to/indie-game-marketing-skills/skills/plan-indie-game-marketing ~/.codex/skills/plan-indie-game-marketing
ln -s /absolute/path/to/indie-game-marketing-skills/skills/audit-steam-store-page ~/.codex/skills/audit-steam-store-page
ln -s /absolute/path/to/indie-game-marketing-skills/skills/optimize-steam-tags ~/.codex/skills/optimize-steam-tags
ln -s /absolute/path/to/indie-game-marketing-skills/skills/review-game-trailer ~/.codex/skills/review-game-trailer
```

Do not install the same skill at both scopes. Project-local skills take context
with the game; global skills are more convenient when working across several
games. After adding the links, start the next Codex turn or task so skill
discovery refreshes.

Because these are symlinks, updating the clone updates the installed skills:

```sh
git -C /absolute/path/to/indie-game-marketing-skills pull --ff-only
```

## Use the skills

Mention a skill explicitly when you want a particular workflow:

- `$plan-indie-game-marketing` for a full roadmap, marketing calendar, next
  action, pricing decision, localization plan, demo strategy, festivals,
  creator outreach, or launch preparation;
- `$audit-steam-store-page` for a publish-readiness or conversion audit of an
  upcoming or live Steam page;
- `$optimize-steam-tags` for tag ordering, comparable-game research, Tag Wizard
  diagnosis, or fixing the public similar-game neighborhood; and
- `$review-game-trailer` for a trailer concept, shot plan, timecoded review, or
  revision plan using authentic gameplay.

Codex may also select them automatically when a request clearly matches their
descriptions. Give it the game repository, current stage, intended date, known
deadlines, store URL, and available evidence. It should ask only for missing
facts that affect the next decision.

These skills plan, audit, organize, and implement internal work. They do not
grant permission to publish a page, send outreach, submit a form, release a
demo, or launch a game. Codex must obtain explicit confirmation immediately
before an external action.

## Repository layout

- `skills/*/SKILL.md` contains each skill's entry instructions.
- `skills/*/references/` contains detailed workflows loaded only when relevant.
- `skills/*/agents/openai.yaml` contains Codex-facing display metadata.
- `SOURCES.md` records which conclusions come from official rules,
  practitioner guidance, or firsthand project evidence.

## Human-authorship policy

These skills must not author original public-facing marketing copy or
generative key art. The agent asks the developer for the exact source-language
words that will reach players, press, creators, or platform reviewers. It may
organize approved words, transcribe human speech, insert verified factual
fields into a human-written template, and flag errors, but it must not quietly
rewrite the developer into an artificial marketing voice.

AI-assisted translation is a deliberate exception. An agent may faithfully
translate exact human-authored source text so the game, Steam page, website,
and assets containing text can launch in priority languages instead of waiting
for a later localization budget. It must preserve claims and voice, track the
machine-translated status internally, run localization QA, and route the
highest-impact text to a native editor when feasible. This exception permits
translation, not invention or synthetic localization-specific marketing copy.

Steam capsule art and other key art must be made by a human developer or
artist, or commissioned from one. Agents may audit, crop, resize, export, and
assemble supplied human-made layers; they may not generate the underlying art.

There is also a narrow exception for non-promotional privacy, consent, and
telemetry boilerplate. An agent may draft it from a verified inventory of what
the product actually collects and does, but may not invent practices, omit a
material fact, or use manipulative consent language. The developer must review
and approve it, with qualified legal review when warranted. This exception does
not apply to store copy, outreach, press releases, social posts, or any other
marketing text.

## Sources and limits

The workflows synthesize:

- firsthand lessons from shipping and marketing an indie Steam game;
- BiteMe Games' public development and marketing videos;
- Chris Zukowski's How To Market A Game articles and datasets; and
- current Steamworks documentation for platform rules.

Advice is labelled by source type where that distinction matters. Platform
rules and dated festival requirements must be checked again at the time of
use. See [SOURCES.md](SOURCES.md) for the initial research ledger.

This is not a promise of commercial success. It is a system for making the
important decisions early, producing honest marketing evidence, and avoiding
preventable launch mistakes.
