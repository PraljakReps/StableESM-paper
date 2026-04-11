# StableESM Paper — TODO

## Placeholder Values to Fill In

- [ ] **SH3 domain AUC scores** (`main.tex` ~line 190): `$AUC$ = XXX` for StableESM and ESM2
- [ ] **Dataset statistics** (`main.tex` ~line 136): median domain length, avg preference pairs per domain
- [ ] **Disorder F1 scores** (`main.tex` ~line 300): mean F1 for StableESM, ESM2, ESM_Therm, one-hot at 650M; % domains improved
- [ ] **Solubility AUROC** (`main.tex` ~line 306): AUROC for StableESM-650M vs ESM2-650M
- [ ] **Extended Figure X** references (`main.tex` ~lines 136, 157): assign actual figure numbers

## Sections to Write

- [ ] **Discussion** (`main.tex`) — draft written, needs review: check tone, verify all claims match results, ensure limitations are fair
- [ ] **Code and Data Availability** (`main.tex`) — draft written, needs review: verify Google Drive links work, confirm repo is public before submission
- [ ] **Acknowledgments** (`main.tex`) — still empty, needs: funding/grant numbers, compute resources (cluster name), any non-author contributors to thank
- [ ] **Author Contributions** (`main.tex`) — still empty, needs author list finalized and CRediT-style contributions
- [ ] **Competing Interests** (`main.tex`) — draft written ("no competing interests"), double-check with all authors before submission

## Sections Needing Revision

- [ ] **Enhanced classification of gain-of-stability mutations** (`main.tex` ~line 217) — marked `#TODO: needs revisions`
- [ ] **Experimental validation** (`main.tex` ~line 318) — update with round 2 single-mutation results when available; overlap mutants (both LLR > 0) are the key story

## Rosetta Benchmarking

- [ ] **Main text**: add Rosetta $\Delta\Delta G$ calculations as a physics-based baseline comparison (e.g., against StableESM LLR predictions on FireProt/MegaScale benchmarks)
- [ ] **Appendix methods** (`appendix.tex` ~line 308, `\subsection{Rosetta Relaxation and Cartesian $\Delta\Delta G$ Calculations}`, `\label{sec:rosetta_methods}`) — subsection already exists and documents FastRelax + `ref2015_cart` + `cartesian_ddg` protocol, **but does not describe how WT structures are acquired**. Extend it to cover:
  - **WT structure sourcing**: when a deposited PDB matches the experimental construct exactly, relax the PDB directly; when the PDB is unavailable **or the deposited crystal construct differs from the UniProt canonical sequence** (see `PraljakReps/StableESM` issue #1 — e.g., Q9UV68 / 3WP4 has 7 residues that differ from UniProt), build the "experimental construct" sequence by patching UniProt with the PDB SEQRES variants and predict its structure with ColabFold.
  - **ColabFold protocol**: AlphaFold2 weights via ColabFold, **template mode enabled** (homologous crystal passed as custom template so the prediction is anchored to the experimentally characterized fold — e.g., 3WP4 for Q9UV68), **full MSA via MMseqs2** (ColabFold default, not single-sequence), top-ranked model relaxed with **Amber** before it enters the Rosetta FastRelax step.
  - **Rationale**: LLR is masked-marginal and so is invariant to the WT-label mismatch, but Rosetta $\Delta\Delta G = G(\text{mut}) - G(\text{wt})$ is not — the construct-aware WT structure is required for physically meaningful ΔΔG.
  - **Scope note**: applied across the entire FireProt long-sequence OOD holdout ($254 < L \leq 1022$), not only the proteins flagged by the consistency sweep.
- [ ] **Results**: compare Rosetta $\Delta\Delta G$ correlations vs StableESM LLR vs ESM2 LLR across OOD benchmarks; position StableESM relative to both ML and physics-based methods. Include a note that LLR and Rosetta report complementary quantities (LLR ↔ masked log-likelihood, Rosetta ↔ folding free energy) and neither directly measures $\Delta T_m$.

## Figures to Create

- [ ] **Figure 4** (`figures/Figure_4.png`): experimental validation — MCO activity assays at 25/65/85°C, overlap vs StableESM-unique vs WT
- [ ] **Figure for disorder/solubility** (`figures/Figure_X_disorder_solubility.png`): (a) F1 scaling curves, (b) per-domain scatter, (c) solubility AUROC scaling
- [ ] **In silico design figure** (currently commented out as `Figure_5.png`): TempBERTura predictions, ColabFold structures
- [ ] Finalize extended/supplementary figure numbering

## Appendix Methods Still Empty

- _(none — the Rosetta subsection exists at `appendix.tex:308` as `\subsection{Rosetta Relaxation and Cartesian $\Delta\Delta G$ Calculations}`; pending edits are tracked under "Rosetta Benchmarking" above.)_

## Appendix Methods Complete

- [x] `\subsection{Curating the Stable Mutant Preference Dataset}` — dataset curation details
- [x] `\subsection{Implementing StableESM: LoRA-based DPO of ESM2}` — LoRA config, DPO loss, masking
- [x] `\subsection{Training StableESM across model sizes using DPO}` — hyperparameter table, optimizer, infrastructure
- [x] `\subsection{Zero-shot mutation effect prediction using log-likelihood ratio}` — LLR scoring, multi-site, reference normalization
- [x] `\subsection{Benchmarking StableESM on single mutations}` — 4-tier evaluation protocol
- [x] `\subsection{Benchmarking StableESM on double mutations}` — MegaScale double mutants, simultaneous masking
- [x] `\subsection{Benchmarking StableESM on disorder region and solubility prediction}` — linear probing framework, CAID benchmark, solubility classification
- [x] `\subsection{Testing catastrophic forgetting on structure prediction}` — ESMFold structure module, CAMEO/CASP14-16
- [x] `\subsection{Testing catastrophic forgetting on clinical variant prediction}` — ProteinGym clinical benchmark, ClinVar variants, AUC/F1
- [x] `\subsection{Testing catastrophic forgetting on ProteinGym benchmarks}` — LLR-based fitness, 5 functional categories, Spearman correlation
- [x] `\subsection{Designing multicopper oxidase alleles and variants with StableESM}` — ML-directed evolution, design strategies
- [x] `\subsection{Experimental protocol for protein purification}` — cloning, CFE, copper activation
- [x] `\subsection{Experimental protocol for activity assays}` — ABTS oxidation assay

## Main Text Sections Already Written

- [x] Introduction
- [x] Large-scale modeling of mutational preferences using pLMs and DPO (includes DPO equation tcolorbox)
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
