# AI for Chips — SLR dataset

Data artefacts for the systematic literature review on AI methods applied across the silicon lifecycle.

**Companion code repository:** [ignaciosim/AI4Chips_SLR](https://github.com/ignaciosim/AI4Chips_SLR) — the pipeline that produces everything here.

---

## Contents

### `corpus/` — primary snapshot (2015–2026)

Full Scopus retrieval + downstream processing for the current pipeline run. ~111 MB.

Retrieval covers six lifecycle phases across three passes — one journal (`SRCTYPE(j) AND DOCTYPE(ar)`) and two conference (`SRCTYPE(p) AND DOCTYPE(cp)`, differing in venue list) — for 18 queries in total. The chain is 19,055 records retrieved → 4,504 removed as duplicates (4,425 exact plus 79 conference papers superseded by an extended journal version) → **14,551 screened** → 707 high-confidence AI-for-Chips → 673 after GaN false-positive removal → **660 analysed** after curation (264 journal articles, 396 conference papers).

| File / subdirectory | Description |
|---|---|
| `scopus_queries.csv` | The 18 Scopus queries as actually issued, one per lifecycle phase × retrieval pass, with `PUBYEAR` templated. |
| `raw_scopus_all.jsonl` + `.csv` | Merged, de-duplicated records across all phases and passes (N = 14,551). |
| `raw_scopus_<phase>.jsonl` | Journal pass, per lifecycle phase (design, fabrication, packaging, transit, in_field, disposal). |
| `raw_scopus_cd_<phase>.jsonl` | First conference pass, per phase. |
| `raw_scopus_cn_<phase>.jsonl` | Second conference pass (broader venue list), per phase. |
| `raw_scopus_venue_counts.csv` | Records retrieved per source title. |
| `classified_scopus.csv` | Ontology-based classification of every screened record (directionality, confidence, method tags, chip tasks, hardware artefacts, AI workloads). |
| `classification_summary.txt` | Text summary of the classification distribution. |
| `pivot_ai_methods_*.csv` | AI method × year / × stage pivot tables. |
| `ai_methods_long.csv` | Long-format paper × method-tag table. |
| `final_ai4chips_high_only.csv` + `.json` | **The analysed corpus (N = 660)** — the set every figure and statistic in the paper is computed over. |
| `high_confidence_pre_curation.csv` + `.json` | The same corpus one step earlier (N = 673): high-confidence AI-for-Chips after GaN false-positive removal but before curation. Retained because it is a step in the PRISMA chain; the 13 papers separating the two are 5 surveys and 8 manual false positives, listed by `create_final_high_confidence_only.py` when it runs. |
| `screening_conference.csv` | Manual screening audit of the conference corpus. |
| `conference_exemplar_candidates.csv` | Candidate conference exemplars considered for the per-stage tables. |
| `patents_strict_list.csv` | AI-for-Chips patent families under the CPC-conjunction plus title-keyword criterion (233 families; Google Patents Public Data snapshot of 26 August 2026). |
| `patents_strict_list_chipkw_sensitivity.csv` | The same list under the alternative chip-keyword title filter. |
| `patents_vs_publications_strict.csv` | Per-company patent families against papers in the analysed corpus. |
| `patents_vs_publications.csv` | The looser OR-based magnitude reference. |
| `case_study_patents.csv` | Patent probes for three case-study papers. |
| `patent_queries.sql` | The complete, expanded BigQuery queries that produced the five patent files above — readable and pasteable into the BigQuery console. Generated from the retrieval script itself (`analysis/patent_analysis.py --print-sql` in the code repository), so it cannot drift from the code that ran. |
| `geo_forecast.csv` + `.md` | Per-country leadership metrics: CAGR, share trajectory, P1/P2 phase comparison. |
| `openalex_cache/openalex_ai4chips.json` | OpenAlex metadata (citation counts, full author lists, reference lists) for the AI-for-Chips subset. |
| `abstracts_cache.json`, `abstracts_openalex.json` | Abstracts per DOI, retrieved via OpenAlex with a Semantic Scholar fallback (92.3% coverage). |
| `existing_refs.json` | Structured metadata for the manuscript's pre-existing references. |
| `references.bib` | IEEE BibTeX file for the manuscript references. |

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
cd AI4Chips_SLR
ln -s ../AI4Chips_SLR_data/corpus corpus
```

Then run, with no further arguments — `DATADIR` defaults to `corpus`:

```bash
make figures      # 21 figure scripts -> corpus/figures/*.png
make analysis     # text analyses to stdout
```

No Scopus credentials are needed: the retrieval stage does not fire when the
corpus is already present. `make patents` is the exception, requiring Google
Cloud credentials; its outputs are already included here.

`external_references_cache/` is consumed directly by
`figures/fig_linguistic_terms.py`, which takes its path as an argument; it does
not need to be linked into `corpus/`.

Or copy the two data directories into the code repository root instead of
symlinking.

---

## Pipeline stages (for orientation)

1. **Fetch** — `fetch_scopus.py` retrieves records from Scopus per lifecycle phase (2015–2026, curated venue list). Journal articles by default; `--conferences` swaps the source-type filter to conference proceedings.
2. **Merge** — `merge_scopus.py` de-duplicates per-phase pulls into `raw_scopus_all.jsonl`, by record identifier and then by an extended-version pass that collapses a conference paper into its journal extension.
3. **Classify** — `classify_scopus.py` applies ontology-based directionality classification and method tagging.
4. **Filter** — `create_final_high_confidence_only.py` narrows to high-confidence AI-for-Chips papers and removes GaN material false positives.
5. **Shortlist** — `analysis/generate_stage_shortlist.py` applies curation (surveys, manual exclusions) and pins the 49 exemplar papers displayed in the manuscript across five stages; `--show-candidates` emits the full algorithmic ranking instead.
6. **Augment** — `analysis/download_shortlist.py` fetches OA PDFs and abstracts for the shortlist. `analysis/build_ieee_refs*.py` produces IEEE references + BibTeX. `analysis/geo_forecast.py` produces country-level analysis.
7. **Figures** — `figures/generate_all_figures.py` and standalones render the publication figures (PNG by default; set `SLR_FIG_PDF=1` for PDF).

See the code repo's top-level README / CLAUDE.md (if present) for the full command list.

---

## Versioning

This dataset snapshot corresponds to code commit `f83c5ab` of [AI4Chips_SLR](https://github.com/ignaciosim/AI4Chips_SLR), and to the revised manuscript. It was produced by the pipeline run held locally as `scopus_out12/` and renamed to `corpus/` for release.

The previous snapshot — the journal-only corpus accompanying the **submitted** manuscript, N = 5,531 screened and 321 high-confidence — is preserved at tag [`snapshot-submitted`](https://github.com/ignaciosim/AI4Chips_SLR_data/releases/tag/snapshot-submitted) so that the figures in the submitted version remain auditable. The two differ in more than corpus size: the revision added conference proceedings, corrected the ontology matcher from substring to word-boundary matching, and collapsed extended-version duplicates. Numbers are not comparable between the two snapshots without reading the code repository's commit history.

Patent counts are reproducible only against a dated snapshot of Google Patents Public Data: the identical query — `corpus/patent_queries.sql`, unchanged in text between the two runs — returned 48 families in April 2026 and 233 in August 2026, the April result being a strict subset of the August one. The figures here are the snapshot of **26 August 2026**. Re-running the query today will return more families again; that is a property of the underlying dataset, not of the criterion.

Earlier pipeline runs are historical artefacts not preserved here.

---

## License

This repository is released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — see [`LICENSE`](LICENSE) for the full legal text. Curated annotations and derived artefacts are covered by this licence; underlying Scopus records remain subject to Elsevier's Scopus API terms of use, and OpenAlex-sourced metadata is provided under CC0. See [`NOTICE`](NOTICE) for the per-asset scope and third-party content carve-outs.
