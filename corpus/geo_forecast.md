# AI-for-Chips — Country leadership & forecast (N=668)

Fit window: 2015–2025 (2026 excluded as partial). Projections extend to 2030. Counting rule: any-affiliation (papers count once per unique country in their affiliation list).

## Per-country table (top 5)

| Country | Total 2015–2025 | Avg share | CAGR (counts) | Exp R² | Share trend (pp/yr) | Share R² | Proj. count 2028 | Proj. count 2030 | Proj. share 2028 | Proj. share 2030 |
|---|---|---|---|---|---|---|---|---|---|---|
| United States | 191 | 38.5% | 14.5% | 0.79 | -3.19 | 0.62 | 47.1 | 61.7 | 13.0% | 6.6% |
| China | 173 | 23.2% | 57.7% | 0.98 | +2.86 | 0.68 | 236.6 | 588.4 | 46.0% | 51.8% |
| Europe | 64 | 11.1% | 19.3% | 0.72 | +0.06 | 0.0 | 20.7 | 29.5 | 11.6% | 11.7% |
| South Korea | 38 | 5.4% | 65.8% | 0.82 | +0.52 | 0.24 | 60.4 | 166.1 | 9.5% | 10.6% |
| Hong Kong | 35 | 4.4% | 27.4% | 0.56 | +0.69 | 0.32 | 17.0 | 27.6 | 10.0% | 11.4% |

## Phase comparison: 2015–2020 vs 2021–2025

Period 1 (P1): 2015–2020, 6 years; Period 2 (P2): 2021–2025, 5 years. *Rate* is papers per year, normalizing for the 6-vs-5 year asymmetry. *Share Δ* is the change in each country's share of global annual output between the two periods.

| Country / bloc | P1 count | P2 count | P1 rate | P2 rate | Rate × | P1 share | P2 share | Share Δ |
|---|---|---|---|---|---|---|---|---|
| United States | 68 | 123 | 11.33 | 24.6 | 2.17 | 40.5% | 28.9% | -11.5 pp |
| China | 28 | 145 | 4.67 | 29.0 | 6.21 | 16.7% | 34.1% | +17.5 pp |
| Europe | 21 | 43 | 3.5 | 8.6 | 2.46 | 12.5% | 10.1% | -2.4 pp |
| South Korea | 8 | 30 | 1.33 | 6.0 | 4.5 | 4.8% | 7.1% | +2.3 pp |
| Hong Kong | 8 | 27 | 1.33 | 5.4 | 4.05 | 4.8% | 6.4% | +1.6 pp |
| **Corpus (AI-for-Chips)** | **168** | **425** | **28.00** | **85.00** | **3.04** | 100% | 100% | 0 pp |

## European drill-down

The Europe bloc aggregates 14 countries (74 country-level contributions across 14 distinct countries, 2015–2026). Individual contributions:

| Country | Papers |
|---|---|
| Germany | 28 |
| Belgium | 10 |
| Italy | 8 |
| France | 6 |
| United Kingdom | 5 |
| Portugal | 4 |
| Switzerland | 3 |
| Netherlands | 2 |
| Austria | 2 |
| Greece | 2 |
| Ireland | 1 |
| Denmark | 1 |
| Czech Republic | 1 |
| Malta | 1 |

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
