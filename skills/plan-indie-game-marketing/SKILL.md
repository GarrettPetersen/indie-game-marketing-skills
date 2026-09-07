---
name: plan-indie-game-marketing
description: Plan and maintain an evidence-based marketing path for a small Steam game from genre selection and trailer-first vertical slice through pricing, early localization, official website, press kit, itch.io or browser playtest, Steam page, demo, telemetry, festivals, creator outreach, launch, and post-launch. Use for whole-project roadmaps, next-action decisions, milestone sequencing, and marketing calendars; use a focused audit skill for a standalone store-page or trailer review.
---

# Plan Indie Game Marketing

Treat marketing as part of product design. Identify the player, genre, visual
promise, and proof required to sell the game before expanding production.

## Default release model

This playbook is for a premium game launched as a substantially finished
product. Do not recommend Early Access or free-to-play as routine ways to get
the game out sooner, build an audience, or compensate for weak positioning.
Both models create different product, operations, retention, monetization, and
community obligations from the premium-release path described here.

If a developer explicitly wants Early Access or free-to-play, treat that as a
change of business model requiring its own evidence and plan; do not quietly
blend it into this workflow. Otherwise, plan for a paid full release.

## Human-authorship invariant

Never draft, rewrite, or "polish" original audience-facing marketing text. This
includes store descriptions, emails, subject lines, press releases, social
posts, captions, trailer title cards, voiceover, calls to action, application
answers, and public biographies.

When outward-facing wording is needed:

1. Ask the user for the exact words in their own voice.
2. Preserve those words verbatim.
3. Flag factual mistakes, unsupported claims, platform violations, ambiguity,
   or likely misunderstandings and ask the user to revise them.
4. Do not silently turn notes into publishable prose.

The agent may organize human-approved text, transcribe human speech, and make
mechanical substitutions in a human-written template, such as a verified
creator name or previously played game. Reusing one good human-written message
is preferable to producing many synthetic personalized messages.

Localization exception: the agent may faithfully translate exact,
human-authored source text into other languages for the game, store page,
website, subtitles, metadata, and assets containing text. It must not introduce
new claims or rewrite the campaign for a locale. Track source revision,
translation provenance, glossary terms, and human-review status internally;
validate variables, layout, fonts, and meaning; and preserve human corrections
when translations are regenerated. Read
[references/early-localization.md](references/early-localization.md) before
planning or auditing language support.

Do not generate capsule art or other key art. Ask the user to create it or
commission a human artist. It is acceptable to inspect, crop, resize, export,
or mechanically compose supplied human-made assets.

Internal plans, audits, questions, tables, and implementation instructions are
not audience-facing and may be written by the agent.

Narrow exception: the agent may draft factual privacy-policy, telemetry, and
consent boilerplate from a verified inventory of implemented collection,
storage, retention, sharing, and deletion behavior. Never invent a practice,
hide a material fact, or use manipulative consent language. Require the
developer to review and approve the text and recommend qualified legal review
when the data or jurisdictions warrant it. This exception does not extend to
marketing copy.

## Start with the decision, not a generic checklist

Determine:

- whether the goal is commercial return, portfolio value, artistic completion,
  community building, or a stated combination;
- the target storefronts and platforms;
- the current stage, budget, team, runway, and intended release window;
- the next irreversible decision or external deadline; and
- what evidence already exists: prototype, gameplay footage, outside play,
  wishlists, coverage, festival results, or sales.

Ask only for missing information that changes the next decision. Do not force a
developer with a nearly finished game back through an imaginary greenlight
exercise, but record the commercial consequences of earlier choices honestly.

## Route by lifecycle stage

- Before production or at concept selection, read
  [references/preproduction.md](references/preproduction.md).
- When choosing a base price, regional prices, launch discount, or discount
  ladder, read [references/pricing.md](references/pricing.md).
- From vertical slice through the coming-soon page, demo, and Next Fest, read
  [references/store-demo-next-fest.md](references/store-demo-next-fest.md).
- When selecting, ordering, or diagnosing Steam tags and their similar-game
  neighborhood, use `optimize-steam-tags`.
- When selecting languages, internationalizing the game, translating public
  pages, or checking Steam language claims, read
  [references/early-localization.md](references/early-localization.md).
- For the official website and downloadable media package, read
  [references/official-site-and-press-kit.md](references/official-site-and-press-kit.md).
- For a browser playtest and opt-in diagnostics, read
  [references/web-playtest-telemetry.md](references/web-playtest-telemetry.md).
- Whenever choosing, combining, or preparing public beats, read
  [references/marketing-beats.md](references/marketing-beats.md).
- For outside testing, festivals, press, or creators, read
  [references/playtesting-festivals-outreach.md](references/playtesting-festivals-outreach.md).
- When choosing or announcing a release date, preparing the launch push, or
  considering a request for Steam featuring, read
  [references/steam-launch-visibility.md](references/steam-launch-visibility.md).
- For release readiness and the period after launch, read
  [references/launch-and-postlaunch.md](references/launch-and-postlaunch.md).
- When the developer asks whether their wishlists, demo engagement, festival
  result, launch conversion, or other marketing performance is good, read
  [references/performance-benchmarks.md](references/performance-benchmarks.md).

Read only the references relevant to the current stage.

## Working method

1. Name the current stage and the concrete outcome for the next milestone.
2. Separate hard platform requirements from recommendations, case studies, and
   experiments.
3. Reserve the project's finite marketing beats, then build backward from dated
   external events with explicit internal buffers.
4. Turn each marketing promise into evidence the build can actually show.
5. Put incomplete prerequisites ahead of promotional activity. In particular,
   do not use Steam Next Fest as a beta test for a substantially unfinished
   game or as pressure to finish the core experience during the event.
6. Give the developer the smallest useful set of next actions, normally one to
   three, with an owner and due date.
7. Update the plan when reality changes; do not preserve a stale launch date or
   obsolete tactic for consistency.

Every calendar item should contain: status, external date and timezone, safe
internal date, prerequisites, required assets/build, source URL, date verified,
and result or follow-up.

## Evidence discipline

For changing rules, deadlines, dimensions, cooldowns, or festival eligibility,
retrieve the current official source. Use secondary sources to discover
opportunities, then verify them with the organizer or platform.

Label recommendations as one of:

- platform requirement;
- measured result or published dataset;
- practitioner recommendation;
- project case study; or
- untested hypothesis.

Do not invent universal wishlist thresholds or imply that completing a
checklist guarantees success.

## Authorization boundary

Research, planning, auditing, file preparation, and private build validation do
not authorize sending emails, submitting forms, publishing pages, releasing a
demo, issuing notifications, distributing keys, or launching a game. Obtain
explicit confirmation immediately before each external action.
