# Patent-landscape analysis for AI-for-Chips

Companion analysis to the publication-based SLR. All counts are patent *families* (deduplicated across jurisdictions) from `patents-public-data.patents.publications` on 2015–2026 publication dates.

## Criterion

To match the SLR's "AI method applied to a chip design task" rule, a patent qualifies as AI-for-Chips only if *all three* conditions hold:

1. Its Cooperative Patent Classification codes include a chip-design/EDA class (G06F30, G06F17/50, G06F115, G06F119, G06F11/22, or G01R31/28). H01L is deliberately excluded: it catches AI-accelerator chip patents (chips-for-AI), power electronics, and process-equipment filings whose AI content is unrelated to chip design.
2. Its CPC codes include a machine-learning class (any subclass of G06N).
3. Its title explicitly names an AI method — one of *artificial intelligence*, *machine learning*, *neural network*, *deep learning*, *reinforcement learning*, *graph neural*, *generative adversarial network*, *convolutional*, *recurrent*, *LSTM*, *transformer-based*, *LLM*, *variational autoencoder*, *Bayesian optimization*, *Gaussian process*, *active/self-supervised/semi-supervised learning*, or *diffusion model*.

The title-keyword step is a precision filter: CPC-only filtering leaves residual false positives whose AI content appears in an unrelated claim or dependent patent. Requiring the method to be named in the title matches the rigour of the peer-reviewed journal corpus, where a paper earns an AI-for-Chips tag only when method and task co-occur in the title or abstract.

## Strict AI-for-Chips patent families per company, 2015–2026 (total n = 48)

Per-family list: `patents_strict_list.csv`. Per-company aggregation: `patents_vs_publications_strict.csv`.

| Company | Patent families | Publications in SLR | Patent-to-publication ratio |
|---|---:|---:|---:|
| Samsung | 7 | 28 | 0.25× |
| IBM | 7 | 0 | inf |
| Synopsys | 6 | 0 | inf |
| Cadence | 5 | 0 | inf |
| Siemens | 4 | 14 | 0.29× |
| NVIDIA | 4 | 4 | 1.00× |
| TSMC | 3 | 0 | inf |
| KLA | 3 | 0 | inf |
| Qualcomm | 2 | 4 | 0.50× |
| Google | 2 | 0 | inf |
| ASML | 2 | 0 | inf |
| Huawei | 1 | 0 | inf |
| MediaTek | 1 | 0 | inf |
| Applied Materials | 1 | 0 | inf |
| Intel | 0 | 46 | 0.00× |
| STMicroelectronics | 0 | 41 | 0.00× |
| Infineon | 0 | 21 | 0.00× |
| NXP | 0 | 16 | 0.00× |
| SK Hynix | 0 | 6 | 0.00× |
| Mentor Graphics | 0 | 0 | — |
| Apple | 0 | 0 | — |
| AMD | 0 | 0 | — |
| Meta | 0 | 0 | — |
| Micron | 0 | 0 | — |
| Broadcom | 0 | 0 | — |
| Lam Research | 0 | 0 | — |
| imec | 0 | 0 | — |
| ARM | 0 | 0 | — |

## Sensitivity cuts

**Chip-keyword title filter (n = 155).** Replaces the method-name title regex with a chip-domain keyword set (semiconductor / layout / lithography / mask / metrology / yield / RTL / Verilog / etc., minus a negative list such as battery / medical / autonomous vehicle). Captures filings whose titles use non-method-named conventions (e.g., "Method and apparatus for ..."), at the cost of lower precision. Per-family list: `patents_strict_list_chipkw_sensitivity.csv`.

**Loose OR-based CPC count.** Accepts patents with *either* a chip-design or an AI CPC (not both). Orders of magnitude higher than the strict count; kept only as a sanity-check reference for the corpus size. Per-company aggregation: `patents_vs_publications.csv`.

| Company | Loose families | Strict families |
|---|---:|---:|
| Samsung | 6,323 | 7 |
| IBM | 5,937 | 7 |
| Synopsys | 852 | 6 |
| Cadence | 831 | 5 |
| Siemens | 2,360 | 4 |
| NVIDIA | 1,018 | 4 |
| TSMC | 1,363 | 3 |
| KLA | 202 | 3 |
| Qualcomm | 1,416 | 2 |
| Google | 1,997 | 2 |
| ASML | 222 | 2 |
| Huawei | 3,295 | 1 |
| MediaTek | 210 | 1 |
| Applied Materials | 235 | 1 |
| Intel | 1,895 | 0 |
| STMicroelectronics | 48 | 0 |
| Infineon | 293 | 0 |
| NXP | 276 | 0 |
| SK Hynix | 474 | 0 |
| Mentor Graphics | 266 | 0 |
| Apple | 482 | 0 |
| AMD | 230 | 0 |
| Meta | 478 | 0 |
| Micron | 477 | 0 |
| Broadcom | 14 | 0 |
| Lam Research | 0 | 0 |
| imec | 74 | 0 |
| ARM | 5 | 0 |

## Regenerate

```
python3 analysis/patent_analysis.py --datadir scopus_out10
```
