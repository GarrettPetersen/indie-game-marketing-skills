---
name: audit-steam-store-page
description: Audit an upcoming or live Steam store page for positioning, capsule art, trailer and screenshots, human-authored descriptions, tags, localization, platform claims, demo presentation, and current Steam compliance. Use when reviewing page readiness or diagnosing weak presentation; do not use to write the developer's store copy or generate capsule art.
---

# Audit Steam Store Page

Judge whether the page lets the right Steam shopper recognize the genre,
understand the play, trust the production, and choose to wishlist or buy.

## Human-authorship invariant

Never draft, rewrite, or polish original public store text. Ask the developer
for the exact source-language short description, long description, headings,
image alt text, captions, announcements, and calls to action. Preserve it
verbatim. If wording is inaccurate, unsupported, confusing, prohibited, or
grammatically broken, explain the issue and ask the developer to revise it; do
not replace it with agent-written marketing prose.

The agent may faithfully machine-translate approved source text for early
localization. It must preserve the claims and voice, introduce no new marketing
idea, validate meaning and formatting, record that the translation still needs
human review, and retain later native-speaker corrections. Machine translation
is an exception for localization, not permission to originate copy.

Never generate capsule art or key art. Require human-made or human-commissioned
art. The agent may audit, crop, resize, export, or mechanically assemble
supplied human-made assets without changing their aspect ratio.

Internal audit findings, questions, severity labels, and art briefs are not
public marketing copy and may be written by the agent.

The lifecycle skill's narrow exception for factual privacy, consent, and
telemetry boilerplate does not permit agent-written store-page marketing copy.

## Audit procedure

1. Retrieve the current public page when available and inspect supplied source
   assets at their original dimensions.
2. Retrieve current Steamworks rules before asserting asset dimensions,
   permitted capsule text, demo behavior, language requirements, or other
   changeable platform facts.
3. Identify the intended player and primary genre from evidence supplied by the
   developer. Do not invent positioning from the page's existing copy.
4. Audit in shopper order: capsule, first seconds of the first trailer, first
   screenshots, short description, tags, then the detailed page.
5. Read [references/audit-checklist.md](references/audit-checklist.md) for the
   full checklist.
6. Use `optimize-steam-tags` when the task requires an ordered tag proposal,
   comparable-game matrix, or diagnosis of the similar-games neighborhood.
7. Report findings as `blocker`, `high impact`, `improvement`, or `verified`.
   Give evidence and the desired outcome, but do not supply replacement copy or
   generated art.

## Missing text protocol

Ask focused questions that elicit the developer's own words, such as what the
player repeatedly does, what ends a run, what fantasy the game fulfills, or why
a feature matters. Quote the answer back for confirmation. Do not convert rough
answers into a polished paragraph. The developer may deliberately choose the
rougher wording because it sounds human.

Do not block a coming-soon page on complete professional localization. An
AI-assisted first pass of exact human-authored copy may launch in priority
languages, especially Japanese, then be edited by a native localization service
later. The audit must still flag mistranslation, terminology, layout, font, and
unreviewed high-visibility text as risks rather than pretending machine output
has been professionally localized.

## Output

Return:

- a one-paragraph diagnosis of the page's current conversion path;
- findings ordered by likely impact;
- exact assets or human answers still required;
- current platform-rule links and date checked; and
- a publish/no-publish recommendation with unresolved blockers.

Do not publish, submit for review, change a live page, or issue a demo
notification without explicit confirmation immediately before that action.
