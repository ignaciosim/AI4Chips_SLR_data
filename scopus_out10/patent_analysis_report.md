# Patent-landscape analysis for AI-for-Chips

Companion analysis to the publication-based SLR. All counts are patent *families* (deduplicated across jurisdictions) from `patents-public-data.patents.publications` on 2015–2026 publication dates.

## Criterion

To match the SLR's "AI method applied to a chip design task" rule, a patent qualifies as AI-for-Chips only if it carries **both** a chip-design/EDA CPC (G06F30, G06F17/50, G06F115, G06F119, G06F11/22, G01R31/28, or H01L) **and** a machine-learning CPC (anywhere under G06N).

## Strict AI-for-Chips patent families per company, 2015–2026

| Company | Patent families | Publications in SLR | Ratio |
|---|---:|---:|---:|
| IBM | 552 | 0 | ∞ / — |
| Samsung | 295 | 28 | 10.5× |
| Siemens | 164 | 14 | 11.7× |
| Intel | 136 | 46 | 3.0× |
| Applied Materials | 116 | 0 | ∞ / — |
| Huawei | 79 | 0 | ∞ / — |
| Google | 73 | 0 | ∞ / — |
| KLA | 55 | 0 | ∞ / — |
| Synopsys | 52 | 0 | ∞ / — |
| TSMC | 50 | 0 | ∞ / — |
| ASML | 43 | 0 | ∞ / — |
| NVIDIA | 37 | 4 | 9.2× |
| Cadence | 31 | 0 | ∞ / — |
| SK Hynix | 27 | 6 | 4.5× |
| Micron | 20 | 0 | ∞ / — |
| Qualcomm | 14 | 4 | 3.5× |
| Meta | 12 | 0 | ∞ / — |
| imec | 9 | 0 | ∞ / — |
| Infineon | 9 | 21 | 0.4× |
| Mentor Graphics | 8 | 0 | ∞ / — |
| MediaTek | 7 | 0 | ∞ / — |
| AMD | 7 | 0 | ∞ / — |
| Apple | 6 | 0 | ∞ / — |
| STMicroelectronics | 2 | 41 | 0.0× |
| NXP | 1 | 16 | 0.1× |

## Sensitivity: loose OR-based count for comparison

The loose filter accepts patents with *either* a chip-design or an AI CPC (not both). Under this definition the counts are roughly 10–20× higher but include traditional algorithmic EDA patents with no ML and general-purpose neural-network patents with no chip content. We report loose counts only for methodological sensitivity.

| Company | Loose families | Strict families | Strict / loose |
|---|---:|---:|---:|
| IBM | 5,937 | 552 | 9% |
| Samsung | 6,323 | 295 | 5% |
| Siemens | 2,360 | 164 | 7% |
| Intel | 1,895 | 136 | 7% |
| Applied Materials | 235 | 116 | 49% |
| Huawei | 3,295 | 79 | 2% |
| Google | 1,997 | 73 | 4% |
| KLA | 202 | 55 | 27% |
| Synopsys | 852 | 52 | 6% |
| TSMC | 1,363 | 50 | 4% |
| ASML | 222 | 43 | 19% |
| NVIDIA | 1,018 | 37 | 4% |
| Cadence | 831 | 31 | 4% |
| SK Hynix | 474 | 27 | 6% |
| Micron | 477 | 20 | 4% |
| Qualcomm | 1,416 | 14 | 1% |
| Meta | 478 | 12 | 3% |
| imec | 74 | 9 | 12% |
| Infineon | 293 | 9 | 3% |
| Mentor Graphics | 266 | 8 | 3% |
| MediaTek | 210 | 7 | 3% |
| AMD | 230 | 7 | 3% |
| Apple | 482 | 6 | 1% |
| STMicroelectronics | 48 | 2 | 4% |
| NXP | 276 | 1 | 0% |

## Interpretation

Semiconductor-equipment makers (Applied Materials, KLA, ASML, imec) have disproportionately high AI-qualifying shares of their chip patent output (12–49%), indicating that ML is penetrating process equipment alongside its more visible role in EDA. Pure chipmakers and fabless design houses run at 3–10% strict/loose ratios. Infineon and STMicroelectronics are unusual in publishing more AI-for-Chips journal articles than they patent, consistent with their analog/power-IC focus and their presence in the device-physics and reliability journals indexed by the SLR corpus.

## Regenerate

```
python3 analysis/patent_analysis.py --datadir scopus_out10
```
