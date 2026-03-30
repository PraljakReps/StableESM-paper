# StableESM Paper

LaTeX source for **"Aligning Protein Language Models with Large-Scale Mutant Preferences"**.

StableESM applies Direct Preference Optimization (DPO) to ESM2 protein language models using ~1M experimental stability mutations across ~1,000 protein domains from MegaScale, Human Domainome 1, and FireProtDB. The aligned models show improved zero-shot mutation effect prediction, generalization to unseen protein families, and no catastrophic forgetting on structure prediction or clinical variant tasks.

**Lab:** Ferguson Lab, University of Chicago

## Repository Structure

```
StableESM-paper/
├── main.tex                # Main manuscript
├── appendix.tex            # Supplementary materials / appendix
├── preamble.tex            # LaTeX preamble (shared macros & packages)
├── fairmeta.cls            # Document class
├── biblio.bib              # Bibliography (BibTeX)
├── main.bbl                # Compiled bibliography
├── figures/                # Paper figures (PDF/PNG)
├── assets/                 # Additional assets
├── Makefile                # Build automation
└── LICENSE
```

## Building the PDF

Requires a LaTeX distribution (e.g., [MacTeX](https://www.tug.org/mactex/) on macOS).

```bash
# Using latexmk (recommended)
latexmk -pdf main.tex

# Or manually
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex

# Clean auxiliary files
latexmk -C
```

## Related Resources

| Resource | Link |
|---|---|
| Code repository | [github.com/PraljakReps/StableESM](https://github.com/PraljakReps/StableESM) |
| Training details & DPO loss | `StableESM/source/METHODS.md` |
| Data | `StableESM/data/README.md` |
| Model checkpoints | `StableESM/checkpoints/README.md` |

## License

See [LICENSE](LICENSE) for details.
