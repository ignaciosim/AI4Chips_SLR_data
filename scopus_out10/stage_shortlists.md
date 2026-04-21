# Stage shortlists — AI for Chips (N=298, 2015–2026)

Surveys excluded: 4 (kw: survey/review/overview/tutorial/taxonomy). Manual false-positive exclusions: 19. Stage overrides applied: 6. Curated gists loaded: 55.
Roles: **Anchor** = top-cited; **Exemplar** = best paper in an otherwise-uncovered (method, task) pair; **Recent** = high cites/year from 2023+; **Newest** = 2026 papers surfaced regardless of citation count (too new to rank); **Curator** = editorial pick for topical importance where citation-based selection would miss it.
Stages with fewer than 10 papers are listed in full.

## Acronyms

| Acronym | Expansion |
|---|---|
| ACM TODAES | ACM Transactions on Design Automation of Electronic Systems |
| ADC | Analog-to-Digital Converter |
| ALD | Atomic Layer Deposition |
| ANN | Artificial Neural Network |
| ASIC | Application-Specific Integrated Circuit |
| BGA | Ball Grid Array |
| BLSA | Bitline Sense Amplifier |
| BO | Bayesian Optimization |
| CFET | Complementary Field-Effect Transistor (stacked n/p-FET) |
| CMOS | Complementary Metal-Oxide-Semiconductor |
| CMP | Chemical-Mechanical Planarisation |
| CNN | Convolutional Neural Network |
| CRP | Challenge-Response Pair (PUF evaluation metric) |
| CWT | Continuous Wavelet Transform |
| DAC | Digital-to-Analog Converter |
| DFM | Design for Manufacturing |
| DNN | Deep Neural Network |
| DPP | Digital Product Passport |
| DRAM | Dynamic Random-Access Memory |
| DRC | Design Rule Check |
| DSE | Design Space Exploration |
| DTCO | Design Technology Co-Optimization |
| EDA | Electronic Design Automation |
| EI | Expected Improvement (Bayesian optimization acquisition function) |
| EM | Electromagnetic (side channel) |
| EPE | Edge Placement Error |
| FBGA | Fine-pitch Ball Grid Array |
| FEM | Finite Element Method |
| FFT | Fast Fourier Transform |
| FinFET | Fin Field-Effect Transistor |
| FPR | False Positive Rate |
| GA | Genetic Algorithm |
| GaN | Gallium Nitride |
| GAN | Generative Adversarial Network |
| GCN | Graph Convolutional Network |
| GDSII | Graphic Data System Version II (chip layout format) |
| GNN | Graph Neural Network |
| HBM | High-Bandwidth Memory |
| HCD | Hot Carrier Degradation |
| HEMT | High-Electron-Mobility Transistor |
| HLS | High-Level Synthesis |
| HT | Hardware Trojan |
| IC | Integrated Circuit |
| ICCAD | IEEE/ACM International Conference on Computer-Aided Design (benchmarks from 2012, 2019) |
| ICICA | International Conference on Intelligent Computing Applications |
| ICSICT | International Conference on Solid-State and Integrated Circuit Technology |
| IEEE TCAD | IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems |
| IEEE TSM | IEEE Transactions on Semiconductor Manufacturing |
| IEEE TVLSI | IEEE Transactions on Very Large Scale Integration (VLSI) Systems |
| IGBT | Insulated-Gate Bipolar Transistor |
| ILP | Integer Linear Programming |
| ILT | Inverse Lithography Technique |
| INN | Invertible Neural Network |
| IR drop | Voltage drop across the power delivery network (I × R) |
| IRPS | IEEE International Reliability Physics Symposium |
| ISA | Instruction Set Architecture |
| KGE | Knowledge Graph Embedding |
| KNN | k-Nearest Neighbours |
| LCB | Lower Confidence Bound (Bayesian optimization acquisition function) |
| LDA | Linear Discriminant Analysis |
| LDO | Low-Dropout (voltage) regulator |
| LLM | Large Language Model |
| LNA | Low-Noise Amplifier |
| LSTM | Long Short-Term Memory |
| LVS | Layout vs. Schematic |
| M3D | Monolithic 3D integration |
| MATES | German Conference on Multiagent System Technologies |
| MC | Monte Carlo |
| MDP | Markov Decision Process |
| MIV | Monolithic Inter-tier Via |
| ML | Machine Learning |
| MLP | Multi-Layer Perceptron |
| MOO | Multi-Objective Optimization |
| MOSFET | Metal-Oxide-Semiconductor Field-Effect Transistor |
| MRAM | Magnetoresistive RAM |
| MTJ | Magnetic Tunnel Junction |
| NAND | NAND flash memory |
| NBTI | Negative Bias Temperature Instability |
| NISQ | Noisy Intermediate-Scale Quantum (computing era) |
| NoC | Network-on-Chip |
| OPC | Optical Proximity Correction |
| OTA | Operational Transconductance Amplifier |
| PCA | Principal Component Analysis |
| PDN | Power Delivery Network |
| PHM | Prognostics and Health Management |
| PI | Probability of Improvement (Bayesian optimization acquisition function) |
| PICMET | Portland International Conference on Management of Engineering and Technology |
| PI-LSTM | Physics-Informed Long Short-Term Memory |
| PINN | Physics-Informed Neural Network |
| PnR | Place and Route |
| PUF | Physical Unclonable Function |
| PVT | Process, Voltage, Temperature (variations) |
| QMC | Quasi-Monte Carlo |
| RAG | Retrieval-Augmented Generation |
| RISC-V | open-source Reduced Instruction Set Computer v-ISA |
| RL | Reinforcement Learning |
| RNN | Recurrent Neural Network |
| RO | Ring Oscillator (used as a process/voltage/temperature-sensitive sensor for side-channel analysis and aging monitoring) |
| RSMT | Rectilinear Steiner Minimum Tree |
| RTL | Register-Transfer Level |
| SAC | Soft Actor-Critic |
| SDC | Silent Data Corruption |
| SMT | Satisfiability Modulo Theories |
| SoC | System-on-Chip |
| STCO | System Technology Co-Optimization |
| SVM | Support Vector Machine |
| TAT | Turnaround Time |
| TPR | True Positive Rate |
| Trust-HUB / TRIT-TC | Community hardware-trojan benchmark suites |
| TSV | Through-Silicon Via |
| UCIe | Universal Chiplet Interconnect Express |
| UQ | Uncertainty Quantification |
| VCO | Voltage-Controlled Oscillator |
| VLSI | Very Large-Scale Integration |
| WM-811K | Wafer Map dataset (811,457 wafer maps) |
| WSC | Winter Simulation Conference |

## Design (n=154)

The largest and most methodologically diverse stage (154 papers). Analog sizing is the most citation-dense subfield — op-amp / OTA / LC-VCO sizing using ANN surrogates (Li 2020, Budak 2022), Bayesian optimization (Zhang 2022), and reinforcement learning (Settaluri 2022, AnaCraft 2026). The 2024–2026 wave is defined by LLMs operating at different levels: RTL generation (VeriGen), tool orchestration (ChatEDA), analog layout (LayoutCopilot), analog topology (Atelier). On the digital side, the recurring theme is physical-design automation — DREAMPlace for placement, GoodFloorplan for floorplanning, IronMan-Pro for HLS. DTCO/STCO — a major industry push — appears only as Cheng 2021's SMT-based CFET cell synthesis, suggesting the academic ML community has not yet caught up to this direction.

| Role | Year | 1st author | Method | Task | Cites | Title | Gist | DOI |
|---|---|---|---|---|---|---|---|---|
| Anchor | 2024 | Thakur S. | llm_foundation_models | logic_synthesis | 141 | VeriGen: A Large Language Model for Verilog Code Generation | Fine-tunes open-source CodeGen-16B on GitHub+textbook Verilog; outperforms GPT-3.5-turbo by 1.1% with 41% improvement in syntactic correctness over base model. Open-source release. | [10.1145/3643681](https://doi.org/10.1145/3643681) |
| Anchor | 2020 | Li Y. | deep_learning | design_space_exploration | 127 | An Artificial Neural Network Assisted Optimization System for Analog D… | Parallel GA with ANN-based local minimum search replaces SPICE calls, ~4× speedup over traditional GA+SPICE. | [10.1109/TCAD.2019.2961322](https://doi.org/10.1109/TCAD.2019.2961322) |
| Anchor | 2024 | Wu H. | llm_foundation_models | logic_synthesis | 116 | ChatEDA: A Large Language Model Powered Autonomous Agent for EDA | LLM agent translates natural-language requirements into task decomposition + tool scripts; AutoMage beats GPT-4 on EDA orchestration. | [10.1109/TCAD.2024.3383347](https://doi.org/10.1109/TCAD.2024.3383347) |
| Anchor | 2022 | Zhang S. | bayesian_probabilistic | analog_circuit_design | 114 | An Efficient Batch-Constrained Bayesian Optimization Approach for Anal… | Ensemble acquisition across PI/EI/LCB with Pareto sampling enables 15–74× speedup over DE/WEIBO at batch size 15. | [10.1109/TCAD.2021.3054811](https://doi.org/10.1109/TCAD.2021.3054811) |
| Anchor | 2021 | Lin Y. | deep_learning | placement | 107 | DREAMPlace: Deep Learning Toolkit-Enabled GPU Acceleration for Modern… | Classical analytical placement recast as NN training in PyTorch, 40× GPU speedup over RePlAce without quality loss. | [10.1109/TCAD.2020.3003843](https://doi.org/10.1109/TCAD.2020.3003843) |
| Exemplar | 2022 | Budak A.F. | classical_ml | analog_circuit_design | 106 | An Efficient Analog Circuit Sizing Method Based on Machine Learning As… | Addresses ML-cost / error-accumulation failure modes that other ML-assisted sizers hide by testing on reduced spec sets. | [10.1109/TCAD.2021.3081405](https://doi.org/10.1109/TCAD.2021.3081405) |
| Exemplar | 2022 | Settaluri K. | reinforcement_learning | analog_circuit_design | 60 | Automated Design of Analog Circuits Using Reinforcement Learning | RL framework for analog/mixed-signal circuit sizing deployed on a 16nm FinFET TIA and folded-cascode; averages 4 parasitic sims, 38× more efficient than prior work, LVS-passing post-layout. | [10.1109/TCAD.2021.3120547](https://doi.org/10.1109/TCAD.2021.3120547) |
| Exemplar | 2022 | Zhou R. | evolutionary_optimization | analog_circuit_design | 60 | An Analog Circuit Design and Optimization System With Rule-Guided Gene… | Genetic algorithm with design-rule-guided mutation injects domain knowledge into mutation step; 1.5–3.3× speedup over traditional GA on op-amps and LC-VCO. | [10.1109/TCAD.2022.3166637](https://doi.org/10.1109/TCAD.2022.3166637) |
| Exemplar | 2023 | Wu N. | deep_learning; graph_neural_networks; reinforcement_learning | logic_synthesis | 51 | IronMan-Pro: Multiobjective Design Space Exploration in HLS via Reinfo… | Three-component ML stack reduces HLS prediction errors 10.9× (resources) / 5.7× (CP timing) and finds Pareto solutions with 400× meta-heuristic speedup. Open source. | [10.1109/TCAD.2022.3185540](https://doi.org/10.1109/TCAD.2022.3185540) |
| Exemplar | 2022 | Xu Q. | general_ml_signals; graph_neural_networks; reinforcement_learning | placement | 48 | GoodFloorplan: Graph Convolutional Network and Reinforcement Learning-… | Formulates floorplanning as an MDP; GCN + RL end-to-end framework outperforms heuristic floorplanners on area and wirelength. | [10.1109/TCAD.2021.3131550](https://doi.org/10.1109/TCAD.2021.3131550) |
| Exemplar | 2021 | Cheng C.K. | symbolic_reasoning | design_space_exploration | 44 | Complementary-FET (CFET) Standard Cell Synthesis Framework for Design… | SMT-based joint place-and-route for Complementary-FET (stacked nFET/pFET) standard cells; 3.5T CFET cells give 21% block-level area reduction over 4.5T conventional via DTCO/STCO exploration. | [10.1109/TVLSI.2021.3065639](https://doi.org/10.1109/TVLSI.2021.3065639) |
| Recent | 2025 | Liu B. | llm_foundation_models | analog_circuit_design | 22 | LayoutCopilot: An LLM-Powered Multiagent Collaborative Framework for I… | LLM multi-agent lowers EDA-tool learning curve by translating design intent into executable layout scripts. | [10.1109/TCAD.2025.3529805](https://doi.org/10.1109/TCAD.2025.3529805) |
| Recent | 2023 | Wei J. | deep_learning | calibration | 43 | A New Compact MOSFET Model Based on Artificial Neural Network With Uni… | ANN-based compact MOSFET model for analog simulation in 0.18µm; Latin-hypercube training outperforms BSIM4 fitting on amplifier/LDO dc convergence. | [10.1109/TCAD.2022.3193330](https://doi.org/10.1109/TCAD.2022.3193330) |
| Newest | 2026 | Ahmadzadeh M. | reinforcement_learning | analog_circuit_design | 5 | AnaCraft: Duel-Play Probabilistic-Model-Based Reinforcement Learning f… | First adversarial multi-agent RL for PVT-robust analog sizing; 3× fewer simulations and 2× runtime reduction vs. SOTA. | [10.1109/TCAD.2025.3582175](https://doi.org/10.1109/TCAD.2025.3582175) |
| Newest | 2026 | Shen J. | llm_foundation_models | analog_circuit_design | 4 | Atelier: An Automated Analog Circuit Design Framework via Multiple Lar… | Multi-agent LLM with graph-of-thoughts and compact KB avoids costly domain fine-tuning while specializing each agent for a design sub-task. | [10.1109/TCAD.2025.3573228](https://doi.org/10.1109/TCAD.2025.3573228) |

## Fabrication (n=71)

Fabrication clusters around two task families: mask / lithography optimization and wafer-level defect analytics. Computational lithography shows a clean methodological progression — GAN-OPC 2020 established learning-for-OPC, followed by Neural-ILT 2.0's end-to-end mask network, DevelSet's transformer + CUDA optimizer, and INN-ILT 2026's physics-embedded invertible network. Wafer-map and yield work is dominated by classical ML and early deep learning (Chiu's Mask R-CNN on WM-811K, Jang's DL yield predictor, Ciccazzo's SVM surrogate). Zhang J.'s 2026 work on mitigating errors in LLM-generated RTL straddles Design and Fabrication, hinting at an emerging cross-stage application of LLM debugging.

| Role | Year | 1st author | Method | Task | Cites | Title | Gist | DOI |
|---|---|---|---|---|---|---|---|---|
| Anchor | 2020 | Yang H. | generative_adversarial | lithography_optimization | 90 | GAN-OPC: Mask Optimization with Lithography-Guided Generative Adversar… | ILT-pretrained GAN with U-Net generator produces quasi-optimal masks that need fewer conventional OPC iterations. | [10.1109/TCAD.2019.2939329](https://doi.org/10.1109/TCAD.2019.2939329) |
| Anchor | 2021 | Chiu M.C. | deep_learning | wafer_map_analysis | 59 | Applying Data Augmentation and Mask R-CNN-Based Instance Segmentation… | Mask R-CNN with 1,056 training items (COCO-pretrained) handles mixed-type wafer defects on WM-811K at 97.7% single-type accuracy. | [10.1109/TSM.2021.3118922](https://doi.org/10.1109/TSM.2021.3118922) |
| Anchor | 2021 | Cheng K.C.C. | classical_ml; general_ml_signals | verification | 55 | Machine Learning-Based Detection Method for Wafer Test Induced Defects | Analyzes probing-order patterns to classify which bad dies are retrieval candidates vs. real fab defects, 97% across 6 real products. | [10.1109/TSM.2021.3065405](https://doi.org/10.1109/TSM.2021.3065405) |
| Exemplar | 2022 | Jiang B. | deep_learning | lithography_optimization | 39 | Neural-ILT 2.0: Migrating ILT to Domain-Specific and Multitask-Enabled… | Single NN for mask prediction + ILT correction, 15–30× TAT speedup over SOTA with better mask complexity. | [10.1109/TCAD.2021.3109556](https://doi.org/10.1109/TCAD.2021.3109556) |
| Exemplar | 2019 | Jang S.J. | classical_ml | yield_prediction | 36 | A wafer map yield prediction based on machine learning for productivit… | DL predicts yield from wafer-map design at pre-production stage, guiding 8.59% higher-productivity wafer-map designs. | [10.1109/TSM.2019.2945482](https://doi.org/10.1109/TSM.2019.2945482) |
| Exemplar | 2016 | Ciccazzo A. | bayesian_probabilistic; classical_ml | yield_prediction | 35 | A SVM surrogate model-based method for parametric yield optimization | SVM surrogate replaces SPICE calls in MC yield optimization; benchmarked against STMicro's industrial reference. | [10.1109/TCAD.2015.2501307](https://doi.org/10.1109/TCAD.2015.2501307) |
| Recent | 2023 | Huang L. | classical_ml | defect_detection | 29 | Linear regression combined KNN algorithm to identify latent defects fo… | Linear regression extracts latent-defect features; KNN classifier distinguishes latent defects from benign process variation in manufacturing test. 32% accuracy improvement over other ML methods on early-life-failure screening by handling class imbalance in the data. | [10.1016/j.mejo.2022.105641](https://doi.org/10.1016/j.mejo.2022.105641) |
| Recent | 2023 | Chen G. | deep_learning | lithography_optimization | 23 | DevelSet: Deep Neural Level Set for Instant Mask Optimization | Level-set representation + transformer NN + CUDA kernels delivers ~1s mask optimization with SOTA printability. | [10.1109/TCAD.2023.3286262](https://doi.org/10.1109/TCAD.2023.3286262) |
| Newest | 2026 | Zhu B. | deep_learning | lithography_optimization | 0 | INN-ILT: Inverse Lithography Technique via Invertible Neural Network | Physics-embedded INN unifies forward lithography + inverse mask optimization in a single invertible network. | [10.1109/TCAD.2025.3650094](https://doi.org/10.1109/TCAD.2025.3650094) |
| Newest | 2026 | Zhang J. | llm_foundation_models | logic_synthesis | 0 | Understanding and Mitigating Errors of LLM-Generated RTL Code | Categorizes failure modes of LLM-generated RTL code and fixes them with domain RAG, description rule-checking, and an iterative sim-debug loop; 98.1% on VerilogEval with Deepseek-v3.2. | [10.1109/TCAD.2026.3661446](https://doi.org/10.1109/TCAD.2026.3661446) |
| Curator | 2025 | Seo J. | classical_ml | process_optimization | 4 | Deriving optimal atomic layer deposition process conditions using mach… | MLP + Gaussian process regression surrogate predicts partial pressure (an indicator of thin-film uniformity) for atomic layer deposition; RMSE 0.0074 and ~18× faster than CFD simulations. Introduces variance- and difference-based uniformity metrics to close the loop from prediction to optimal process conditions under pattern-loading effects in high-aspect-ratio advanced-node structures. (Only AI-for-ALD paper in the corpus — included as a Curator pick for topical whitespace.) | [10.1016/j.jii.2025.100879](https://doi.org/10.1016/j.jii.2025.100879) |

## Packaging (n=11)

A small stage (12 papers after curation) centred on 3D-IC physical design and advanced packaging workflows. Anchors span wire-bonding PHM (Kao 2023, DNN+CNN ensemble on linear-encoder signals), on-chip power-delivery clustering (Vaisband 2015), and thermal-aware 3D-IC test scheduling (Chatterjee 2022). A clear 3D-IC optimization thread runs through the shortlist: Dewan 2023's RSMT routing database for monolithic 3D integration, Vanna-Iampikul 2023's GNN flip-flop clustering for 3D clock networks, and Wu 2023's ILP substrate router for FBGA packaging. Chen 2026's physics-informed NN surrogate for 2.5D chiplet PDNs is the stage's newest entry. Two shortlisted papers (Dewan, Wu) use symbolic / combinatorial optimization rather than learning-based methods — the ontology tags them as AI via its symbolic-reasoning category; a stricter ML-only framing would demote them.

| Role | Year | 1st author | Method | Task | Cites | Title | Gist | DOI |
|---|---|---|---|---|---|---|---|---|
| Anchor | 2023 | Kao S.X. | deep_learning; general_ml_signals | fault_diagnosis | 27 | Deep Learning-Based Positioning Error Fault Diagnosis of Wire Bonding… | DNN+CNN ensemble detects inappropriate wire-bonder bond-head installation from linear-encoder signals for predictive maintenance. | [10.1109/TSM.2023.3243775](https://doi.org/10.1109/TSM.2023.3243775) |
| Anchor | 2015 | Vaisband I. | classical_ml | power_analysis | 11 | Energy efficient adaptive clustering of on-chip power delivery systems | Recursive polynomial-time clustering algorithm for co-designing heterogeneous on-chip power delivery systems (power-converter placement and regulator configuration); up to 21% power efficiency improvement on IBM power-grid benchmarks with orders-of-magnitude runtime speedup. (Symbolic/algorithmic — no learned ML model, despite classical_ml tag.) | [10.1016/j.vlsi.2014.06.003](https://doi.org/10.1016/j.vlsi.2014.06.003) |
| Anchor | 2022 | Chatterjee S. | classical_ml | test_generation | 7 | Frequency-scaled thermal-aware test scheduling for 3D ICs using machin… | ML-based predictive thermal model for 3D ICs embedded in a frequency-scaled thermal-aware test scheduling algorithm; up to 60% test-time reduction on benchmark circuits by scaling test clock frequency within thermal constraints. | [10.1016/j.mejo.2022.105535](https://doi.org/10.1016/j.mejo.2022.105535) |
| Exemplar | 2023 | Dewan M.I. | symbolic_reasoning | routing | 6 | Construction of All Multilayer Monolithic RSMTs and Its Application to… | Constructs all multilayer monolithic rectilinear Steiner minimum trees on the 3D Hanan grid, yielding a routing-topology database that accelerates MIV insertion for M3D-integrated ICs. (Symbolic / algorithmic, not learning-based.) | [10.1145/3626958](https://doi.org/10.1145/3626958) |
| Exemplar | 2020 | Pittino F. | classical_ml; general_ml_signals | thermal_management | 5 | Robust Identification of Thermal Models for In-Production High-Perform… | Combines classical ML and deep learning to select workload traces suitable for thermal-model identification on in-production HPC systems; DL is necessary for correct trace selection up to 96% of the time, achieving sub-1°C compact-model accuracy. | [10.1109/TCAD.2019.2950378](https://doi.org/10.1109/TCAD.2019.2950378) |
| Exemplar | 2023 | Vanna-Iampikul P. | classical_ml; graph_neural_networks | design_space_exploration | 5 | GNN-based Multi-bit Flip-flop Clustering and Post-clustering Design Op… | Unsupervised GNN-based flip-flop clustering merges single-bit FFs into multi-bit FFs, jointly optimizing 3D IC clock-network power and performance; integrated with a SOTA 3D flow, 18% total-power and 8.2% performance improvement. | [10.1145/3588570](https://doi.org/10.1145/3588570) |
| Recent | 2025 | Yan H. | graph_neural_networks | hotspot_detection | 3 | A Lightweight Heterogeneous Graph Embedding Framework for Hotspot Dete… | Lightweight 3-hop GNN over a modified transitive-closure graph representation of layouts; uses dynamic edge transforms for augmentation, beats image-based hotspot detectors on ICCAD 2012/2019. | [10.1109/TCAD.2025.3543436](https://doi.org/10.1109/TCAD.2025.3543436) |
| Recent | 2023 | Wu J.S. | symbolic_reasoning | routing | 3 | ILP-based Substrate Routing with Mismatched Via Dimension Consideratio… | ILP-based router for fine-pitch BGA wire-bonding package substrate design, handling design-dependent constraints and via-dimension mismatches; 278× solver speedup from ILP constraint reduction. (Symbolic / algorithmic, not learning-based.) | [10.1145/3579843](https://doi.org/10.1145/3579843) |
| Newest | 2026 | Chen X. | deep_learning | power_analysis | 0 | A Physics-Informed Neural Network Surrogate for Runtime PDN and Dynami… | PINN embeds circuit constraints for 2.5D chiplet PDN analysis; 300× speedup over commercial solvers, sub-mV accuracy. | [10.1109/TVLSI.2025.3650633](https://doi.org/10.1109/TVLSI.2025.3650633) |

## Transit (n=13)

Transit is almost entirely security-focused — every shortlisted paper targets hardware-trojan detection or counterfeit-IC identification. Yasaei's two GNN papers (2022, 2025) define golden-reference-free HT detection; Popryho 2025 (NetVGE, knowledge-graph embedding) and Utyamishev 2024 push the scalability frontier with novel graph convolutions at 17k-gate scale. Chen's GNN4HT adds function classification — not just whether a trojan is present but what it does. Stern's EMFORCED uses EM side-channel fingerprints plus PCA/LDA to detect counterfeits without decapsulation, and Narwariya 2025 closes a related gap with zero-area-overhead age prediction from IO-pad protection diodes for recycled-IC detection. Both Stern and Narwariya are textbook cases of AI reconstructing provenance that a continuous digital thread would have recorded directly. Notably absent: any ML work on environmental or mechanical transit telemetry (shock, temperature, humidity), a clear whitespace in the literature.

| Role | Year | 1st author | Method | Task | Cites | Title | Gist | DOI |
|---|---|---|---|---|---|---|---|---|
| Anchor | 2022 | Yasaei R. | graph_neural_networks | security_analysis | 41 | Golden Reference-Free Hardware Trojan Localization Using Graph Convolu… | GCN localizes HT signals directly in circuit graphs with no golden reference; 99.6% accuracy, 93.1% F1. | [10.1109/TVLSI.2022.3191683](https://doi.org/10.1109/TVLSI.2022.3191683) |
| Anchor | 2025 | Yasaei R. | deep_learning; graph_neural_networks | security_analysis | 35 | Hardware Trojan Detection Using Graph Neural Networks | GNN on DFG detects unknown HTs with 97% recall at RTL (21ms) and 84% at gate level (13.4s). | [10.1109/TCAD.2022.3178355](https://doi.org/10.1109/TCAD.2022.3178355) |
| Anchor | 2020 | Stern A. | classical_ml | security_analysis | 28 | EMFORCED: EM-Based Fingerprinting Framework for Remarked and Cloned Co… | EM-side-channel clock-network fingerprints classify authentic vs. counterfeit ICs: 99.46% (PCA) / 100% (LDA) across ICs from multiple vendors/dates/lot codes + gray market. | [10.1109/TVLSI.2019.2949733](https://doi.org/10.1109/TVLSI.2019.2949733) |
| Exemplar | 2025 | Popryho Y. | graph_neural_networks | logic_synthesis | 3 | NetVGE: Netwise Hardware Trojan Detection at RTL Using Variable Depend… | RT-level HT detection via weighted variable dependency graphs embedded with knowledge-graph embedding (KGE) + HittER scoring in the latent space; 93% recall / 98% precision on Trust-HUB RTL, unsupervised and reference-free. | [10.1109/TCAD.2025.3569492](https://doi.org/10.1109/TCAD.2025.3569492) |
| Exemplar | 2025 | Narwariya A.S. | llm_foundation_models | reliability_analysis | 1 | Leveraging IO Pad Protection Diodes for Recycled IC Detection and Age… | Detects counterfeit recycled ICs and estimates chip age from voltage drop across existing IO-pad protection diodes, fit with polynomial regression; sensorless and zero-area-overhead, usable on deployed chips. | [10.1109/TVLSI.2025.3590317](https://doi.org/10.1109/TVLSI.2025.3590317) |
| Recent | 2025 | Chen L. | graph_neural_networks | security_analysis | 12 | GNN4HT: A Two-Stage GNN-Based Approach for Hardware Trojan Multifuncti… | First two-stage GNN that goes beyond binary HT detection to classify HT function (80.95% gate-level, 62.96% RTL). | [10.1109/TCAD.2024.3428469](https://doi.org/10.1109/TCAD.2024.3428469) |
| Recent | 2024 | Utyamishev D. | graph_neural_networks | security_analysis | 6 | Netwise Detection of Hardware Trojans Using Scalable Convolution of Gr… | Scalable netwise gate-level HT detection using a novel graph-convolution algorithm tailored to IC graphs; 96% recall / 86% precision on TrustHub TRIT-TC at 17k-gate scale, highlighting compromised nets in <0.1 s. | [10.1109/TCAD.2024.3383348](https://doi.org/10.1109/TCAD.2024.3383348) |
| Newest | 2026 | Ghimire A. | classical_ml | security_analysis | 0 | AI-enabled image processing approach for efficient clustering and iden… | Ring-oscillator side-channel data rendered as images; unsupervised image clustering detects hardware-trojan insertion at 95% accuracy with no golden-reference IC required. | [10.1016/j.vlsi.2025.102628](https://doi.org/10.1016/j.vlsi.2025.102628) |

## In-Field (n=49)

The most task-diverse stage — covering aging and reliability prediction, post-silicon validation, runtime security, and quantum-circuit fidelity. Mao 2022's ML for BGA board-level drop response anchors by citation but is physically transit-adjacent. Physics-informed ML is the emerging methodological theme: de Jong 2025's PI-LSTM for solder fatigue and Wu 2026's PINN-LSTM for NBTI/HCD coupled aging. Rahmani 2017 (post-silicon trace-signal selection) and Bathla 2023 (Bayesian reliability of combinational circuits) cover validation workflows. Elnaggar 2019's runtime HT detection via changepoint anomaly analysis on performance counters complements the pre-silicon HT work in Transit — a full-lifecycle HT story emerges when the two are paired. Saravanan 2023's GNN for NISQ quantum-circuit reliability is a domain outlier but shows the ML-for-reliability template generalizing beyond CMOS.

| Role | Year | 1st author | Method | Task | Cites | Title | Gist | DOI |
|---|---|---|---|---|---|---|---|---|
| Anchor | 2022 | Mao M. | classical_ml | reliability_analysis | 30 | Machine learning for board-level drop response of BGA packaging struct… | Back-propagation DNN replaces finite-element simulation for 3D board-level drop-response prediction on BGA solder joints; 3+ orders of magnitude faster than FE, Pearson >0.95 for stress/strain/warpage prediction. Handles surface, line, and point contact drop types and generalizes to drop angles outside the training distribution. | [10.1016/j.microrel.2022.114553](https://doi.org/10.1016/j.microrel.2022.114553) |
| Anchor | 2017 | Rahmani K. | classical_ml | verification | 26 | Postsilicon Trace Signal Selection Using Machine Learning Techniques | ML trained on few simulation runs replaces expensive full simulation in trace-signal selection; up to 143% restorability improvement. | [10.1109/TVLSI.2016.2593902](https://doi.org/10.1109/TVLSI.2016.2593902) |
| Anchor | 2019 | Elnaggar R. | anomaly_detection | security_analysis | 25 | Hardware Trojan Detection Using Changepoint-Based Anomaly Detection Te… | Changepoint anomaly detection on perf counters catches HT activation at runtime; >99% TPR on OpenSPARC T1 FPGA prototype. | [10.1109/TVLSI.2019.2925807](https://doi.org/10.1109/TVLSI.2019.2925807) |
| Exemplar | 2023 | Saravanan V. | deep_learning; general_ml_signals; graph_neural_networks | reliability_analysis | 12 | Data-Driven Reliability Models of Quantum Circuit: From Traditional ML… | GNN-based fidelity prediction on IBM Q Guadalupe; drives gate rescheduling without prior calibration circuits. | [10.1109/TCAD.2022.3202430](https://doi.org/10.1109/TCAD.2022.3202430) |
| Exemplar | 2023 | Bathla S. | bayesian_probabilistic | reliability_analysis | 10 | A Framework for Reliability Analysis of Combinational Circuits Using A… | Bayesian inference on a four-valued (correct/incorrect) signal representation replaces the XOR-gate dual-circuit model for output error-rate estimation; sum-product belief propagation gives consistent scaling with gate error probabilities. | [10.1109/TVLSI.2023.3237885](https://doi.org/10.1109/TVLSI.2023.3237885) |
| Exemplar | 2023 | Hou T. | deep_learning | reliability_analysis | 10 | A Deep Learning Framework for Solving Stress-based Partial Differentia… | Physics-informed neural network for solving stress-based PDEs that govern electromigration in VLSI interconnect trees; mesh-free solutions via automatic differentiation handle varying atom diffusivity per segment during the void nucleation phase, with accuracy comparable to traditional EM solvers at lower computational cost. | [10.1145/3567424](https://doi.org/10.1145/3567424) |
| Recent | 2025 | de Jong S.D.M. | classical_ml | reliability_analysis | 8 | Solder joint reliability predictions using physics-informed machine le… | PI-LSTM predicts solder plastic strain + cycles-to-failure at FEM-matching accuracy for power-electronics reliability. | [10.1016/j.microrel.2025.115797](https://doi.org/10.1016/j.microrel.2025.115797) |
| Recent | 2023 | Dong X. | deep_learning | power_analysis | 9 | Worst-case Power Integrity Prediction Using Convolutional Neural Netwo… | CNN-based framework for worst-case power integrity prediction on power delivery networks; reduces spatial and temporal redundancy in the PDN and input-current vectors, then uses a custom CNN architecture. 25-69× speedup over commercial tools at 0.6-1.0% relative error for dynamic-noise prediction, 24-64× at 0.2-1.1% for bump-current prediction. (Stage-imprecise in In-Field: PDN sign-off is typically a design-phase task.) | [10.1145/3564932](https://doi.org/10.1145/3564932) |
| Newest | 2026 | Wu Z. | deep_learning | fault_diagnosis | 0 | Neural network approach to NBTI/HCD coupled failure analysis of MOS IC… | Physics-informed NN-LSTM on 2D voltage plane models coupled NBTI/HCD aging; 11.92% avg error vs. experiments, 8.6% RO frequency error. | [10.1016/j.microrel.2025.115996](https://doi.org/10.1016/j.microrel.2025.115996) |
| Newest | 2026 | Benmahdjoub M.A. | deep_learning | thermal_management | 0 | Hybrid junction temperature prediction of IGBTs combining detailed ele… | Physics-informed ML (Random Forest, Feedforward NN with SCG and Adam, RNN) for IGBT junction-temperature prediction trained on Hefner electro-thermal model simulation data; RNN achieves RMSE <0.5 K, R² ≈ 0.9. (IGBT = power semiconductor, not CMOS IC; in scope under a broad AI-for-semiconductor definition.) | [10.1016/j.mejo.2026.107133](https://doi.org/10.1016/j.mejo.2026.107133) |
