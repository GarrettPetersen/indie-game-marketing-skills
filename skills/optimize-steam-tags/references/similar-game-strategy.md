# Similar-game tag strategy

The objective is not to collect plausible labels. It is to give Steam a
coherent representation of the game that overlaps with the histories of the
right players. Use the similar-games outputs to test that representation.

## 1. Define anchor, adjacent, and anti-target games

Build three sets:

- **Anchor games:** players repeatedly do substantially similar things and
  would recognize the same core genre promise.
- **Adjacent games:** share an audience-relevant system, structure, or fantasy,
  but differ in a way that must remain visible.
- **Anti-target games:** share superficial art, setting, or broad genre terms
  while promising a materially different experience.

Prefer three to eight strong anchors over a long list of famous names. For each
candidate, record the repeated player activity, run or campaign structure,
perspective, progression, tone, and purchasing expectation that support or
reject the comparison.

The desired neighborhood should contain commercially meaningful games, but
commercial success alone is not evidence of audience fit. A small precise game
can be a better anchor than a blockbuster with one shared feature.

## 2. Build the overlap matrix

Record the current top tags of the game and each anchor. Use current Steam data
and distinguish developer ordering from community-influenced public weights
when possible.

Use a table with these columns:

| Candidate tag | True and prominent? | Anchor overlap | Specificity | Buyer expectation | Proposed rank |
| --- | --- | --- | --- | --- | --- |

`True and prominent?` is a gate, not a score. Reject the tag if the mechanic,
structure, viewpoint, mood, or theme is absent or too incidental to influence a
reasonable purchase decision.

Do not add numerical precision unsupported by Steam. Use the matrix to expose:

- tags shared by several anchors that accurately define the core;
- specific tags that distinguish the right subgenre from a broad parent genre;
- redundant tags that consume high positions without changing the audience;
- tags attracting anti-target games; and
- truthful differentiators that keep the game from looking like a clone.

## 3. Order the profile

Construct one coherent profile rather than optimizing each tag independently.

- **Top five:** communicate the specific genre, repeated play, structure, and
  defining audience identity at capsule-hover depth.
- **Positions 6–15:** reinforce the neighborhood with important mechanics,
  activities, perspective, progression, and meaningful theme or presentation
  signals.
- **Positions 16–20:** add accurate supporting facets and useful browse paths
  that do not displace stronger identity signals.

These are defaults, not fixed category slots. `Pixel Graphics`, `Anime`,
`Relaxing`, or another visual or mood tag can belong in the top five when it is
central to who buys the game. Conversely, a mechanic should rank low or be
omitted when it appears rarely.

Specificity matters only when true. A narrow subgenre or activity tag often
contains more recommendation information than a super-genre used by thousands
of unrelated games. Keep broad tags below the terms that tell Steam which
portion of that broad audience is relevant.

## 4. Use the similar-titles preview as a test

Snapshot the existing ordered tags and Tag Wizard similar-titles preview. Apply
the proposed order in the wizard without publishing, then record the new
preview.

Classify each resulting title:

- desired anchor;
- credible adjacent comparison;
- surprising but explainable;
- misleading; or
- unknown and requiring inspection.

A strong result is not necessarily an exact list of hand-picked anchors. It is
a recognizable audience neighborhood with few misleading games. If the list is
an incoherent mixture of unrelated genres, the profile probably relies on
broad, contradictory, or weakly supported tags.

For every mismatch, identify the tag combination likely responsible. Correct
the profile only when the replacement remains accurate. If an honest game sits
between audiences, preserve that fact and explain the resulting tradeoff
instead of manufacturing certainty.

Valve explicitly warns that the wizard's similar-titles preview is strictly
tag-driven and is not a direct rendering of the live `More Like This`
algorithm. Use it as a controlled diagnostic, then inspect the public section
and traffic reports after publication.

## 5. Measure and maintain

Before an authorized change, record:

- ordered top 20 and visible top five;
- wizard preview and public `More Like This` list;
- relevant tag-page, recommendation, Discovery Queue, and store traffic;
- current positioning, capsule, and trailer; and
- community-added or unwanted tags.

Publish the coherent profile as one intentional change. Record the exact time
and avoid simultaneous positioning changes when the purpose is to learn what
the tag update did. Allow reporting and public surfaces time to update; do not
infer failure from an immediate cached result.

Review the profile:

- before the coming-soon page announcement;
- after a material change in the build or positioning;
- when demo or playtest evidence contradicts the intended audience;
- before an important festival or launch, without adding eligibility bait;
- after enough community tags accumulate to alter weights; and
- when the public similar-game neighborhood becomes misleading.

Do not reorder weekly without a hypothesis. Each revision needs an observed
problem, an accurate proposed correction, and a measurement date.

## Steam facts to preserve

- Steam requires at least five tags and recommends adding up to 20.
- Only the top 20 are visible and used to influence store visibility.
- The top five receive the most descriptive weight; some filters prioritize the
  first 15.
- Multiple overlapping top-20 tags strengthen tag-based similarity; order is
  less important for this overlap than it is for the top-five description and
  first-15 filters.
- Less-common relevant tags may carry more recommendation information than
  broad common tags.
- Community tagging can alter weights, and developers can remove inaccurate
  tags.
- A demo inherits the base game's tags.
- Steam localizes tag names automatically while preserving their order.

Recheck [Steam's current tag documentation](https://partner.steamgames.com/doc/store/tags)
before relying on these mechanics.
