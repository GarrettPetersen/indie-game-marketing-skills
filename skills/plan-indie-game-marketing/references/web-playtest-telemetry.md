# Browser playtest and opt-in telemetry

A browser build lowers friction for early playtesters, festival judges, press,
and selected creators. It can also expose compatibility, performance, and game
logic failures across a much wider device set than the developer owns.

Treat this as product infrastructure, not merely a web export.

## Deployment model

Maintain explicit release channels:

- an internal or disposable development build;
- a current playtest build for invited users; and
- immutable, versioned snapshots for festivals, judging, press, or any link
  that must keep working after development moves on.

A convenient `latest` URL may redirect to a tested playtest version. Do not use
a moving target where a judge or reviewer needs a reproducible build. Display a
build identifier in an unobtrusive diagnostics or credits view and attach it to
every report.

Test first load, cached reload, update behavior, offline or interrupted asset
loads, supported browsers, input methods, viewport changes, audio permission,
save persistence, memory pressure, and slow hardware. Never put secrets or
privileged database credentials in the browser bundle.

The build may live on the game's owned site or on itch.io. Test the exact host,
iframe or fullscreen mode, relative asset paths, storage behavior, input focus,
network requests, and update cache. Keep telemetry ingestion independent from
the hosting vendor where practical, and record the hosting channel with the
build identifier so incidents can be reproduced.

## Consent is a product state

Diagnostic collection must be off until the player explicitly opts in. Supply
a real path to play without optional telemetry. Record the consent-policy
version and allow the player to inspect or change the choice later.

The agent may draft factual privacy, telemetry, and consent boilerplate from a
verified inventory of implemented behavior. It must not invent collection or
sharing practices, omit a material fact, or use manipulative consent language.
The developer must review and approve the text; obtain qualified legal review
when the collected data or jurisdictions warrant it. This is a narrow privacy
exception, not permission to write surrounding marketing copy. Bug-report
prompts and other product voice should still come from the developer.

Manual bug reports are a separate deliberate action. Let the player review
their description and choose whether to attach diagnostics, a screenshot, or a
save. Make contact information optional unless a reply genuinely requires it.

## Collect the minimum useful evidence

Prefer structured, bounded fields:

- random session or installation identifier, not a real-world identity;
- build identifier, release channel, locale, and game mode;
- browser, operating system, renderer, viewport, and coarsened device class;
- incident kind, stable error code, stack, and deterministic fingerprint;
- relevant canonical game-state identifiers and coarse state, not localized
  display text;
- load timings, frame-time summaries, long stalls, memory warnings, asset
  failures, and other threshold-triggered performance incidents; and
- player-supplied report text only after the explicit submit action.

Do not collect keystrokes, clipboard contents, unrelated URLs, filesystem
paths, authentication material, full save data, chat, or continuous screenshots.
Do not attach a save or screenshot without a separate clear choice.

Measure performance in bounded intervals or when a threshold is crossed. Do not
send per-frame telemetry or unbounded event streams.

## Ingestion and database contract

Validate an explicit versioned payload schema at both client and server. The
server should assign receipt time and an incident ID, reject unknown or
oversized fields, rate-limit abuse, authenticate administrative access, encrypt
transport, and enforce retention and deletion policy.

An incident record normally needs:

- incident ID and timestamps;
- schema, consent-policy, and build versions;
- release channel and random session ID;
- incident kind, severity, stable code, and fingerprint;
- validated environment and game context;
- bounded metrics or diagnostic attachment references;
- triage status, linked issue, first/last seen, and occurrence count; and
- resolution build when fixed.

Keep player-written reports and optional contact data in a separately governed
record when practical. Deduplicate automatic incidents by fingerprint plus
build and relevant environment; do not merge distinct regressions merely
because their messages look alike.

## Operational loop

1. Query new, severe, frequent, and newly regressed incidents by build.
2. Reproduce with the recorded environment and canonical game context.
3. Link the incident cluster to one tracked defect.
4. Fix the violated invariant and add a regression test.
5. Deploy a new identified build.
6. Verify the incident stops on that build without confusing old-build reports
   for a continuing regression.
7. Record resolution and retain only the data required by policy.

Alerts should identify actionable regressions, not every individual report.
Keep queues, attachments, retries, and retention bounded.

If an automatic upload fails, use a bounded retry and local diagnostic; it must
not break the game. If a player explicitly submits a bug report, show whether
it was received or failed rather than silently claiming success.

Deploying the build, enabling collection, changing the privacy policy, or
accessing identifiable reports requires the appropriate explicit authorization.

## Sources

- [OWASP Logging Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html)
- [GoogleChrome/web-vitals](https://github.com/GoogleChrome/web-vitals)
- [itch.io: Uploading HTML5 games](https://itch.io/docs/creators/html5)
- [itch.io: Controlling who can access your project](https://itch.io/docs/creators/access-control)
