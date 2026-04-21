# Enriched Stage Shortlists — AI for Chips (40 papers, 2015–2026)

Per-paper analysis derived from reading each abstract.
Verdict legend: **✓ confirmed** = solid AI-for-Chips; **⚠ flag** = likely chips-for-AI or scope issue, consider excluding; **? borderline** = defensible but worth noting; **(no abstract)** = ScienceDirect holdout, VPN read required.

## Summary of findings

- **32 confirmed** AI-for-Chips papers across the 5 displayed stages
- **2 flag** candidates (recommend adding to `EXCLUDE_DOIS`):
  - #22 Pandey 2022 NeuroMap — uses algorithmic task-mapping (not ML) to run DNNs on HBM; chips-for-AI infrastructure work
  - #40 Bahador 2026 MRAM PUF — designs a PUF and uses ML only as the *attacker*; circuit-design paper, AI appears only in the evaluation
- **5 no-abstract** (all ScienceDirect — VPN'd browser needed to verify)
- **6 stage-boundary notes** (clean AI-for-Chips but classified in the wrong stage):
  - #19 Lee 2026 DRAM sense-amp UQ — should be **Design** (DRAM circuit sizing, not fab)
  - #21 Zhang 2021 optical NoC routing — design concern, not packaging
  - #24 Zhao 2025 PDNNet IR drop — design/sign-off, not packaging
  - #32 Kao 2023 wire bonding — packaging/assembly, not in-field
  - #36 Gai 2022 hotspot — fabrication/DFM, not in-field
  - #37 de Jong 2025 solder fatigue — transit-adjacent
- **3 method-tag corrections** (minor; ontology lexicon mismatches):
  - #5 DREAMPlace: not learned DL; reuses DL infra for classical placement
  - #15 Jang wafer yield: abstract says deep learning, tag says classical_ml
  - #16 Ciccazzo: SVM surrogate tagged as bayesian_probabilistic
- **1 domain note:** #38 Saravanan quantum-circuit reliability — applies to quantum NISQ, not conventional CMOS

---

## Design (10)

### #1 Thakur 2024 — VeriGen (anchor, 141 cites)
- **DOI:** [10.1145/3643681](https://doi.org/10.1145/3643681)
- **Verdict:** ✓ confirmed
- **Actual method:** Fine-tuned CodeGen-16B decoder LLM
- **Actual task:** Verilog RTL code generation (precedes synthesis)
- **Gist:** Fine-tunes open-source CodeGen-16B on GitHub+textbook Verilog; outperforms GPT-3.5-turbo by 1.1% with 41% improvement in syntactic correctness over base model. Open-source release.
- **Notes:** Task tag `logic_synthesis` is slightly too narrow — paper is about RTL generation, upstream of synthesis.

### #2 Li 2020 — ANN + GA for analog (anchor, 127 cites)
- **DOI:** [10.1109/TCAD.2019.2961322](https://doi.org/10.1109/TCAD.2019.2961322)
- **Verdict:** ✓ confirmed
- **Actual method:** ANN surrogate (local search) + Genetic Algorithm (global), fully parallelized
- **Actual task:** Analog circuit sizing (op-amp, Chebyshev filter)
- **Gist:** Parallel GA with ANN-based local minimum search replaces SPICE calls, ~4× speedup over traditional GA+SPICE.
- **Notes:** Task tag `design_space_exploration` is too generic — this is specifically analog circuit sizing.

### #3 Wu 2024 — ChatEDA (anchor, 116 cites)
- **DOI:** [10.1109/TCAD.2024.3383347](https://doi.org/10.1109/TCAD.2024.3383347)
- **Verdict:** ✓ confirmed
- **Actual method:** Fine-tuned LLM (AutoMage) as autonomous agent orchestrating EDA tools
- **Actual task:** End-to-end EDA workflow from RTL to GDSII
- **Gist:** LLM agent translates natural-language requirements into task decomposition + tool scripts; AutoMage beats GPT-4 on EDA orchestration.
- **Notes:** Task tag `logic_synthesis` understates scope — this spans the whole backend flow.

### #4 Zhang 2022 — MACE Bayesian optimization (exemplar, 114 cites)
- **DOI:** [10.1109/TCAD.2021.3054811](https://doi.org/10.1109/TCAD.2021.3054811) *(local PDF: Zhang_An_Efficient_Batch_Constrained_Bayesian_Optim.pdf)*
- **Verdict:** ✓ confirmed
- **Actual method:** Parallel Bayesian optimization with Multi-objective Acquisition function Ensemble (PI + EI + LCB, sampled from Pareto front)
- **Actual task:** Constrained + unconstrained analog circuit synthesis
- **Gist:** Ensemble acquisition across PI/EI/LCB with Pareto sampling enables 15–74× speedup over DE/WEIBO at batch size 15.
- **Notes:** Clean fit.

### #5 Lin 2021 — DREAMPlace (exemplar, 107 cites)
- **DOI:** [10.1109/TCAD.2020.3003843](https://doi.org/10.1109/TCAD.2020.3003843)
- **Verdict:** ✓ confirmed (with caveat)
- **Actual method:** *Not* deep learning in the training sense — recasts analytical placement as neural-network *training* and exploits PyTorch GPU kernels/autograd
- **Actual task:** Global placement (physical design)
- **Gist:** Classical analytical placement recast as NN training in PyTorch, 40× GPU speedup over RePlAce without quality loss.
- **Notes:** **Method tag is misleading.** No learned network here — the paper leverages DL *infrastructure* for a classical optimization objective. Might note "uses DL frameworks" rather than "applies deep learning".

### #6 Budak 2022 — ESSAB (exemplar, 106 cites)
- **DOI:** [10.1109/TCAD.2021.3081405](https://doi.org/10.1109/TCAD.2021.3081405)
- **Verdict:** ✓ confirmed
- **Actual method:** ANN surrogate + novel candidate ranking to suppress prediction-error accumulation
- **Actual task:** Analog circuit sizing with full (stringent) spec sets
- **Gist:** Addresses ML-cost / error-accumulation failure modes that other ML-assisted sizers hide by testing on reduced spec sets.
- **Notes:** Clean.

### #7 Liu 2025 — LayoutCopilot (recent, 22 cites)
- **DOI:** [10.1109/TCAD.2025.3529805](https://doi.org/10.1109/TCAD.2025.3529805)
- **Verdict:** ✓ confirmed
- **Actual method:** LLM-based multi-agent collaborative framework
- **Actual task:** Analog layout (interactive; natural-language → EDA scripts)
- **Gist:** LLM multi-agent lowers EDA-tool learning curve by translating design intent into executable layout scripts.
- **Notes:** Clean.

### #8 Wu 2023 — IronMan-Pro (recent, 51 cites)
- **DOI:** [10.1109/TCAD.2022.3185540](https://doi.org/10.1109/TCAD.2022.3185540)
- **Verdict:** ✓ confirmed
- **Actual method:** GNN predictor (GPP) + RL explorer (RLMD, multi-objective) + code transformer (CT) — three-component end-to-end framework
- **Actual task:** HLS design space exploration (Pareto over resources/area/latency)
- **Gist:** Three-component ML stack reduces HLS prediction errors 10.9× (resources) / 5.7× (CP timing) and finds Pareto solutions with 400× meta-heuristic speedup. Open source.
- **Notes:** Clean.

### #9 Ahmadzadeh 2026 — AnaCraft (newest, 5 cites)
- **DOI:** [10.1109/TCAD.2025.3582175](https://doi.org/10.1109/TCAD.2025.3582175)
- **Verdict:** ✓ confirmed
- **Actual method:** Multi-agent RL (Soft Actor-Critic sizing agents + adversarial PVT agent) + model-based rollouts from probabilistic model ensemble
- **Actual task:** PVT-robust analog circuit sizing (45nm CMOS op-amp, 7nm FinFET data receiver)
- **Gist:** First adversarial multi-agent RL for PVT-robust analog sizing; 3× fewer simulations and 2× runtime reduction vs. SOTA.
- **Notes:** Clean; strong methodological novelty.

### #10 Shen 2026 — Atelier (newest, 4 cites)
- **DOI:** [10.1109/TCAD.2025.3573228](https://doi.org/10.1109/TCAD.2025.3573228)
- **Verdict:** ✓ confirmed
- **Actual method:** General-purpose LLM agents in graph-of-thoughts architecture + curated compact knowledge base (no fine-tuning)
- **Actual task:** Analog circuit design (topology selection, modification, parameter tuning, decision)
- **Gist:** Multi-agent LLM with graph-of-thoughts and compact KB avoids costly domain fine-tuning while specializing each agent for a design sub-task.
- **Notes:** Clean; good complement to AnaCraft (symbolic/knowledge vs. RL approaches to the same task).

---

## Fabrication (10)

### #11 Yang 2020 — GAN-OPC (anchor, 90 cites)
- **DOI:** [10.1109/TCAD.2019.2939329](https://doi.org/10.1109/TCAD.2019.2939329)
- **Verdict:** ✓ confirmed
- **Actual method:** GAN with U-Net generator + subpixel super-resolution; jointly pretrained with Inverse Lithography Technique (ILT)
- **Actual task:** Mask optimization (OPC) in advanced-node lithography
- **Gist:** ILT-pretrained GAN with U-Net generator produces quasi-optimal masks that need fewer conventional OPC iterations.
- **Notes:** Canonical GAN-for-lithography reference; clean.

### #12 Chiu 2021 — Mask R-CNN wafer defects (anchor, 59 cites)
- **DOI:** [10.1109/TSM.2021.3118922](https://doi.org/10.1109/TSM.2021.3118922)
- **Verdict:** ✓ confirmed
- **Actual method:** Mask R-CNN instance segmentation + copy-paste / rotational augmentation + COCO transfer learning
- **Actual task:** Mixed-type wafer-map defect classification + localization
- **Gist:** Mask R-CNN with 1,056 training items (COCO-pretrained) handles mixed-type wafer defects on WM-811K at 97.7% single-type accuracy.
- **Notes:** Clean.

### #13 Cheng 2021 — ML test-induced defects (anchor, 55 cites)
- **DOI:** [10.1109/TSM.2021.3065405](https://doi.org/10.1109/TSM.2021.3065405)
- **Verdict:** ✓ confirmed
- **Actual method:** Multiple classical ML algorithms on test-path features
- **Actual task:** Distinguishing test-induced site-dependent defects from fab-induced defects (yield recovery)
- **Gist:** Analyzes probing-order patterns to classify which bad dies are retrieval candidates vs. real fab defects, 97% across 6 real products.
- **Notes:** Task tag `verification` is misleading — this is yield recovery / test-process diagnosis, not design verification.

### #14 Jiang 2022 — Neural-ILT 2.0 (exemplar, 39 cites)
- **DOI:** [10.1109/TCAD.2021.3109556](https://doi.org/10.1109/TCAD.2021.3109556)
- **Verdict:** ✓ confirmed
- **Actual method:** End-to-end DL network doing mask prediction + ILT correction in one pass; domain-specific (lithography-aware) pretraining
- **Actual task:** Mask optimization (OPC/ILT)
- **Gist:** Single NN for mask prediction + ILT correction, 15–30× TAT speedup over SOTA with better mask complexity.
- **Notes:** Clean.

### #15 Jang 2019 — DL wafer yield prediction (exemplar, 36 cites)
- **DOI:** [10.1109/TSM.2019.2945482](https://doi.org/10.1109/TSM.2019.2945482)
- **Verdict:** ✓ confirmed
- **Actual method:** Deep learning (abstract explicit: "based on deep learning algorithms")
- **Actual task:** Pre-fabrication yield prediction from wafer-map spatial features + die-level yield variation
- **Gist:** DL predicts yield from wafer-map design at pre-production stage, guiding 8.59% higher-productivity wafer-map designs.
- **Notes:** **Method tag `classical_ml` is wrong** — abstract clearly says deep learning.

### #16 Ciccazzo 2016 — SVM surrogate yield (exemplar, 35 cites)
- **DOI:** [10.1109/TCAD.2015.2501307](https://doi.org/10.1109/TCAD.2015.2501307)
- **Verdict:** ✓ confirmed
- **Actual method:** SVM surrogate model inside Monte Carlo yield-optimization loop
- **Actual task:** Parametric yield optimization on STMicro consumer circuits
- **Gist:** SVM surrogate replaces SPICE calls in MC yield optimization; benchmarked against STMicro's industrial reference.
- **Notes:** **Method tag `bayesian_probabilistic` is wrong** — SVM is not Bayesian.

### #17 Huang 2023 — LR+KNN latent defects (recent, 29 cites)
- **DOI:** [10.1016/j.mejo.2022.105641](https://doi.org/10.1016/j.mejo.2022.105641)
- **Verdict:** ? no abstract (ScienceDirect holdout)
- **Actual method:** Linear regression combined with KNN (from title)
- **Actual task:** Latent defect identification in semiconductor manufacturing
- **Gist:** *(abstract unavailable — VPN read required)*
- **Notes:** ScienceDirect holdout.

### #18 Chen 2023 — DevelSet (recent, 23 cites)
- **DOI:** [10.1109/TCAD.2023.3286262](https://doi.org/10.1109/TCAD.2023.3286262)
- **Verdict:** ✓ confirmed
- **Actual method:** Transformer-based multi-branch NN with level-set mask representation + CUDA lithography simulator + CUDA mask optimizer
- **Actual task:** Metal-layer mask optimization (OPC)
- **Gist:** Level-set representation + transformer NN + CUDA kernels delivers ~1s mask optimization with SOTA printability.
- **Notes:** Clean.

### #19 Lee 2026 — ML DRAM sense-amp UQ (newest, 0 cites)
- **DOI:** [10.1109/TCAD.2025.3603112](https://doi.org/10.1109/TCAD.2025.3603112)
- **Verdict:** ✓ confirmed (**but stage-misplaced**)
- **Actual method:** Sobol QMC sampling + 3-stage ML training + Bayesian Optimization
- **Actual task:** DRAM bitline sense-amplifier (BLSA) sizing under process variation (TSMC 65nm)
- **Gist:** QMC + 3-stage ML surrogate + BO cuts BLSA design simulation time 43%, enables process-variation-aware optimization.
- **Notes:** **Stage misplacement — this is chip *design* (BLSA sizing), not fabrication.** Classified here via "process variation" keyword.

### #20 Zhu 2026 — INN-ILT (newest, 0 cites)
- **DOI:** [10.1109/TCAD.2025.3650094](https://doi.org/10.1109/TCAD.2025.3650094)
- **Verdict:** ✓ confirmed
- **Actual method:** Invertible neural network (INN) with physics-embedded coupling layers + permutation layer + hybrid bidirectional loss
- **Actual task:** Inverse lithography (mask optimization)
- **Gist:** Physics-embedded INN unifies forward lithography + inverse mask optimization in a single invertible network.
- **Notes:** Clean; interesting methodological shift from GAN/CNN OPC to invertible architectures.

---

## Packaging (5)

### #21 Zhang 2021 — Approximate Q-learning optical NoC (anchor, 15 cites)
- **DOI:** [10.1109/TCAD.2020.2987775](https://doi.org/10.1109/TCAD.2020.2987775)
- **Verdict:** ✓ confirmed (**with stage caveat**)
- **Actual method:** Table-free approximate Q-learning (function approximation RL)
- **Actual task:** Thermal-aware adaptive routing on silicon-photonic NoC
- **Gist:** Function-approximation Q-learning scales thermal-aware NoC routing without the table-blowup of tabular Q-routing.
- **Notes:** **Stage boundary:** optical NoC routing is really a design-phase topic, not packaging. Got here via "thermal management" vocab leakage.

### #22 Pandey 2022 — NeuroMap (anchor, 14 cites)
- **DOI:** [10.1109/TCAD.2022.3197698](https://doi.org/10.1109/TCAD.2022.3197698)
- **Verdict:** ⚠ **FLAG — recommend excluding**
- **Actual method:** Application-aware task mapping + DVFS + DRAM low-power states. **Not ML-based** — the "deep learning" appears only because the *workload* being managed consists of DNNs.
- **Actual task:** Runtime DNN workload management on 3D-stacked HBM
- **Gist:** Exploits channel layout + temperature gradients in HBM to map DNN workloads with 39% execution time / 40% memory energy reduction.
- **Notes:** **Chips-for-AI disguised as AI-for-Chips.** The paper manages DNN execution on existing HBM; no ML is applied to the chip-design side. Consistent with the Du Z. 2015 / Zhan 2022 / Wang 2015 pattern already in `EXCLUDE_DOIS`.

### #23 Vaisband 2015 — power delivery clustering (exemplar, 11 cites)
- **DOI:** [10.1016/j.vlsi.2014.06.003](https://doi.org/10.1016/j.vlsi.2014.06.003)
- **Verdict:** ? no abstract (ScienceDirect holdout)
- **Actual method:** Adaptive clustering (classical ML, from title)
- **Actual task:** On-chip power delivery design
- **Gist:** *(abstract unavailable — VPN read required)*
- **Notes:** VLSI Journal holdout.

### #24 Zhao 2025 — PDNNet (recent, 3 cites)
- **DOI:** [10.1109/TCAD.2024.3509796](https://doi.org/10.1109/TCAD.2024.3509796)
- **Verdict:** ✓ confirmed (**with stage caveat**)
- **Actual method:** Heterogeneous dual-branch GNN+CNN over a novel PDNGraph (unified PDN topology + cell-current representation)
- **Actual task:** Dynamic IR drop prediction on power delivery network
- **Gist:** First GNN-based dynamic IR drop method; 545× faster than commercial tool, outperforms CNN-only baselines.
- **Notes:** **Stage boundary:** IR drop prediction is typically a design/sign-off concern, not packaging.

### #25 Chen 2026 — PINN for 2.5D chiplet PDN (newest, 0 cites)
- **DOI:** [10.1109/TVLSI.2025.3650633](https://doi.org/10.1109/TVLSI.2025.3650633)
- **Verdict:** ✓ confirmed
- **Actual method:** Physics-informed NN (PINN) with PDE residuals + workload encoding + step-load superposition
- **Actual task:** Runtime PDN modeling for 2.5D chiplet systems with resistive+inductive droop
- **Gist:** PINN embeds circuit constraints for 2.5D chiplet PDN analysis; 300× speedup over commercial solvers, sub-mV accuracy.
- **Notes:** Clean fit — 2.5D/chiplet/interposer focus is genuinely packaging.

---

## Transit (5)

### #26 Yasaei 2022 — GCN HT localization (anchor, 41 cites)
- **DOI:** [10.1109/TVLSI.2022.3191683](https://doi.org/10.1109/TVLSI.2022.3191683)
- **Verdict:** ✓ confirmed
- **Actual method:** Graph Convolutional Network with automatic node-feature extraction from circuit graphs
- **Actual task:** Hardware Trojan localization (pre-silicon, RTL/netlist level)
- **Gist:** GCN localizes HT signals directly in circuit graphs with no golden reference; 99.6% accuracy, 93.1% F1.
- **Notes:** Clean fit.

### #27 Yasaei 2025 — GNN HT detection (anchor, 35 cites)
- **DOI:** [10.1109/TCAD.2022.3178355](https://doi.org/10.1109/TCAD.2022.3178355)
- **Verdict:** ✓ confirmed (**companion paper to #26**)
- **Actual method:** GNN on Data Flow Graph representation
- **Actual task:** Hardware Trojan detection at RTL and gate-level netlist
- **Gist:** GNN on DFG detects unknown HTs with 97% recall at RTL (21ms) and 84% at gate level (13.4s).
- **Notes:** **Same first author as #26, closely related line of work.** Could swap for an alternative-author HT paper if you want more authorial diversity in the shortlist.

### #28 Stern 2020 — EMFORCED (exemplar, 28 cites)
- **DOI:** [10.1109/TVLSI.2019.2949733](https://doi.org/10.1109/TVLSI.2019.2949733)
- **Verdict:** ✓ confirmed
- **Actual method:** Non-invasive EM side-channel acquisition from clock-distribution network + PCA (unsupervised) + LDA (supervised)
- **Actual task:** Counterfeit IC detection (remarked and cloned, no decapsulation)
- **Gist:** EM-side-channel clock-network fingerprints classify authentic vs. counterfeit ICs: 99.46% (PCA) / 100% (LDA) across ICs from multiple vendors/dates/lot codes + gray market.
- **Notes:** **Exemplifies the digital-thread hypothesis** — this is AI reconstructing provenance that a functional thread would have recorded.

### #29 Chen 2025 — GNN4HT (recent, 12 cites)
- **DOI:** [10.1109/TCAD.2024.3428469](https://doi.org/10.1109/TCAD.2024.3428469)
- **Verdict:** ✓ confirmed
- **Actual method:** Two-stage GNN (stage 1: localize; stage 2: classify HT *function*) + logical-equivalence data augmentation
- **Actual task:** HT detection + **function** classification (what the trojan does)
- **Gist:** First two-stage GNN that goes beyond binary HT detection to classify HT function (80.95% gate-level, 62.96% RTL).
- **Notes:** Good complement to Yasaei papers — adds the "what does the trojan do" angle.

### #30 Ghimire 2026 — AI image processing counterfeit (newest, 0 cites)
- **DOI:** [10.1016/j.vlsi.2025.102628](https://doi.org/10.1016/j.vlsi.2025.102628)
- **Verdict:** ? no abstract (ScienceDirect holdout)
- **Actual method:** Classical ML + image processing (from title)
- **Actual task:** Counterfeit IC clustering/identification
- **Gist:** *(abstract unavailable — VPN read required)*
- **Notes:** VLSI Journal holdout.

---

## In-Field (10)

### #31 Mao 2022 — ML BGA drop response (anchor, 30 cites)
- **DOI:** [10.1016/j.microrel.2022.114553](https://doi.org/10.1016/j.microrel.2022.114553)
- **Verdict:** ? no abstract (ScienceDirect holdout)
- **Actual method:** Classical ML (from title)
- **Actual task:** BGA board-level drop response (mechanical shock modeling)
- **Gist:** *(abstract unavailable — VPN read required)*
- **Notes:** Microelectronics Reliability holdout. **Inherently transit-adjacent** — drop damage is a shipping/handling concern.

### #32 Kao 2023 — DL wire-bonding positioning fault (anchor, 27 cites)
- **DOI:** [10.1109/TSM.2023.3243775](https://doi.org/10.1109/TSM.2023.3243775)
- **Verdict:** ✓ confirmed (**but stage-misplaced**)
- **Actual method:** Ensemble DNN + CNN on time-domain statistics + CWT + FFT features of linear-encoder signals; high-pass filter preprocessing
- **Actual task:** Wire-bonding positioning-error fault diagnosis (bond-head installation) — PHM for assembly equipment
- **Gist:** DNN+CNN ensemble detects inappropriate wire-bonder bond-head installation from linear-encoder signals for predictive maintenance.
- **Notes:** **Stage misplacement — this is IC assembly / packaging, not in-field operation.** Classified here via "fault diagnosis" vocab.

### #33 Rahmani 2017 — ML trace-signal selection (anchor, 26 cites)
- **DOI:** [10.1109/TVLSI.2016.2593902](https://doi.org/10.1109/TVLSI.2016.2593902)
- **Verdict:** ✓ confirmed
- **Actual method:** ML framework trained on *bounded mock simulations* + compound search-space exploration
- **Actual task:** Post-silicon trace signal selection (debug)
- **Gist:** ML trained on few simulation runs replaces expensive full simulation in trace-signal selection; up to 143% restorability improvement.
- **Notes:** Clean fit.

### #34 Elnaggar 2019 — Changepoint HT detection (exemplar, 25 cites)
- **DOI:** [10.1109/TVLSI.2019.2925807](https://doi.org/10.1109/TVLSI.2019.2925807)
- **Verdict:** ✓ confirmed
- **Actual method:** Changepoint-based anomaly detection on performance-counter data streams
- **Actual task:** Run-time HT detection (post-deployment, no on-chip sensor modification)
- **Gist:** Changepoint anomaly detection on perf counters catches HT activation at runtime; >99% TPR on OpenSPARC T1 FPGA prototype.
- **Notes:** **Actually correctly placed in in-field** (vs. pre-silicon HT work in transit) — complements Yasaei's pre-silicon HT papers nicely. Good pairing for the digital-thread narrative: HT detection happens in multiple phases.

### #35 Ma 2023 — ML-attack-resistant PUF (exemplar, 21 cites)
- **DOI:** [10.1016/j.mejo.2023.105977](https://doi.org/10.1016/j.mejo.2023.105977)
- **Verdict:** ? no abstract (ScienceDirect holdout; title suggests similar borderline status as #40 — AI appears only as attacker)
- **Actual method:** Classical ML (from title)
- **Actual task:** PUF design resistant to ML modeling attacks
- **Gist:** *(abstract unavailable — VPN read required)*
- **Notes:** Microelectronics Journal holdout. Worth reading the abstract to decide whether to flag for exclusion alongside Bahador #40.

### #36 Gai 2022 — Flexible hotspot detection (exemplar, 18 cites)
- **DOI:** [10.1109/TCAD.2021.3135786](https://doi.org/10.1109/TCAD.2021.3135786)
- **Verdict:** ✓ confirmed (**but stage-misplaced**)
- **Actual method:** Fully Convolutional Network (FCN) + transfer learning scheme for new technology nodes
- **Actual task:** Layout hotspot detection (lithography DFM)
- **Gist:** FCN detects multiple hotspots in layouts of any size; transfer scheme reduces sample requirements when moving to a new technology node.
- **Notes:** **Stage misplacement — hotspot detection is classically fabrication/DFM, not in-field.** Classified here via "reliability enhancement" vocab.

### #37 de Jong 2025 — PI-LSTM solder fatigue (recent, 8 cites)
- **DOI:** [10.1016/j.microrel.2025.115797](https://doi.org/10.1016/j.microrel.2025.115797)
- **Verdict:** ✓ confirmed
- **Actual method:** Physics-informed LSTM with flow rule embedded in the loss; trained on FEM-simulation data
- **Actual task:** Solder-joint fatigue / plastic strain prediction under thermal cycling
- **Gist:** PI-LSTM predicts solder plastic strain + cycles-to-failure at FEM-matching accuracy for power-electronics reliability.
- **Notes:** Stage defensible (reliability under thermal cycling). Transit-adjacent for the digital-thread narrative.

### #38 Saravanan 2023 — Quantum reliability GNN (recent, 12 cites)
- **DOI:** [10.1109/TCAD.2022.3202430](https://doi.org/10.1109/TCAD.2022.3202430)
- **Verdict:** ✓ confirmed (**domain-specific: quantum chips**)
- **Actual method:** GNN (over traditional ML baselines) capturing quantum-circuit structure + gate features
- **Actual task:** NISQ quantum-circuit output-fidelity prediction + single-qubit gate rescheduling
- **Gist:** GNN-based fidelity prediction on IBM Q Guadalupe; drives gate rescheduling without prior calibration circuits.
- **Notes:** **Domain: quantum NISQ, not conventional CMOS.** Keep it but flag the domain distinction in the paper's breadth discussion.

### #39 Wu 2026 — NBTI/HCD PINN-LSTM (newest, 0 cites)
- **DOI:** [10.1016/j.microrel.2025.115996](https://doi.org/10.1016/j.microrel.2025.115996)
- **Verdict:** ✓ confirmed
- **Actual method:** PINN-LSTM with reaction-diffusion (NBTI) + energy-driven (HCD) physical models; 2D voltage-plane weight factor
- **Actual task:** Coupled NBTI/HCD aging failure modeling → ring-oscillator and LNA degradation prediction
- **Gist:** Physics-informed NN-LSTM on 2D voltage plane models coupled NBTI/HCD aging; 11.92% avg error vs. experiments, 8.6% RO frequency error.
- **Notes:** Clean fit for in-field (aging).

### #40 Bahador 2026 — Reconfigurable MRAM PUF (newest, 0 cites)
- **DOI:** [10.1109/TCAD.2026.3667088](https://doi.org/10.1109/TCAD.2026.3667088)
- **Verdict:** ⚠ **FLAG — recommend excluding**
- **Actual method:** PUF *circuit design* (7nm FinFET MRAM/MTJ array + novel level converter + writing scheme). **The ML — LR, SVM, MLP, CNN, DNN, RL — appears only as the attacker in the security evaluation.**
- **Actual task:** Strong PUF architecture for IoT authentication
- **Gist:** Reconfigurable MRAM-based PUF resists ML modeling attacks across 1M challenge-response pairs; 34.7 μm² at 7.78 fJ/bit.
- **Notes:** **Not AI-for-Chips** — the paper's method is circuit design; ML is used only to empirically test security. Consistent with why Du Z., Wang J., Zhan J. are in `EXCLUDE_DOIS`. **Likely candidate for the same list.**

---

## Recommended follow-up actions

1. **Add to `EXCLUDE_DOIS`:**
   - `10.1109/tcad.2022.3197698` — Pandey 2022 NeuroMap (chips-for-AI, algorithmic workload management)
   - `10.1109/tcad.2026.3667088` — Bahador 2026 MRAM PUF (AI appears only as attacker)
2. **Read abstracts via VPN before finalizing:**
   - Ma X. 2023 — likely another "ML-as-attacker, chip-design-as-defense" pattern; candidate for exclusion by analogy with Bahador
   - Vaisband 2015, Mao 2022, Huang 2023, Ghimire 2026 — confirm they're genuine AI-for-Chips
3. **Optional stage rehoming** (not affecting inclusion, but useful for narrative clarity):
   - Lee 2026 → Design; Zhang W. 2021 / Zhao 2025 → Design; Kao 2023 → Packaging; Gai 2022 → Fabrication
4. **Minor tag corrections** are cosmetic — won't change the shortlist selection, only the reported method labels. Skip unless you want a cleaner pivot table.
