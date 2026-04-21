# [Conclusion draft] The broken digital thread

*A ~350-word subsection for the paper's conclusion, framing the stage-level findings as symptoms of a single underlying systemic gap. Can be trimmed to a single closing paragraph (~180 words) by collapsing the middle paragraph — see the "tight variant" at the bottom.*

---

## The broken digital thread

Stepping back from the stage-by-stage reading, a common pattern emerges across the findings. Most of the AI-for-Chips work reviewed here addresses problems that are local to a single lifecycle phase, because the data itself is local to that phase. When papers do appear at stage boundaries, they tend to be *reconstructions of provenance* that a continuous digital thread would have preserved directly: EM-side-channel fingerprinting of counterfeit ICs (Stern 2020), age prediction from IO-pad protection diodes for recycled chips (Narwariya 2025), graph-convolutional hardware-trojan localization without a golden reference (Yasaei 2022, 2025). These are among the most methodologically sophisticated entries in our corpus — and they are sophisticated precisely because they have to infer what should have been recorded.

The deeper observation is that every time a chip crosses a lifecycle boundary, information is lost. Design intent is not carried into fabrication decisions. Die-level provenance is typically discarded at lidding. The journey from foundry to system integrator is essentially untelemetried. The empty Disposal stage of our corpus is not a query artefact; it is the shape of the field. The very existence of ML-based recycled-IC detection is evidence that a chip's *provenance* is not maintained end-to-end, and the proliferation of runtime hardware-trojan detectors is evidence that the *integrity* of its supply chain is not either.

Industrial infrastructure to close these gaps is beginning to appear — Silicon Lifecycle Management platforms from Synopsys and Siemens Tessent, chiplet-metadata standards via UCIe, and the EU Digital Product Passport (Regulation 2024/1781, effective 2027). What our survey suggests is that the academic ML-for-Chips community has not yet responded to this shift. The next productive frontier is not deeper models applied to single-stage tasks; it is models that consume *cross-stage* data — design intent plus fabrication signatures plus field telemetry — to solve problems invisible to any one stage considered alone. The methodological techniques already exist in the shortlist of this review. The data infrastructure to let them work, largely, does not. Closing that gap is where the next wave of foundational contributions will come from.

---

### Tight variant (~180 words, single paragraph)

*Use this if the full three-paragraph version feels too long for your conclusion section.*

A final observation cuts across all six stages. Most of the AI-for-Chips work reviewed here solves problems local to a single lifecycle phase, because the data itself is local to that phase. When papers appear at stage boundaries, they tend to be *reconstructions of provenance* that a continuous digital thread would have preserved directly — EM-side-channel counterfeit detection (Stern 2020), age prediction from IO-pad diodes for recycled chips (Narwariya 2025), hardware-trojan localization without a golden reference (Yasaei 2022, 2025). These are among the most methodologically sophisticated entries in the corpus precisely because they have to infer what should have been recorded. The empty Disposal stage is not a query artefact; it is the shape of the field. Emerging industrial infrastructure — Silicon Lifecycle Management platforms, UCIe chiplet metadata, and the EU Digital Product Passport (Regulation 2024/1781, effective 2027) — is beginning to address the data gap. The corresponding shift in ML-for-Chips research, from stage-siloed to *thread-aware* models that ingest design, fabrication, and field data jointly, has not yet happened. It is where the next wave of foundational contributions will originate.

---

### Notes for placement

- The paper-anchor citations (Stern 2020, Narwariya 2025, Yasaei 2022/2025) are already in the shortlist, so they'll be in your bibliography by the time this conclusion runs; you're just reusing them for narrative weight.
- The Regulation 2024/1781 citation needs a formal reference entry — the full title is *Regulation (EU) 2024/1781 of the European Parliament and of the Council … establishing a framework for the setting of ecodesign requirements for sustainable products* (commonly called the ESPR / Digital Product Passport regulation). Worth double-checking the exact citation format your target journal uses.
- Synopsys SLM and Siemens Tessent are industry product lines, not peer-reviewed work — they're fine to cite as vendor whitepapers or footnotes, not as primary references. If your target venue is uncomfortable with that, you can drop the vendor names and say "industry platforms for silicon lifecycle management" generically.
- The "cross-stage ML" framing at the end can be sharpened with a concrete example if your paper elsewhere discusses STCO / DTCO or digital twins — those are natural vehicles for thread-aware ML.
