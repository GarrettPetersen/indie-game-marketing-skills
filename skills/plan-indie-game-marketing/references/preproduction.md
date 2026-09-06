# Preproduction: choose the market and design the proof

Use this reference before substantial production or when a project needs a
commercial reset.

## 1. Define success and constraints

Record why this game exists, what outcome would justify making it, available
time and cash, team strengths, target platform, plausible price range, and the
maximum tolerable scope. A hobby or art project may knowingly ignore market
demand; do not disguise that choice as a commercial forecast.

Choose the page-launch language set while architecture is still cheap to
change. Include Japanese by default for a commercial Steam project unless there
is a concrete reason not to support it, and read
[early-localization.md](early-localization.md) before content volume makes
externalizing strings, font coverage, and layout expensive.

Record an initial price hypothesis for scope and revenue planning, then revisit
it after representative players have used the vertical slice. Read
[pricing.md](pricing.md) before recommending a price.

## 2. Choose the genre before production

Research the current market rather than relying on the genres the developer
personally notices. For a commercial Steam project, prefer genres with evidence
of durable player demand, content depth, replayability, and production leverage.
Crafty-buildy, strategy, simulation, management, sandbox, and related genres
often have these properties, while puzzle platformers usually face weaker Steam
demand and require expensive hand-authored content. Treat this as a market
prior, not a guarantee or a command to abandon the developer's goals.

Identify:

- the primary genre and subgenre a Steam shopper would use;
- several commercially relevant comparable games;
- genre conventions players expect;
- review complaints and unmet wants in those games;
- recent release count, rough performance distribution, and production risk;
- how much playtime and variety each unit of authored content can support;
- whether the team's skills and budget can deliver the expected depth, feel,
  content, interface, and presentation; and
- one legible differentiator that does not destroy the genre promise.

Play representative games. Do not infer a genre from tags alone. Avoid combining
several weakly understood genres in the hope that their audiences will add
together.

### Look for demand paired with dissatisfaction

A comparable game with a large review count and a Mixed rating can expose a
valuable gap: many players cared enough to acquire and play this kind of game,
but many felt that the existing product failed them. Use the Steam review API
or current store data to inspect both volume and sentiment, then read a useful
sample of positive and negative reviews.

Cluster complaints by cause. A promising opportunity has repeated complaints
about a genre need the proposed game can credibly satisfy while preserving what
positive reviewers value. It is weaker evidence when dissatisfaction comes
from an off-topic review campaign, price or monetization policy, abandoned
service, broken launch, unsupported hardware, localization, or a production
problem the team cannot afford to solve.

Review count is a proxy for audience activity, not an exact sales number. Steam
reviews can come from purchases, keys, free access, or other license sources,
and only some contribute to the displayed score. Confirm the pattern across
several comparable games and recent releases rather than building a concept
around one anomalous title.

### Check optional promotional accelerants

Streamability is helpful but not required. Assess whether a viewer can quickly
understand the situation, anticipate an outcome, enjoy surprising stories or
strong reactions, and see meaningful differences between sessions. Rage games
and social multiplayer games sometimes called "friendslop" can benefit from
these properties, but do not add frustration, multiplayer, or streamer-facing
gimmicks to a game whose core loop does not need them.

A concise social-media hook is also helpful but not required. Ask whether the
developer can truthfully describe the game in their own words as an immediately
interesting activity. One test is to ask the developer to complete, in their
own words, `This indie developer is making a game where you {activity}.` Then
ask whether authentic gameplay supplies a surprising or recognizable visual
within the first seconds. Look for repeatable, shareable outcomes rather than a
premise that sounds clever but produces monotonous footage. Do not substitute
virality speculation for evidence of a paying audience.

### Make a comparative recommendation

When choosing between concepts, compare them on:

- audience demand relative to competing supply;
- evidence of underserved demand in reviews;
- production scope and content leverage;
- expected session depth and replayability;
- trailer, capsule, and screenshot legibility;
- team fit and ability to satisfy genre expectations;
- optional streamability; and
- optional social-media hook.

Weight the commercial foundation above the optional promotional accelerants.
Avoid false-precision scoring: record the evidence, confidence, and decisive
tradeoffs. If one concept has a material commercial advantage, recommend it
plainly. If the evidence is genuinely inconclusive, state what prototype or
market test would resolve the decision.

The output is a genre decision record, not public copy. Include the recommended
concept, evidence, uncertainties, rejected alternative, and a stop/reconsider
condition.

## 3. Develop trailer-first

Before building the full game, create a visual-only trailer beat sheet. Do not
write audience-facing narration or title cards. Each beat should answer:

- What player fantasy is being sold?
- What action proves the core loop?
- What visually changes as the player progresses?
- What creates danger, surprise, mastery, or payoff?
- What environmental or systemic variety proves this is a complete game rather
  than a single-room prototype?
- What final image leaves the viewer wanting to play?

Map every beat to runnable gameplay required in the vertical slice. A promised
feature that cannot be shown clearly is not trailer-ready. A feature that is
neither core nor useful evidence is a candidate for deferral.

Trailer-first development does not mean fabricating a concept trailer. The
vertical slice must produce authentic gameplay footage with representative
controls, interface, art direction, effects, and performance.

## 4. Greenlight the vertical slice

Proceed when the slice can demonstrate:

- the core loop and its immediate appeal;
- the primary genre without explanation;
- the chosen visual identity;
- a beginning, escalation, and payoff;
- enough visual or systemic variety for distinct screenshots and trailer beats;
- a runnable machine-localized build in the priority page-launch languages,
  with representative CJK layout and fonts when Japanese is included;
- a credible production path within the budget; and
- interest from outside players who were not coached through the experience.

If the game is unclear, visually monotonous, unpleasant to control, or far too
expensive to finish, change the design or stop before scaling production.

## Sources

- [How To Market Your Indie Game: A 10 Step Plan](https://howtomarketagame.com/2021/07/12/how-to-market-your-indie-game-a-10-step-plan/)
- [What genres are popular on Steam](https://howtomarketagame.com/2022/04/18/what-genres-are-popular-on-steam-in-2022/)
- [HTMAG: More evidence of which genres Steam shoppers play](https://howtomarketagame.com/2022/05/30/more-evidence-of-which-genres-steam-shoppers-love-to-play/)
- [HTMAG: Crafty Buildy Strategy Simulation Buyers Guide](https://howtomarketagame.com/2025/07/02/crafty-buildy-strategy-simulation-buyers-guide/)
- [HTMAG: Respect players' time by making longer games](https://howtomarketagame.com/2023/05/30/respect-players-time-by-making-longer-games/)
- [When should I post my Steam coming-soon page?](https://howtomarketagame.com/2025/03/10/when-should-i-post-my-steam-coming-soon-page/)
- [BiteMe Games: Ultimate Indie Gamedev Genre Tierlist](https://www.youtube.com/watch?v=Yg8wig1LTtE)
- [BiteMe Games: Small games win big](https://www.youtube.com/watch?v=8Kr5TruT-YU)
- [Steamworks: User Reviews](https://partner.steamgames.com/doc/store/reviews)
- [Steamworks: Get user reviews](https://partner.steamgames.com/doc/store/getreviews)
