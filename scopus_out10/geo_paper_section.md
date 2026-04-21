# [Paper section draft] Geographic landscape of AI-for-Chips research

*Ready-to-paste paper section. The table in "A phase shift at 2020" is the main quantitative anchor; figure references `(Figure X/Y/Z)` are placeholders — see "Suggested figures" at the bottom for the corresponding files in `scopus_out10/figures/`.*

---

## Geographic landscape of AI-for-Chips research

The AI-for-Chips literature is geographically concentrated in a pattern that has shifted substantially across the 2015–2025 decade. We analysed the 320 high-confidence AI-for-Chips papers in our corpus that carry resolvable author affiliations, assigning each paper to every unique country in its affiliation list — the *any-affiliation* rule that is standard for bibliometric leadership analysis. To test whether European participation should be read as national or supranational, we additionally computed an aggregate "Europe" bloc covering all EU-27 member states plus the United Kingdom, Switzerland, and Norway, matching the framing used by the EU Chips Act.

Across the full 2015–2025 fit window, the contribution distribution is headed by **China (105 papers, 29.0% average share of annual output)**, **the United States (68 papers, 27.6%)**, and — when treated as a bloc — **Europe (31 papers, 12.1%)**. A meaningful second tier follows at 4–6% share each: South Korea, Hong Kong (which Scopus resolves as an affiliation country distinct from mainland China), and India. Canada and a long tail of emerging contributors (Iran, Turkey, Brazil, the United Arab Emirates, Saudi Arabia, Algeria) each account for one to three papers across the decade. **Figure X** shows the full distribution.

### A phase shift at 2020

Splitting the decade into two non-overlapping halves — **P1 (2015–2020, six years)** and **P2 (2021–2025, five years)** — makes the underlying dynamics considerably clearer than any single-series growth statistic. The field as a whole quadrupled its annual publication rate across the split, from 10.8 papers per year in P1 to 43.8 papers per year in P2, a ratio of ×4.0. Whether each contributor beat this baseline determines whether their *relative weight* in the field grew or compressed.

| Contributor | P1 rate (/yr) | P2 rate (/yr) | P2 / P1 | P1 share | P2 share | Share Δ |
|---|---|---|---|---|---|---|
| China | 2.5 | 18.0 | **×7.2** | 23% | **41%** | **+18 pp** |
| United States | 3.2 | 9.8 | ×3.1 | 29% | 22% | −7 pp |
| Europe (bloc) | 1.7 | 4.2 | ×2.5 | 15% | 10% | −6 pp |
| South Korea | 0.7 | 2.8 | ×4.2 | 6% | 6% | +0 pp |
| Hong Kong | 0.5 | 2.6 | ×5.2 | 5% | 6% | +1 pp |
| India | 0.2 | 2.4 | **×14.4** | 2% | 6% | +4 pp |
| *Field (all AI-for-Chips)* | *10.8* | *43.8* | *×4.0* | 100% | 100% | — |

*Table X. Contribution rates and shares before and after 2020. Share Δ is the change in each contributor's share of annual AI-for-Chips output between the two periods.*

Three readings fall out of these numbers. First, **only China and India grew their annual publication rate faster than the field average** (×7.2 and ×14.4 respectively; India's ratio is dramatic but starts from a single paper across the entire first period). Both are the year-over-year gainers in relative weight, with China's share rising +18 percentage points and India's +4. Second, **the United States and Europe both grew absolutely and shrank relatively**: U.S. output tripled between P1 and P2, and Europe's 2.5×'d, but both accelerations fell below the field's ×4.0 baseline, so their shares compressed (U.S. −7 pp, Europe −6 pp). Third, and worth underlining because it cuts against the casual "China has always led this" reading, **the United States led AI-for-Chips in P1**: China was the #2 contributor in 2015–2020 at 23% share, below the U.S.'s 29%. The leadership crossover happened during the P1 → P2 transition, with China's output flat at four to five papers per year through 2021 and then ramping sharply from 2022 onward (11, 18, 18, 39 papers per year from 2022 to 2025). China's 2025 output alone (39 papers) exceeds the U.S.'s total output across the entire 2015–2020 period (19 papers).

The inflection aligns with — and is probably not independent from — the LLM-for-EDA wave (VeriGen, ChatEDA, LayoutCopilot, Atelier), the GNN-based work in placement and hardware-trojan detection, and the broader post-2022 surge in machine-learning research worldwide. These methodological waves crest during the same window, and papers with Chinese affiliations are disproportionately represented in all three. The geographic and methodological accelerations are two views of the same phenomenon. **Figure Y** plots the year-by-year trajectories; **Figure Z** presents the P1-vs-P2 shares in grouped-bar form; and **Figure W** visualizes the share *delta* directly as a diverging bar chart, making the China-gains / U.S.-and-Europe-loses contrast visible at a glance.

### Country-level readings

**China** is the clear accelerator. Its output was essentially flat at 1–5 papers per year through 2019 and then entered a sustained climb, peaking at 39 papers in 2025. The driver mix visible across our curated shortlist is heavy on analog-circuit sizing (Li 2020, Zhang 2022, Budak 2022, AnaCraft 2026), LLM-based EDA tooling (LayoutCopilot 2025, Atelier 2026, ChatEDA 2024), and GNN-based hardware-trojan detection (Yasaei 2022 and 2025, Chen 2025).

**The United States** occupies a "growing but losing share" posture. Absolute output peaked at 17 papers in 2023 and has since settled into the 8–11 paper/year range. The U.S. remains a dominant source of canonical methodology — VeriGen and DREAMPlace both originated at U.S. groups, and the RL-for-analog line (Settaluri 2022) has been driven from Berkeley. The CHIPS and Science Act (2022) post-dates most of our fit window, so any lift from that investment would not yet be visible in 2024–2026 data. The most honest reading is that the U.S. continues to grow in absolute terms while China grows much faster, eroding the U.S.'s share of the conversation.

**Europe as a bloc** holds a remarkably stable ~12% share across the decade. The bloc's absolute output rises (P1 rate 1.7/yr → P2 rate 4.2/yr, ×2.5), but its share trend line is statistically flat (slope +0.08 percentage points per year, R² = 0.0), meaning Europe is running to stand still. Internally the bloc is heavily concentrated: **Germany contributes 12 of the 37 European papers (32%)**, reflecting Fraunhofer institutes and university groups at TU Dresden, RWTH Aachen, and Munich; **Belgium's 5 papers trace almost entirely to imec and its university partners** (KU Leuven, Ghent). Italy, France, the United Kingdom, and Greece contribute 3 papers each, and the Netherlands, Switzerland, Austria, Portugal, and Denmark round out participation at 1–2 papers each. No single European country reaches top-5 status individually; it is only the bloc framing that places Europe in third position. The EU Chips Act's 2023 target of doubling Europe's semiconductor market share by 2030 implies a research-output response that should eventually appear as a break in this trend line; none is yet visible in 2024–2026 publication data.

**The second tier** — South Korea, Hong Kong, and India — is real but small. Korea grew ×4.2 across the period split, essentially matching the field average; its high absolute CAGR translates into a flat share trajectory, meaning Korea is keeping pace with global growth rather than gaining relative weight. Hong Kong shows a similar profile slightly above the field baseline (×5.2). India's trajectory is the most striking in ratio terms (×14.4) but starts from a single paper across all of 2015–2020; its 5.5% P2 share reflects post-2021 emergence rather than sustained capacity. Together, the three represent about 16% of the field's output.

### Outlook

Extrapolating the 2015–2025 trend lines forward suggests that, absent policy or funding disruptions, China's share continues to rise through the end of the decade while the U.S. and European shares compress further. These extrapolations are model outputs, not forecasts — the CHIPS Act (2022), EU Chips Act (2023), and China's parallel industrial-policy programmes post-date most of the fit window, and any research-publication response to them will lag their passage by three to five years. A more cautious reading is that China's current advantage is structural enough that any convergence will depend on the comparative scale of the competing policy interventions, not on organic contribution trends alone.

### Caveats

Affiliation geography is not funding geography — a paper whose first author sits at a U.S. university may be funded by a foreign entity and vice versa. We report only institutional affiliation, following standard bibliometric practice. Country counts for contributors below roughly 30 papers carry enough year-to-year noise that growth ratios for Korea, Hong Kong, and India should be read as directional, not precise. The any-affiliation counting rule slightly inflates aggregate counts for internationally-collaborated papers; in this corpus international collaboration is rare (~1% of papers), so the inflation is negligible. The 2026 data point is partial at the time of analysis because Scopus indexing continues after publication; it appears in the time-series figures but is excluded from rate calculations.

---

### Suggested figures and where to place them

The three callouts in the section map to existing figures in the pipeline output. All are available as both PDF (for typesetting) and PNG (for preview) in `scopus_out10/figures/`.

| Callout | Figure file | Description |
|---|---|---|
| **Figure X** | `fig_geo_totals` | Top-10 country contributions, 2015–2026 totals. Horizontal bar chart with country labels; the natural "who's there" figure. |
| **Figure Y** | `fig_geo_trends` | Top-5 country year-by-year trajectories. Line chart with markers, 2015–2026. Best shows the China takeoff around 2022 and the U.S. plateau. |
| **Figure Z** | `fig_geo_periods` | Period comparison P1 (2015–2020) vs P2 (2021–2025) as grouped horizontal bars, top-8 contributors. Visually anchors the "phase shift" paragraph. |
| **Figure W** | `fig_geo_share_delta` | Share-delta (P2 − P1) diverging horizontal bar chart for the top-6 including the Europe bloc. Gainers in one colour, losers in another, zero line marked and values annotated. The sharpest visual rendering of the "who gained / who lost" story. |

Two supplementary figures are also available if you want them for an appendix or online supplement:

| Figure file | Description |
|---|---|
| `fig_geo_forecast_counts` | Top-6 (including Europe bloc) with exponential fits extended to 2030. Shows the wide variance between the China curve and the rest. |
| `fig_geo_forecast_share` | Top-6 share trajectories with linear fits. Makes Europe's flat ~12% share visually explicit. |

One caveat: `fig_geo_periods` in its current form shows the top 8 *individual* countries (including Germany, France, etc. separately) rather than the Europe-as-bloc framing used in the table above. If you prefer the figure to match the table exactly, the figure can be regenerated with the bloc treatment — say the word and I'll add that variant. Otherwise the existing figure is fine as a complementary country-level view alongside the bloc table.
