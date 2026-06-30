# Reality TV: 2004–2024

This is an interactive bubble chart mapping ~70 English-language reality TV shows across two axes: **highbrow vs. lowbrow** and **wholesome vs. depraved**. Dot size is scaled to show viewership data. You can toggle between three different ways of measuring the landscape.


Each dot is a reality TV show. Position reflects editorial judgment. Size reflects data about viewership and longevity.


**Horizontal axis is lowbrow v. highbrow**. Does the show's intent assume a curious, intelligent audience, or is it pure entertainment?

**Vertical axis is wholesome v. depraved** Does the show profit from exploiting or humiliating its participants? Sexual content and manufactured degradation pull toward depraved; exploitation of vulnerable people weighs most heavily.


### Modes

Use the buttons under the chart to toggle between modes. All three use the same scale: **dot area is proportional to the underlying value**, calibrated so the largest show in each mode fills the maximum radius. There is no log compression.

#### Peak viewership
Dot size = peak or typical audience for the show's best period.

- Broadcast figures are live+same-day Nielsen ratings
- Streaming figures are Netflix/platform-reported unique viewers or households (Netflix counts any account that watched 2+ minutes)
- The two scales are not directly comparable

Tooltips note the source.

#### Estimated cumulative viewership
Dot size = average viewers × total episode count. This is a rough proxy for total exposure over the show's life.

This is not a published figure anywhere. It systematically favors long-running broadcast shows (*Survivor*, *American Idol*) over short-run viral streaming hits (*Tiger King*), which is arguably the more truthful picture of total reach. Streaming shows are likely undercounted since their per-episode averages are harder to verify.

#### Number of episodes
Dot size = total episodes through 2024.

This is an verifiable measure of longevity and output, and we can be more confident in this number than we were with viewership estimates. Long-running shows like *Big Brother* (900 episodes), *Survivor* (760 episodes), and *The Challenge* (500 episodes) loom large. Prestige limited (self-contained, limited-run) series like *Making a Murderer* (16 episodes) and *The Last Dance* (10 episodes) shrink to near-minimum.


### Quadrant totals

The small numbers near the axis intersection show the sum of peak viewership / episode count /cumulative viewership) for all shows in that quadrant. The grand total across all 70 shows is displayed below the chart.


### Methodology notes

- Placement is editorial, not empirical. Every show's position on both axes reflects judgment calls, not a scoring rubric. Reasonable people will disagree with individual placements.
- The viewership data is mixed-methodology. Broadcast Nielsen numbers, UK BARB figures, Netflix household counts, and cable ratings are not directly comparable. The chart treats them as best-available proxies. Where a figure is estimated (e.g. Netflix shows pre-2023, when Netflix began releasing data), the tooltip notes this.
- The sqrt scale. The dot radius = k × √(value), where k is set so the maximum value in each mode hits the maximum radius. This means that dot area is directly proportional to the underlying number. A dot that looks twice as large in area represents a show with twice the viewership/episodes.
- Opacity. Opacity is set to 0.72 to keep overlapping circles legible.


### Technical details

This is a single self-contained HTML file.

- **SVG** for the chart itself — dots are rendered as `<circle>` elements by JavaScript on load
- **Vanilla JS** for the toggle interaction and tooltip — the `shows` array holds all three pre-computed radii (`rp`, `re`, `rc`) and switching modes just updates each circle's `r` attribute
- **CSS transitions** on the `r` attribute create the animated size change between modes
- Dark mode is supported via `@media (prefers-color-scheme: dark)`

To use: download `reality_tv_quadrant_final.html` and open it in a browser. No server is required.


### Data sources

Viewership figures were drawn from:

- Nielsen Media Research (broadcast, via published reports and press releases)
- UK BARB ratings (BBC, ITV, Channel 4 shows)
- Netflix self-reported viewership data (post-2023 releases and selected earlier disclosures)
- Third-party Nielsen streaming estimates (Tiger King, Making a Murderer)
- Industry reporting via Deadline, Variety, The Wrap, and TV Series Finale

Episode counts are from Wikipedia and IMDb, verified against network/platform episode guides.

_Made by Shaya Bendix Lyon in 2026, with the help of [Claude.ai](https://claude.ai). Why? I mentioned to my partner in passing that "Million Dollar Nanny" seemed slightly less awful than "MILF Manor"... and the idea was born._
