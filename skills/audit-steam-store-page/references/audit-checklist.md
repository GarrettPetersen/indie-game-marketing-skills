# Steam store-page audit checklist

## Positioning

- Can a genre fan recognize the primary genre and subgenre without reading the
  long description?
- Do the top tags describe gameplay and audience rather than generic qualities?
- Do comparable games and their audiences support the chosen positioning?
- Are every feature, mode, platform, language, date, and content claim true in
  the current intended release build?

## Capsules and library art

- Use current Steam templates; never rely on remembered dimensions.
- Preserve authored aspect ratios and inspect the actual upload, not only the
  source artwork.
- Confirm the title remains readable at the smallest real display size.
- Confirm art communicates genre, mood, subject, and visual quality without
  miscellaneous marketing text prohibited by Steam.
- Confirm the main capsule is not accidentally a logo-only or other incorrectly
  assigned asset.
- Confirm library hero art is artwork-only and the transparent library logo is
  separate where current Steam rules require that.
- Use only human-made or human-commissioned art. Do not recommend generative
  imagery as a cheaper substitute.

## Trailer

- The first trailer is current, representative, and gameplay-first.
- The opening seconds show a legible core action or fantasy.
- The trailer shows progression, variety, stakes, and payoff without promising
  absent features.
- The first visible trailer is deliberately ordered because Steam derives the
  store's six-second microtrailer from it.
- The actual Steam-generated microtrailer has been inspected muted, looping,
  and at hover-preview size after the latest trailer upload or reorder. It has
  no sampled black frames, logos, loading screens, unreadable text or modals,
  obsolete UI, incoherent fragments, or incompetent play.
- See `review-game-trailer` for a shot-level audit.

## Screenshots

- Lead with strong gameplay, not logos, title cards, settings, or passive text.
- Use the current build and normal player-facing interface.
- Show distinct environments, situations, systems, scales, and progression.
- Avoid near-duplicates, obsolete UI, debug state, incompetent play, unreadable
  modal flashes, misleading staging, and stretched aspect ratios.
- Meet current Steam resolution and aspect requirements.

## Human-authored descriptions

- The short description names the recognizable genre and concrete player
  activity in the developer's own words.
- The opening of the long description explains actual play before lore.
- Claims correspond to screenshots or trailer evidence.
- Headings help scanning without turning every sentence into promotional copy.
- The agent identifies missing facts but never supplies replacement prose.

## Tags and discoverability

- Treat the Tag Wizard similar-titles list as a central audience diagnostic,
  not a decorative checklist result.
- Identify the players of the intended anchor games and verify that the actual
  core loop, structure, and expectations make them plausible customers.
- Put accurate subgenre, core mechanic, structure, and theme tags first.
- Make the top five a coherent description and order all of the first 15
  deliberately; use up to 20 accurate tags for similarity and browse surfaces.
- Inspect the resulting "More Like This" neighborhood.
- Avoid elevating broad tags such as `Indie` above useful gameplay identity.
- Do not hide an accurate polarizing genre tag merely to broaden appeal.
- Do not add inaccurate tags to qualify for a festival.
- Use `optimize-steam-tags` for the full comparison and ordering workflow.

## Languages, accessibility, and platforms

- The page launched with priority-language versions rather than saving all
  localization for a later beat; Japanese is present unless deliberately
  excluded for a documented project reason.
- Store-page and in-game localization are audited separately. A translated
  store page does not justify checking in-game `Interface`, `Subtitles`, or
  `Full Audio` support.
- Every checked in-game language exists in the intended release build and has
  working fonts, layout, input where needed, fallback behavior, and string
  coverage.
- Machine-localized text is a faithful translation of approved human-authored
  source copy, not newly generated marketing copy. Translation provenance,
  source revision, glossary, and human-review status are recorded internally.
- Critical Japanese text, names, mechanics, calls to action, variables,
  line-breaks, image text, and search-facing title are spot-checked before the
  page goes live; professional editing can continue afterward.
- System requirements and controller/platform claims have been tested.
- Accessibility statements describe implemented behavior, not intentions.

## Demo

- The demo is associated with the correct base game.
- Any separate demo page describes only what the demo actually contains.
- Demo screenshots and trailer are representative of demo-accessible content.
- The base-game wishlist path and logged-out install flow work.
- The one-time notification is scheduled deliberately within Steam's current
  allowed window.

## Current authoritative sources

- [Steamworks graphical assets](https://partner.steamgames.com/doc/store/assets)
- [Steamworks graphical asset rules](https://partner.steamgames.com/doc/store/assets/rules)
- [Steamworks trailers and microtrailers](https://partner.steamgames.com/doc/store/trailer)
- [Steamworks demos](https://partner.steamgames.com/doc/store/application/demos)
- [Steamworks wishlists](https://partner.steamgames.com/doc/marketing/wishlist)
- [Steamworks localization and languages](https://partner.steamgames.com/doc/store/localization)
- [Steamworks tags](https://partner.steamgames.com/doc/store/tags)
- [BiteMe Games Steam-page guide](https://www.youtube.com/watch?v=cYvV_RLwKJ8)
- [How To Market A Game Steam-page checklist](https://howtomarketagame.com/wp-content/uploads/2020/03/SteamPageChecklistv1.pdf)
