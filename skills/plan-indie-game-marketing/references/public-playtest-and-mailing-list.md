# Early public playtest and opt-in mailing list

Run an explicitly labelled public playtest well before the polished demo
launch. Leave weeks or months for onboarding changes, bug fixes, and fresh
player retests. Its marketing job is to turn interested people into an engaged
community: let them play, share genuine experiences, see their feedback acted
on, wishlist, and optionally subscribe. Hype is earned by the experience, not
by collecting addresses or making access artificially scarce.

Keep the initial game announcement separate. Do not claim a later demo is the
first public playable build when an earlier public playtest existed. A public
playtest can be its own honest beat without spending the Steam demo's first
release or notification. For the subsequent sequence, read
[store-demo-next-fest.md](store-demo-next-fest.md).

## Choose the access route before building a distributor

**Platform behavior, checked 2026-11-04:** Steam Playtest uses a separate child
App ID, not a full-game review-key package. Its store-page Request Access flow
can admit applicants in limited batches or automatically with open signup.
Steam selects limited-batch applicants randomly and emails admitted players.
This route does not require individually distributing keys. Do not assume
Steam signup supplies an exportable email-marketing list.

For an owned-site signup and delivery flow, request keys for the **Playtest
App ID**. Valve supports Standard Release keys for this app, not Release State
Override keys; the Playtest must be Playable for redeemed access to work.
Requests still need Valve approval: request and verify inventory ahead of the
announced wave. Do not use base-game review keys as disposable public-test
keys, sell Playtest access, or promise that a test key includes the full game.

Use the simplest route that serves the campaign:

- Steam Request Access plus an optional newsletter link is lowest-friction.
- A website that emails Playtest keys is useful when owned audience-building,
  controlled waves, or off-Steam recruitment justify the extra operations.
- A browser/itch.io playtest may need no Steam keys at all. Add an optional
  signup without blocking play, and use
  [web-playtest-telemetry.md](web-playtest-telemetry.md) for diagnostics.

Explain access dates, test scope, whether sharing/streaming is encouraged, and
whether progress will survive. Public Steam Playtests are not confidential by
default. Hide signups before ending access with Not Playable, and communicate
the end in advance. Do not reset the playtest merely to pause it: Steam's reset
is destructive and disables its keys, including unused ones.

## Minimal owned-site key system

If the campaign chooses email-delivered keys, build and test this small flow
before promoting signup. Use an existing mailing-list provider for consent,
unsubscribe and campaign delivery rather than inventing an email platform.

1. Import the approved Playtest key batch into private server-side storage;
   validate app/package, batch identity, duplicate keys, and available count.
   No raw keys, email addresses, or consent records belong in public Git,
   client bundles, analytics events, or ordinary logs.
2. Collect the delivery address and show a separate, optional, unchecked
   marketing opt-in. Deliver access even if marketing is declined. Verify the
   address before allocation; double opt-in is a sensible list-quality choice,
   not a universal legal requirement.
3. Assign a stable signup ID and atomically reserve one unique key. Repeated
   requests and delivery retries reuse that assignment, never consume a new
   key. Use bounded abuse controls and a visible waitlist when inventory runs
   out; do not claim access was sent when it was not.
4. Send the requested access message through a transactional delivery path.
   Keep it separate from promotional campaigns and use exact human-approved
   wording. Track delivery acceptance, failure, and bounces without treating
   provider acceptance as proof it reached the inbox.
5. Keep a private ledger of signup ID, delivery address, key reference, batch,
   assigned/delivered timestamps and delivery state. Keep the raw key protected
   separately. Record redemption as unknown unless independently verified;
   email opens and link clicks do not prove key redemption or playtime.
6. Store marketing permission separately: subscriber ID, consent timestamp,
   source, exact consent-text version/scope, confirmation and unsubscribe state.
   A launch-only opt-in does not cover future games. Ask explicitly for the
   studio's future-game news if that is the intended list.

Verify that two simultaneous requests cannot obtain the same key, a retry does
not allocate another, declining marketing still delivers access, exhausting
inventory does not send an empty key, and unsubscribed/bounced addresses cannot
enter a campaign. Test the real email and redemption path with a reserved test
key before opening signup. Keep telemetry consent independent as well.

## Use the list deliberately

Key delivery is not newsletter consent. Keep proof of permission, sender
identity, an easy unsubscribe, a suppression list, and a retention/deletion
policy. Recheck applicable email/privacy rules for sender and audience; for
Canadian senders, CRTC guidance requires consent, identification, and an
unsubscribe mechanism, and rejects pre-checked express-consent boxes. Obtain
qualified advice where needed; this is an operational checklist, not legal
clearance.

Prepare human-authored messages for the demo/Next Fest opening, game launch,
and future games only within the recorded consent scope. Segment and dedupe
recipients, respect suppression across imports, and use a properly configured
mailing service rather than a large personal-Gmail BCC blast. Sending still
requires explicit authorization immediately before the campaign.

Measure playtest participation, useful feedback, repeat play, wishlists,
confirmed subscribers, and attributable launch results separately. A large
signup count is neither a tested build nor a sales forecast.

## Sources

- [Steamworks: Steam Playtest](https://partner.steamgames.com/doc/features/playtest)
- [Steamworks: Demos and notifications](https://partner.steamgames.com/doc/store/application/demos)
- [CRTC: Canada's anti-spam legislation FAQ](https://crtc.gc.ca/eng/com500/faq500.htm)
