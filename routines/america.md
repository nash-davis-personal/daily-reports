# Scout routine — America (a-political)

Daily job for the scout agent. Self-contained: assume no memory of previous runs.
Working directory is the root of the `daily-reports` repo.

## Goal
File one neutral, **a-political** briefing on the biggest things happening in the United
States since the last edition.

## Source
- **Not a single feed** — search broadly with WebSearch/WebFetch across: the economy
  (markets, jobs, inflation, the Fed, rates, major corporate news, big M&A), policy &
  legislation with a concrete effect on small business, major national events, weather &
  natural disasters, public-safety incidents, science & space, and infrastructure/energy.
- A **personal-investor lens** on markets is welcome (what a move means for someone managing
  their own money), as are **Charlotte / North Carolina** items of real significance.
- **Slug:** `america` · **Label:** `America` · **Color:** `#f59e0b`

## Hard exclusions — NEVER include (even if it's the day's biggest story)
- **Sports** — scores, leagues, championships, athletes, drafts, trades. Never.
- **Entertainment** — movies, TV/streaming, box office, celebrity/influencer gossip.
- **Partisan political horse-race** — election handicapping, polls, left-vs-right fights.
  (Substantive policy is allowed only as neutral facts + concrete effect — see THE RULE.)

## THE RULE — keep it a-political and neutral
- Report big factual happenings **without partisan framing and without taking sides.**
- **Avoid** hot-button partisan fights, culture-war commentary, election horse-race, and
  any story whose substance is really a left-vs-right argument. When in doubt, prefer
  non-political national news.
- If a government/policy event is unavoidably major national news, report **only** the
  neutral facts — what happened, who, when, and the concrete real-world effect — with zero
  editorializing or spin. If a story has a politically charged *cause*, report the domestic
  effect neutrally and attribute the cause in a single neutral clause.

## Macro context — the Macroscope board feed
- Read `/Users/nashdavis/Documents/macro-brain/digests/board-feed.json` (small JSON; written at
  each Macroscope synthesis publish, so by this run it carries the previous evening's board —
  its `board_date` says which). It holds the regime read, themes and signals with
  direction/conviction, the nearest tripwires, divergences, and dated catalysts.
- Use it two ways:
  1. **Sanity-check** your economy items against the board's directions so the briefing and the
     board never silently contradict each other. A real disagreement is worth reporting as a
     disagreement, with both sources shown.
  2. **Close the economy block** with a one-line callout labeled **"The macro backdrop:"** —
     the regime label + direction, the nearest alert-grade wire in plain words, and the next
     dated catalyst. Cite it as `TSD Macroscope board (as of <board_date>)`.
- The feed is a neutral terrain map: direction + conviction only. Never turn it into advice or
  a prediction, and never present a board read as a reported news fact — it is TSD's internal
  read, and the callout should look like context rather than reporting.

## Steps
1. `git pull`, then read `profile.local.md` (gitignored, local) for Nash's interest
   weighting and the hard exclusions above.
2. Find the newest existing file in `reports/america/` (YYYY-MM-DD). Cover what's new since
   that date.
3. Run several distinct searches across the focus areas. Verify each item with a real,
   datable source URL. Never include something you can't source. Then read the Macroscope
   board feed (section above) for the macro backdrop and the contradiction check.
4. Pick the **4–6 most nationally significant items**. Demote the rest to quick-hits.
5. Copy `templates/report-template.html` → `reports/america/<date>.html`. Fill every
   `{{TOKEN}}` and all `<meta name="report:*">` tags (source=america, label=America,
   color=#f59e0b). For this section, use the `.so-what` callout with the label
   **"Why it matters:"** (neutral) instead of "So what for TSD".
6. Voice: blunt and factual, lead with what happened. No "X, not Y" construction. No spin,
   no opinion, no fabrication.
7. `node scripts/build-manifest.mjs`, then `git add -A && git commit -m "report(america): briefing for <date>" && git push origin main`.

## Quiet day
File the 2–4 biggest neutral national items. Never reach for partisan controversy to fill space.
