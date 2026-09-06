# Early localization

Treat localization as launch infrastructure, not post-launch polish. A game can
only collect early regional wishlists, platform discovery, social attention,
and press interest in languages it supports while those marketing beats are
still fresh.

## Operating rule

For a commercial Steam game, localize both the game and its coming-soon page
into the priority languages before the store-page announcement. Include
Japanese by default unless the developer has a concrete market, content,
technical, or support reason not to serve Japanese players.

An AI-assisted first pass is acceptable and preferable to missing the page
launch entirely. Budgeted localization services or native community reviewers
can edit it later. Prioritize their review of the game name, short description,
opening long-description text, calls to action, tutorial, controls, store art
containing text, and other high-traffic or high-consequence strings.

This is a practitioner operating strategy, not a Steam requirement or a promise
of coverage. In the Marque & Reprisal case, having Japanese support at the
coming-soon launch made the game legible to Japanese players and preceded
coverage from the large Japanese indie-games account Indie Freaks. Preserve the
lesson without claiming that Japanese localization guarantees the same result.

## Preserve human authorship through translation

The source marketing text must be written by the developer. AI may translate
that exact approved text, but may not add a new hook, quotation, feature,
superlative, call to action, or locale-specific pitch. When the source is
ambiguous, ask the developer what it means instead of guessing creatively.

Maintain:

- stable string keys independent of the displayed text;
- one authoritative source-language string for each key;
- a glossary for names, mechanics, genre terms, factions, places, pronouns, and
  words that must remain untranslated;
- placeholders and markup as typed tokens that translation cannot alter;
- per-language source revision, translation method and date, reviewer, review
  status, and manual override; and
- a missing, stale, and unreviewed-string report that fails loudly in release
  validation rather than silently falling back throughout the interface.

Regenerating machine translations must not overwrite a native speaker's manual
correction. Route changed source strings back through translation and review
instead of leaving old translations attached to new meanings.

## Build for localization before content scales

Externalize player-facing text early. Test variable expansion, plurals,
gendered language where relevant, line wrapping, text expansion, font fallback,
controller glyphs, keyboard input, search, sorting, and save compatibility.
Include the required CJK glyphs without bundling an unbounded font accidentally.

Exercise every localized screen at representative window sizes. Automated
checks should find missing keys, extra or altered placeholders, invalid markup,
untranslated source fragments, duplicate IDs, overflow, clipped buttons, and
unsupported glyphs. A successful file import is not localization QA.

For Japanese, spot-check at minimum:

- whether the game title should remain in Latin characters or use an approved
  localized name;
- consistent treatment of names, ranks, places, historical terms, and player
  gender;
- natural menu labels and control instructions;
- line breaking, punctuation, numerals, and font readability at gameplay size;
- the short description and first store-page screenful; and
- text baked into screenshots, animated headings, trailers, and capsule-adjacent
  promotional assets.

## Distinguish Steam's two language systems

Steam supports store-page localization and in-game localization independently.
Translate the page's descriptions, images, trailers, and localized application
name for the languages used in the campaign. Separately configure the in-game
support table for `Interface`, `Subtitles`, and `Full Audio`.

Only check an in-game support box when the corresponding support is present in
the intended release build and will be maintained. A Japanese store description
alone does not make the game Japanese-supported. Conversely, do not ship a
Japanese game build behind an English-only store page that prevents Japanese
shoppers or media from understanding it.

Valve says language-based visibility uses in-game language settings rather than
store-page localization, while also recommending that localized products
localize their pages. Valve also suggests translating candidate store pages
early to observe regional wishlists and decide where deeper investment is
warranted. Record regional visits and wishlists from the first day instead of
using English-only launch data to conclude that no foreign-language demand
exists.

## Page-launch gate

Before publishing the coming-soon page:

- priority languages and their `Interface`, `Subtitles`, and `Full Audio`
  claims are explicitly listed;
- the localized game build or representative vertical slice is runnable;
- store description, title choice, images containing text, trailer text, and
  metadata exist in each priority language;
- machine translations have passed terminology, placeholder, markup, glyph,
  overflow, and basic meaning checks;
- a native-review order and budget are recorded, even when review happens after
  page launch;
- support channels can accept language-specific reports; and
- regional Steam traffic and wishlist measurements have an owner and baseline.

Do not publish language claims, page changes, or builds without explicit
authorization immediately before the external action.

## Sources

- [Steamworks: Localization and Languages](https://partner.steamgames.com/doc/store/localization)
- [Steamworks: Languages Supported on Steam](https://partner.steamgames.com/doc/store/localization/languages)
- [Indie Freaks coverage of Marque & Reprisal](https://x.com/i/status/2082949368362238267)
