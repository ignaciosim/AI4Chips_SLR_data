# AI-for-Chips — Country leadership & forecast (N=320)

Fit window: 2015–2025 (2026 excluded as partial). Projections extend to 2030. Counting rule: any-affiliation (papers count once per unique country in their affiliation list).

## Per-country table (top 6)

| Country | Total 2015–2025 | Avg share | CAGR (counts) | Exp R² | Share trend (pp/yr) | Share R² | Proj. count 2028 | Proj. count 2030 | Proj. share 2028 | Proj. share 2030 |
|---|---|---|---|---|---|---|---|---|---|---|
| China | 105 | 29.0% | 57.4% | 0.95 | +2.77 | 0.45 | 144.4 | 357.8 | 51.2% | 56.7% |
| United States | 68 | 27.6% | 18.4% | 0.57 | -2.13 | 0.52 | 20.9 | 29.3 | 10.5% | 6.3% |
| Europe | 31 | 12.1% | 16.7% | 0.7 | +0.08 | 0.0 | 8.8 | 11.9 | 12.8% | 12.9% |
| South Korea | 18 | 6.1% | 46.9% | 0.78 | +0.36 | 0.04 | 17.4 | 37.6 | 9.0% | 9.8% |
| Hong Kong | 16 | 5.4% | 21.2% | 0.38 | -0.03 | 0.0 | 5.8 | 8.5 | 5.2% | 5.2% |
| India | 13 | 4.0% | 35.6% | 0.67 | +0.43 | 0.08 | 9.2 | 16.9 | 7.4% | 8.3% |

## Phase comparison: 2015–2020 vs 2021–2025

Period 1 (P1): 2015–2020, 6 years; Period 2 (P2): 2021–2025, 5 years. *Rate* is papers per year, normalizing for the 6-vs-5 year asymmetry. *Share Δ* is the change in each country's share of global annual output between the two periods.

| Country / bloc | P1 count | P2 count | P1 rate | P2 rate | Rate × | P1 share | P2 share | Share Δ |
|---|---|---|---|---|---|---|---|---|
| China | 15 | 90 | 2.5 | 18.0 | 7.2 | 23.1% | 41.1% | +18.0 pp |
| United States | 19 | 49 | 3.17 | 9.8 | 3.09 | 29.2% | 22.4% | -6.9 pp |
| Europe | 10 | 21 | 1.67 | 4.2 | 2.52 | 15.4% | 9.6% | -5.8 pp |
| South Korea | 4 | 14 | 0.67 | 2.8 | 4.2 | 6.2% | 6.4% | +0.2 pp |
| Hong Kong | 3 | 13 | 0.5 | 2.6 | 5.2 | 4.6% | 5.9% | +1.3 pp |
| India | 1 | 12 | 0.17 | 2.4 | 14.4 | 1.5% | 5.5% | +3.9 pp |
| **Corpus (AI-for-Chips)** | **65** | **219** | **10.83** | **43.80** | **4.04** | 100% | 100% | 0 pp |

## European drill-down

The Europe bloc aggregates 11 countries (37 country-level contributions across 11 distinct countries, 2015–2026). Individual contributions:

| Country | Papers |
|---|---|
| Germany | 12 |
| Belgium | 5 |
| Italy | 3 |
| France | 3 |
| Greece | 3 |
| United Kingdom | 3 |
| Netherlands | 2 |
| Switzerland | 2 |
| Austria | 2 |
| Portugal | 1 |
| Denmark | 1 |

**Reading the columns:**
- *CAGR (counts)* — compound annual growth rate from the exponential fit on yearly paper counts.
- *Exp R²* — fit quality for the count model (1.0 = perfect, < 0.5 = poor fit, treat CAGR as indicative only).
- *Share trend* — linear slope on the country's yearly share (percentage points per year).
- *Share R²* — fit quality for the share trajectory.
- *Projected 2028 / 2030* — extrapolated yearly count and share if the current trend continues. These are model extrapolations, not forecasts — they assume the structure that produced 2015–2025 is unchanged.

## Caveats
- Small-N noise: countries below ~30 total papers produce loose fits. Treat CAGR for Korea / small-contributor countries as directional only.
- The share projection can exceed 100% or go negative if extrapolated far enough; bound your interpretation to the next 3–5 years.
- No policy / funding shocks are modeled. The US CHIPS Act, EU Chips Act, and China's response post-date most of the fit window; their full effect may not yet be visible.
