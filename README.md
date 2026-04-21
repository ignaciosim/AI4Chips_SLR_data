# AI for Chips — SLR dataset

Data artefacts for the systematic literature review on AI methods applied across the silicon lifecycle.

**Companion code repository:** [ignaciosim/AI4Chips_SLR](https://github.com/ignaciosim/AI4Chips_SLR) — the pipeline that produces everything here.

---

## Contents

### `scopus_out10/` — primary snapshot (2015–2026)

Full Scopus retrieval + downstream processing for the 10th (current) pipeline run. ~67 MB.

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
| `papers_oa/` | Open-access PDFs auto-downloaded via Unpaywall (where available). |
| `papers_manual.html` | VPN-ready HTML list of paywalled shortlist papers with inline abstracts. |
| `papers_download_log.csv` | Per-paper status of OA/paywall/error outcomes. |
| `stage_shortlists.md` + `stage_shortlists_enriched.md` | Curated per-stage shortlist of 52 exemplar papers with gists and acronym glossary. |
| `gists.json` | Hand-curated one-line contribution summaries per shortlisted paper. |
| `stage_summaries.json` | Per-stage narrative paragraphs used in the paper. |
| `acronyms.md` | Glossary of acronyms used in the shortlist tables. |
| `existing_refs.json` | Structured metadata for the manuscript's pre-existing references [1]–[14]. |
| `references.bib` | Full IEEE BibTeX file (76 entries: 14 pre-existing + 52 shortlist + can be extended). |
| `references_ieee.docx` + `.md` | Paste-ready IEEE reference list with hyperlinked DOIs. |
| `references_lookup.md` | Author-Year → BibTeX key → `[N]` number mapping. |
| `geo_forecast.csv` + `.md` | Per-country leadership metrics: CAGR, share trajectory, P1/P2 phase comparison. |
| `geo_leadership.md` + `geo_paper_section.md` | Narrative drafts for the geographic-landscape section of the paper. |
| `conclusion_digital_thread.md` | Narrative draft for the paper's closing "broken digital thread" argument. |
| `figures/` | Publication-quality PDF + PNG figures (40 figures: pub volume, growth model, methods, tasks, geo, citations, linguistic terms, forecasts). |

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
ln -s ../../../AI4Chips_SLR_data/scopus_out10 scopus_out10
ln -s ../../../AI4Chips_SLR_data/external_references_cache scopus_out7/openalex_cache
# then all pipeline scripts work unchanged
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

This dataset snapshot corresponds to code commit `e76d2a1` of [AI4Chips_SLR](https://github.com/ignaciosim/AI4Chips_SLR), pipeline run number 10. Earlier pipeline runs (`scopus_out1` through `scopus_out9`) are historical artefacts not preserved here; only the 10th run represents the corpus referenced in the paper.

---

## License

Data curation and extracted metadata fall under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Underlying Scopus and OpenAlex records remain subject to their respective terms of use (Elsevier Scopus API terms; OpenAlex CC0). The included OA PDFs in `papers_oa/` are copyrighted by their respective publishers and included under the original open-access licences displayed in the `papers_download_log.csv`.
