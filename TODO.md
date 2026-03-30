# StableESM Paper — TODO

## Placeholder Values to Fill In

- [ ] **SH3 domain AUC scores** (`main.tex` ~line 190): `$AUC$ = XXX` for StableESM and ESM2
- [ ] **Dataset statistics** (`main.tex` ~line 136): median domain length, avg preference pairs per domain
- [ ] **Disorder F1 scores** (`main.tex` ~line 300): mean F1 for StableESM, ESM2, ESM_Therm, one-hot at 650M; % domains improved
- [ ] **Solubility AUROC** (`main.tex` ~line 306): AUROC for StableESM-650M vs ESM2-650M
- [ ] **Extended Figure X** references (`main.tex` ~lines 136, 157): assign actual figure numbers

## Sections to Write

- [ ] **Discussion** (`main.tex` ~line 356) — empty
- [ ] **Code and Data Availability** (`main.tex`) — empty
- [ ] **Acknowledgments** (`main.tex`) — empty
- [ ] **Author Contributions** (`main.tex`) — empty
- [ ] **Competing Interests** (`main.tex`) — empty

## Sections Needing Revision

- [ ] **Enhanced classification of gain-of-stability mutations** (`main.tex` ~line 217) — marked `#TODO: needs revisions`
- [ ] **Experimental validation** (`main.tex` ~line 318) — update with round 2 single-mutation results when available; overlap mutants (both LLR > 0) are the key story

## Rosetta Benchmarking

- [ ] **Main text**: add Rosetta $\Delta\Delta G$ calculations as a physics-based baseline comparison (e.g., against StableESM LLR predictions on FireProt/MegaScale benchmarks)
- [ ] **Appendix methods** (`appendix.tex`): `\subsection{Predicting mutational effects with physics-based methods: Rosetta}` — currently empty, needs protocol details (Rosetta version, scoring function, relaxation protocol, cartesian_ddg vs row3 etc.)
- [ ] **Results**: compare Rosetta $\Delta\Delta G$ correlations vs StableESM LLR vs ESM2 LLR across OOD benchmarks; position StableESM relative to both ML and physics-based methods

## Figures to Create

- [ ] **Figure 4** (`figures/Figure_4.png`): experimental validation — MCO activity assays at 25/65/85°C, overlap vs StableESM-unique vs WT
- [ ] **Figure for disorder/solubility** (`figures/Figure_X_disorder_solubility.png`): (a) F1 scaling curves, (b) per-domain scatter, (c) solubility AUROC scaling
- [ ] **In silico design figure** (currently commented out as `Figure_5.png`): TempBERTura predictions, ColabFold structures
- [ ] Finalize extended/supplementary figure numbering

## Appendix Methods Still Empty

- [ ] `\subsection{Curating the Stable Mutate Preference Dataset}` — dataset curation details
- [ ] `\subsection{Implementing StableESM: LoRA-based DPO of ESM2}` — LoRA config, hyperparameters
- [ ] `\subsection{Training StableESM across model sizes using DPO}` — training details per scale
- [ ] `\subsection{Zero-shot mutation effect prediction using log-likelihood ratio}` — LLR scoring method
- [ ] `\subsection{Benchmarking StableESM on single mutations}` — evaluation protocol
- [ ] `\subsection{Benchmarking StableESM on double mutations}` — evaluation protocol
- [ ] `\subsection{Testing catastrophic forgetting on clinical variant prediction}` — clinical benchmark details (datasets, metrics, evaluation protocol)
- [ ] `\subsection{Predicting mutational effects with physics-based methods: Rosetta}` — Rosetta protocol

## Appendix Methods Already Written

- [x] `\subsection{Benchmarking StableESM on disorder region prediction}` — CAID benchmark, linear probe, solubility
- [x] `\subsection{Testing catastrophic forgetting on structure prediction}` — ESMFold structure module, CAMEO/CASP14-16
- [x] `\subsection{Testing catastrophic forgetting on ProteinGym benchmarks}` — LLR-based fitness, Spearman correlation
- [x] `\subsection{Designing multicopper oxidase alleles and variants with StableESM}` — ML-directed evolution, design strategies
- [x] `\subsection{Experimental protocol for protein purification}` — cloning, CFE, copper activation
- [x] `\subsection{Experimental protocol for activity assays}` — ABTS oxidation assay

## Main Text Sections Already Written

- [x] Introduction
- [x] Large-scale modeling of mutational preferences using pLMs and DPO
- [x] Training StableESM with DPO (~1M variants)
- [x] Generalization to unseen single mutants, homologs, and families
- [x] SH3 domain case study (needs XXX values filled in)
- [x] Transfer to higher-order mutational effects (double mutations)
- [x] Preference alignment unlocks scaling benefits
- [x] Enhanced classification of gain-of-stability mutations (needs revisions)
- [x] Catastrophic forgetting — structure prediction
- [x] Catastrophic forgetting — ProteinGym benchmarks (fitness, activity, binding, expression, stability)
- [x] Catastrophic forgetting — clinical variant prediction
- [x] Transfer to disorder region and solubility prediction (needs XXX values)
- [x] Designing thermostable MCO with StableESM (round 2 results pending)

## Fixes

- [ ] **Typo** (`main.tex` ~line 213): "prefrenece" → "preference"
- [ ] **Broken citation** (`main.tex` ~line 227): `\citep{lin2023evolutionary]` — square bracket instead of closing brace
- [ ] **Makefile** references `paper.tex` but main file is `main.tex`
- [ ] **Git committer name/email** — set via `git config`
