# AI for Chips — SLR dataset

Data artefacts for the systematic literature review on AI methods applied across the silicon lifecycle.

**Companion code repository:** [ignaciosim/AI4Chips_SLR](https://github.com/ignaciosim/AI4Chips_SLR) — the pipeline that produces everything here.

---

## Contents

### `corpus/` — primary snapshot (2015–2026)

Full Scopus retrieval + downstream processing for the current pipeline run. ~67 MB.

| File / subdirectory | Description |
|---|---|
| `raw_scopus_all.jsonl` + `.csv` | Merged, deduplicated Scopus records across six lifecycle phases (N = 5,531). |
| `raw_scopus_<phase>.jsonl` + `.csv` | Per-phase retrievals (design, fabrication, packaging, transit, in_field, disposal). |
| `scopus_counts_by_stage_year.csv` | Per-stage × per-year retrieval counts. |
| `classified_scopus.csv` | Ontology-based classification of every paper (directionality, method tags, chip tasks, hardware artefacts, AI workloads). |
| `pivot_ai_methods_*.csv` | AI method × year / × stage pivot tables. |
| `final_ai4chips_high_only.csv` + `.json` | High-confidence AI-for-Chips subset after GaN false-positive filtering (N = 321). |
| `classification_summary.txt` | Text summary of classification distribution. |
| `openalex_cache/openalex_ai4chips.json` | OpenAlex metadata (citation counts, full author lists, reference lists) for the AI-for-Chips subset. |
| `abstracts_cache.json` | Abstracts per DOI fetched from OpenAlex → Elsevier → publisher-meta fallback chain. |
| `papers_manual.html` | VPN-ready HTML list of paywalled shortlist papers with inline abstracts. |
| `papers_download_log.csv` | Per-paper OA/paywall/error status and Unpaywall licence string at retrieval time. |
| `existing_refs.json` | Structured metadata for the manuscript's pre-existing references. |
| `references.bib` | IEEE BibTeX file for the manuscript references. |
| `geo_forecast.csv` | Per-country leadership metrics: CAGR, share trajectory, P1/P2 phase comparison. |

Pre-publication narrative drafts (paper-section markdown, stage shortlists with curator gists, acronym glossary, references lookup) are intentionally not part of this public dataset; their contents are intended to live in the manuscript itself.

Rendered figures (PDF + PNG) are *not* committed to this repository — they regenerate deterministically from the code in [AI4Chips_SLR](https://github.com/ignaciosim/AI4Chips_SLR) via `python3 figures/generate_all_figures.py`.

### `external_references_cache/` — OpenAlex external-references corpus

Used by `figures/fig_linguistic_terms.py` to produce the broad-terms trend figures over a ~90 000-title corpus (the full reference graph of the SLR corpus, not just the SLR papers themselves). ~19 MB.

| File | Description |
|---|---|
| `ref_metadata_full.json` | OpenAlex metadata (title, year, DOI) for every external reference cited by any SLR-corpus paper (N ≈ 90 000). |
| `ref_years_full.json` | Publication years indexed by OpenAlex ID, for faster lookup. |

These were fetched once via `analysis/fetch_ref_titles.py` in the companion code repo. Rebuilding them requires ~30 minutes of OpenAlex API calls.

---

## How to reproduce

Clone the code repo alongside this one:

```bash
git clone https://github.com/ignaciosim/AI4Chips_SLR.git
git clone https://github.com/ignaciosim/AI4Chips_SLR_data.git
```

Point the code at the data:

```bash
cd AI4Chips_SLR/elsevier/files
ln -s ../../../AI4Chips_SLR_data/corpus corpus
ln -s ../../../AI4Chips_SLR_data/external_references_cache corpus/openalex_cache
# then point pipeline scripts at ./corpus via --outdir / --datadir flags
```

Or just copy the two data directories into `elsevier/files/`.

---

## Pipeline stages (for orientation)

1. **Fetch** — `fetch_scopus.py` retrieves journal articles from Scopus per lifecycle phase (2015–2026, journal-only, curated venue list).
2. **Merge** — `merge_scopus.py` deduplicates per-phase pulls into `raw_scopus_all.jsonl`.
3. **Classify** — `classify_scopus.py` applies ontology-based directionality classification and method tagging.
4. **Filter** — `create_final_high_confidence_only.py` narrows to high-confidence AI-for-Chips papers and removes GaN material false positives.
5. **Shortlist** — `analysis/generate_stage_shortlist.py` curates 52 exemplar papers across five stages using a blended criterion (anchors, exemplars, recent, newest).
6. **Augment** — `analysis/download_shortlist.py` fetches OA PDFs and abstracts for the shortlist. `analysis/build_ieee_refs*.py` produces IEEE references + BibTeX. `analysis/geo_forecast.py` produces country-level analysis.
7. **Figures** — `figures/generate_all_figures.py` and standalones render all 40 publication figures.

See the code repo's top-level README / CLAUDE.md (if present) for the full command list.

---

## Versioning

This dataset snapshot corresponds to code commit `e76d2a1` of [AI4Chips_SLR](https://github.com/ignaciosim/AI4Chips_SLR). The directory was previously named `scopus_out10/` to reflect its position as the tenth iteration of the pipeline during development; it has been renamed to `corpus/` for the public release. Earlier pipeline runs are historical artefacts not preserved here.

---

## License

This repository is released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — see [`LICENSE`](LICENSE) for the full legal text. Curated annotations and derived artefacts are covered by this licence; underlying Scopus records remain subject to Elsevier's Scopus API terms of use, and OpenAlex-sourced metadata is provided under CC0. See [`NOTICE`](NOTICE) for the per-asset scope and third-party content carve-outs.
