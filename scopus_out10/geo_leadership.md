# AI-for-Chips — Who leads, who's catching up, where it's going

*Draft narrative for the paper's "Geographic landscape" section. All numbers from the high-confidence AI-for-Chips set (N=320 with resolvable affiliations, 2015–2026). Fits computed on 2015–2025; 2026 is shown but excluded from projections as a partial indexing year. Europe is treated as a bloc (aggregating all EU-27 + UK + Switzerland + Norway) to match the framing of the EU Chips Act and similar industrial-policy instruments.*

## 1. Who leads today

China is the clear contributor leader (105 papers, 29.0% average share of annual output), followed by the United States (68 papers, 27.6%). **Europe is a credible third contributor when treated as a bloc** (31 papers in the fit window, 37 including 2026, 12.1% average share), ahead of South Korea (6.1%), Hong Kong (5.4%, counted separately because Scopus resolves it as a distinct affiliation country), India (4.0%), and a long tail of emerging contributors (Iran, Turkey, Brazil, Canada, UAE, Saudi Arabia, Algeria) each with 1–3 papers over the decade.

A notable feature of the top three is how different their trajectories look once you unfold by year. China's output is sharply accelerating, the U.S. is growing but losing share, and Europe is maintaining a steady ~12% share with flat year-over-year growth.

## 2. How we got here (2015–2025)

China's output was flat through 2015–2019 (1–5 papers/yr) and then accelerated sharply — 11 papers in 2022, 18 in 2023, 39 in 2025. The exponential fit on the full 2015–2025 window gives a compound annual growth rate of **57.4% with R² = 0.95** — a tight, high-confidence fit. China's share of annual AI-for-Chips output rose from essentially zero in 2015 to ~50% by 2025, a gain of **+2.8 percentage points per year** of share capture.

The United States looks strong on its own terms — **18.4% CAGR** on counts, continued presence in top-5 every year — but the share trajectory tells the real story: U.S. share slides at **−2.1 percentage points per year**, peaking at ~35% in 2020 and settling into the mid-teens by 2025. This is the classic "growing but losing share" pattern: the U.S. is doing more absolute work, but China is adding papers roughly 3× faster.

Europe as a bloc shows a different pattern from both China and the U.S. Absolute counts rise steadily (CAGR 16.7%, R² = 0.70), but the share trend is essentially flat (+0.08 pp/yr, R² = 0.0), meaning European contributions are keeping pace with global growth without gaining relative weight. Internally, the bloc is heavily concentrated: Germany accounts for 12 of the 37 papers, Belgium for 5 (reflecting imec's outsized role in European semiconductor research), and Italy, France, Greece, and the United Kingdom tie at 3 each. The Netherlands, Switzerland, Austria, Portugal, and Denmark round out participation at 1–2 papers. No single European country reaches top-5 status individually; it is only the bloc framing that places Europe as the third contributor.

South Korea and India are the emerging-contender stories. Korea shows a high CAGR (46.9%) but on a small base — the R² of 0.78 is acceptable but not tight, and the share trend is essentially flat (+0.36 pp/yr, R² = 0.04), meaning Korea is keeping pace with global growth rather than gaining share. India shows similar characteristics at a lower level (CAGR 35.6%, flat share).

## 3. A cleaner view: first half vs second half of the decade

Splitting 2015–2025 into two non-overlapping periods — **P1 (2015–2020, 6 years)** and **P2 (2021–2025, 5 years)** — reveals the phase shift more clearly than any CAGR can. The corpus as a whole quadrupled its annual publication rate across the split (10.8 papers/yr → 43.8 papers/yr, a ×4.0 acceleration). What distinguishes the leaders is whether they grew *faster* than that baseline.

| | P1 rate (/yr) | P2 rate (/yr) | Rate × (P2 / P1) | P1 share | P2 share | Share Δ |
|---|---|---|---|---|---|---|
| **China** | 2.5 | **18.0** | **×7.2** | 23% | **41%** | **+18 pp** |
| United States | 3.2 | 9.8 | ×3.1 | 29% | 22% | −7 pp |
| Europe (bloc) | 1.7 | 4.2 | ×2.5 | 15% | 10% | −6 pp |
| South Korea | 0.7 | 2.8 | ×4.2 | 6% | 6% | +0 pp |
| Hong Kong | 0.5 | 2.6 | ×5.2 | 5% | 6% | +1 pp |
| India | 0.2 | 2.4 | ×14.4 | 2% | 6% | +4 pp |
| *Corpus (field average)* | *10.8* | *43.8* | *×4.0* | 100% | 100% | — |

Three readings fall out immediately:

- **Only China and India beat the field's ×4.0 acceleration.** China at ×7.2 and India at ×14.4 are the two actors whose *relative weight* in AI-for-Chips grew post-2020. India's ratio is larger but it starts from a microscopic base (one paper over six years).
- **The U.S. and Europe both grew absolutely and shrank relatively.** Both crossed the P2 boundary with healthy absolute acceleration — U.S. tripled, Europe 2.5×'d — but fell below the field average, so their shares compressed. The U.S. went from **leader to challenger** (29% → 22%), and Europe slipped from 15% to 10%.
- **In P1, the U.S. was #1.** China was the #2 contributor in 2015–2020 (23% vs U.S. 29%). The leadership swap happens during the P1→P2 transition; by 2022–2023 China is clearly ahead, and by 2025 it outpublishes the U.S. by more than 3× in a single year.

The inflection is more specific than "post-2020" — within P2, China's output flattens at ~5 papers/yr through 2021 and then ramps sharply from 2022 onward (11 → 18 → 18 → 39). The LLM-for-EDA wave (VeriGen, ChatEDA, LayoutCopilot, Atelier) and the GNN-for-placement / HT detection waves both crest during this same period, and China's share of those specific subfields is disproportionately high — the geographic and methodological accelerations are the same phenomenon.



## 4. Where it's going (projections)

Under the assumption that the 2015–2025 trends continue — a strong assumption we'll qualify below — the exponential and linear fits project to 2028 and 2030 as follows:

| Country / bloc | 2025 actual (count) | Proj. 2028 | Proj. 2030 | Proj. share 2028 | Proj. share 2030 |
|---|---|---|---|---|---|
| China | 39 | 144 | 358 | 51% | 57% |
| United States | 11 | 21 | 29 | 11% | 6% |
| Europe (bloc) | 6 | 9 | 12 | 13% | 13% |
| South Korea | 12 | 17 | 38 | 9% | 10% |
| Hong Kong | ~3 | 6 | 9 | 5% | 5% |
| India | 4 | 9 | 17 | 7% | 8% |

**What to read into these numbers:**

- **China's consolidation is the dominant signal.** A ~57% CAGR sustained through 2030 would push China's share past 50% — majoritarian leadership. Whether this actually materializes depends on whether the 2015–2025 acceleration reflects a durable research capacity or a funding pulse driven by 2018–2022 industrial-policy shifts. The fit is tight but the underlying driver is policy-dependent.
- **The U.S. projection is the weakest component of the model** (Exp R² = 0.57). U.S. output peaked in 2023 and has since plateaued, so a forward-looking exponential fit captures an average rather than a trend. Share projections to 6% by 2030 likely overstate the relative decline — the more honest reading is "U.S. is growing slowly while China grows fast, eroding the U.S. share of the conversation." The U.S. CHIPS and Science Act (2022) post-dates most of the fit window; its full effect on research output would not yet be visible and would not be captured by a 2015–2025 trend.
- **Korea is worth watching as the next-break-out candidate.** A 47% CAGR on a small base is a high-variance prediction, but Korea sits alongside the largest semiconductor industry ecosystem outside of the U.S. and China. The projected 38 papers in 2030 would put it at roughly U.S. 2025 levels.
- **Europe's share is remarkably stable but shows no acceleration.** The bloc's ~12% share holds flat across the decade (share R² = 0.0, slope ≈ +0.08 pp/yr), meaning Europe is running to stand still. With the EU Chips Act (2023) explicitly targeting a doubling of European semiconductor market share by 2030, the question worth watching is whether this fit reflects Europe's structural ceiling or the pre-policy baseline. A flat share combined with a positive absolute CAGR (16.7%) says that Europe is growing with the field but not faster — any post-2023 acceleration from the Chips Act will show up as a break in this trend line. None is visible yet in 2024–2026 data.
- **Within Europe, Germany and Belgium dominate the signal.** Germany's 12 papers (about a third of the European total) reflect the strength of Fraunhofer institutes and university groups at TU Dresden, RWTH Aachen, and Munich; Belgium's 5 papers trace almost entirely to imec and its university partners (KU Leuven, Ghent). The remainder of the bloc's contribution is distributed across 9 countries at 1–3 papers each — the definition of a dispersed research base where no single national node reaches critical mass on its own.

## 5. What this tells a reader

Four points we can confidently make in the paper:

1. **AI-for-Chips is consolidating geographically.** The field's growth is disproportionately carried by a single country. This is structurally different from many areas of CS where contribution diffuses outward over time.
2. **The U.S. is entering a relative-decline phase** even as its absolute output rises. Any narrative that frames AI-for-Chips as a U.S.-led field is a 2018–2021 reading, not a 2024–2026 reading.
3. **Europe is stable at the third position but not closing the gap.** Treated as a bloc, Europe holds a steady ~12% share across the decade. Internally the bloc is dispersed (Germany 32% of European output, Belgium 14%, rest distributed thinly). The EU Chips Act's effect on research-publication volume, if any, is not yet visible in 2024–2026 data.
4. **The non-China/U.S./Europe tier is real but small.** Korea, Hong Kong, and India together represent about 16% of the field and are all growing absolute counts. None are yet positioned to challenge the top three individually, but collectively they complicate a tripolar narrative that includes only China, U.S., and Europe.

## 6. Caveats

- **2026 is partial.** Scopus indexing lag means 2026 papers are still trickling in as of this writing; the single 2026 data point per country is shown but not used in fits.
- **Counting rule.** A paper is counted once per unique country in its affiliation list (*any-affiliation* rule). Among 320 resolvable papers, international collaboration is rare (~1%), so the rule choice has minimal effect — fractional counting would change none of the top-5 rankings.
- **Small-N for trailing tiers.** CAGR and share trends are calculated on yearly counts that for Korea, Hong Kong, and India often fall below 5 papers/yr. Year-to-year variance is large; the fits are indicative, not precise.
- **No policy-shock modelling.** The CHIPS Act (U.S., 2022), EU Chips Act (2023), and China's accelerated semiconductor-independence drive post-date most of the fit window. Projected values assume the pre-shock trend continues; actual post-2026 outcomes will reflect these investments and their lagged research-publication cycle (typically 3–5 years).
- **Affiliation ≠ funding source.** A paper with a first author at a U.S. university may be funded by a foreign entity or vice versa. This review reports institutional geography, not geopolitical attribution.

## Outputs

- **`scopus_out10/geo_forecast.csv`** — machine-readable metrics per country
- **`scopus_out10/geo_forecast.md`** — compact tabular summary (this file is the narrative version)
- **`scopus_out10/figures/fig_geo_forecast_counts.{pdf,png}`** — top-5 annual count curves with exponential fits + projection dashes
- **`scopus_out10/figures/fig_geo_forecast_share.{pdf,png}`** — top-5 share trajectories with linear fits + projection dashes

*Regenerate with `python3 analysis/geo_forecast.py --datadir scopus_out10 --top 5`.*
