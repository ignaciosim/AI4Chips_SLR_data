# [Paper section draft] Limitations

*Ready-to-paste subsection for the Discussion. ~350 words; can be shortened by merging (i)/(ii) on database and document-type together, or by dropping (vi) on corpus recency.*

---

This review carries several methodological limitations that a reader should weigh when interpreting the findings.

**(i) Single-database retrieval.** We searched Scopus only. PRISMA 2020 recommends two or more databases to reduce coverage gaps; we chose Scopus for its breadth across IEEE/ACM/Elsevier engineering venues and its integration with OpenAlex for downstream bibliometrics. The principal risk is that journals indexed in IEEE Xplore or Web of Science but not in Scopus — a small set for engineering journals in the 2015–2026 window — would be systematically missing. A cross-check pull from IEEE Xplore for the top-cited Fabrication venues (IEEE TCAD, IEEE TVLSI, IEEE TSM) returned no additional high-confidence AI-for-Chips papers outside the Scopus set, but we note the limitation.

**(ii) Journal-only, peer-reviewed filter.** We excluded conference proceedings, workshops, and preprint servers (arXiv). This choice trades recall for signal quality: conference AI-for-chips work — particularly at DAC, ICCAD, and ISSCC — is extensive but also includes workshop posters and work-in-progress that are difficult to separate from finished research. The AI-for-Chips shortlist therefore under-represents industrial contributions that appear primarily in conference form, and early-stage academic work that has not yet cleared peer review.

**(iii) Ontology substring collisions.** The ontology-based classifier matches lexical surface forms against titles and abstracts. Three substring-collision patterns surfaced during manual audit and are documented in the code: (a) the "GAN" / "GaN" collision (generative adversarial network vs. gallium nitride material), caught by a dedicated filter that removed 15 papers; (b) the "ilt" / "built" collision that mis-tagged several built-in-self-test papers as lithography-optimization work; and (c) keyword-driven "LLM" / "RAG" tags on pre-LLM-era papers triggered by unrelated substrings. Manual curation corrected the classifier's output on 19 papers where substring collisions produced confident-looking but clearly wrong classifications; all excluded DOIs and their rationales are documented in `analysis/generate_stage_shortlist.py`.

**(iv) Editorial curation.** Beyond the automated filters, the per-stage shortlists reflect editorial judgements on survey removal, stage reassignment, and one topical promotion (Seo et al. 2025 on AI-for-ALD, surfaced as a "Curator" pick despite low citation count). These decisions are individually justified in the code comments but remain the authors' calls; a different editor could defensibly produce a different 53-paper shortlist from the same 298-paper corpus.

**(v) Language.** Queries were in English; work published in Chinese, Japanese, Korean, or other languages is under-represented. Given that China accounts for roughly 40% of the corpus under English-language search, this is a meaningful constraint on coverage of the 2022–2025 Chinese contribution.

**(vi) Corpus recency.** Scopus indexing lag means 2026 coverage is partial at the time of analysis. The 2026 data point appears in time-series figures but is excluded from trend fits and period comparisons; the shortlist does include 2026 papers under a "Newest" tier that explicitly surfaces them regardless of citation count, since citation accumulation is not a viable ranking signal within months of publication.

**(vii) Affiliation versus funding.** Our geographic analysis counts per-paper country by author affiliation (any-country rule). A paper whose first author sits at a U.S. university may be funded by a foreign entity and vice versa. We report institutional affiliation following standard bibliometric practice; readers should not read national publication share as a direct proxy for national research funding.
