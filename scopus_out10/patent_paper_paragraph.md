# [Paper section draft] Patent landscape (companion analysis)

*Ready-to-paste subsection for the Results or Discussion. ~460 words plus one table. If space is tight, the table can move to a supplementary appendix and the in-text prose retained.*

---

To situate the publication corpus against industrial activity we ran a companion analysis on Google Patents Public Data [`patents-public-data.patents.publications`, accessed 2026-04-23], applying a patent-side criterion parallel to the publication-side one. A patent qualifies as AI-for-Chips only if (i) its Cooperative Patent Classification codes include both a chip-design/EDA class (G06F30, G06F17/50, G06F115, G06F119, G06F11/22, or G01R31/28) **and** a machine-learning class (any subclass of G06N), and (ii) its title explicitly names an AI method — one of *artificial intelligence*, *machine learning*, *neural network*, *deep learning*, *reinforcement learning*, *graph neural*, *generative adversarial network*, *convolutional*, *recurrent*, *LSTM*, *transformer-based*, *LLM*, *variational autoencoder*, *Bayesian optimization*, *Gaussian process*, *active/self-supervised/semi-supervised learning*, or *diffusion model*. The CPC conjunction mirrors the ontology's dual requirement that a publication co-mention an AI method and a chip-design task; the title-keyword filter removes the residual false positives that CPC-only filtering leaves behind — AI-accelerator chip patents, semiconductor-equipment patents whose AI content sits in an unrelated claim, and simulation patents outside chip design. We report this strict, precision-optimised cut as our headline number; a looser sensitivity cut (chip-CPC ∧ G06N with a chip-keyword-only title filter, 155 families) is retained in the companion data repository for readers who prefer a higher-recall definition.

The strict criterion yields **48 patent families across the 2019–2025 window**. Table N juxtaposes the per-company patent count against the corresponding journal publication count in the SLR corpus for our benchmark of 28 multinationals.

**Table N.** Strict AI-for-Chips patent families (2019–2025) vs. peer-reviewed journal publications (2015–2026) per company.

| Company | Patent families | SLR journal publications |
|---|---:|---:|
| Samsung | 7 | 28 |
| IBM | 7 | 0 |
| Synopsys | 6 | 0 |
| Cadence | 5 | 0 |
| NVIDIA | 4 | 4 |
| Siemens | 4 | 14 |
| TSMC | 3 | 0 |
| KLA | 3 | 0 |
| ASML | 2 | 0 |
| Google | 2 | 0 |
| Qualcomm | 2 | 4 |
| Applied Materials | 1 | 0 |
| Huawei | 1 | 0 |
| MediaTek | 1 | 0 |
| Intel | 0 | 46 |
| STMicroelectronics | 0 | 41 |
| Infineon | 0 | 21 |
| NXP | 0 | 16 |
| SK Hynix | 0 | 6 |
| AMD, Apple, Meta, Micron, Broadcom, Lam Research, Mentor Graphics, imec, ARM | 0 | 0 |

Three observations follow. First, the intersection of the two channels is narrower than either channel alone: only Samsung, Siemens, NVIDIA, and Qualcomm appear on both sides with non-trivial counts, suggesting that most industrial actors concentrate on one disclosure channel rather than both. Second, the patent record captures actors who are largely absent from our peer-reviewed journal corpus because their AI-for-chips work is published at the conference venues (DAC, ICCAD, ISSCC) that our retrieval excluded by design — IBM, Synopsys, Cadence, TSMC, KLA, Google, ASML, Applied Materials, Huawei, and MediaTek fall into this category, and the patent data should therefore be read as complementary coverage rather than as a contradiction. Third, the set of integrated device manufacturers that publishes in peer-reviewed journals but does not patent under this strict criterion — Intel, STMicroelectronics, Infineon, NXP, SK Hynix — is numerically the largest gap in the table; possible readings include that these organisations treat their ML methods as publishable know-how rather than protectable IP, file under subsidiary assignee names our regex does not resolve, or use title conventions that omit the method name. The strict filter certainly under-counts companies whose patent-drafting style is terse (for example, "method and apparatus" titles that do not name the AI technique); the 155-family sensitivity cut in the companion repository places an upper bound.

Google's two families, both on ML-based floorplan/placement, are the patent record behind Mirhoseini et al. [2021] in *Nature*, a known anchor of the publication shortlist and one of the clearest concrete links between an industrial patent filing and a downstream peer-reviewed publication in this review.
