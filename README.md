# FrameXplore

**Automated disulfide bond correction for cysteine‑rich protein structures predicted by ColabFold**

[DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20132827.svg)](https://doi.org/10.5281/zenodo.20132827)
https://github.com/Vidhusv/FRAMEXPLORER

**FrameXplore** is a Google Colab notebook that extends [ColabFold](https://github.com/sokrypton/ColabFold) to automatically **identify and correct disulfide bonds** in protein structures. It is built for toxin researchers, structural biologists, and anyone working with cysteine‑rich peptides (conotoxins, ICK motifs, defensins, etc.).

---

## What FrameXplore does

AlphaFold2 and ColabFold often predict **incorrect disulfide connectivity** in cysteine‑rich proteins, sometimes even giving the wrong fold. FrameXplore fixes this by:

1. Running the full **ColabFold v1.6.1** prediction pipeline.
2. Automatically extracting all cysteine residues from the best model.
3. Computing pairwise **Cα–Cα** and **S–S distance** matrices.
4. Identifying **true disulfide bonds** with strict geometric cutoffs (Cα–Cα < 6.5 Å, S–S < 2.5 Å).
5. Writing a **corrected PDB** with proper `CONECT` records.
6. Providing an **interactive 3D view** with cysteines shown as sticks and disulfide bonds as orange dashed lines.

No extra steps needed – just `Runtime` → `Run all`.

---

## Quick start

1. Open the notebook in Colab (click the **Open in Colab** badge above).
2. Paste your cysteine‑rich protein sequence.
3. Click `Runtime` → `Run all`.
4. FrameXplore will automatically correct the disulfide bonds and display the corrected structure.

---

## Example test case

Try the built‑in example: **α‑Conotoxin GI** from *Conus geographus*  

"MGMRMMFTVFLLVVLATTVVSFPSERASDGRDDTAKDEGSDMDKLVEKKECCNPACGRHYSCGR"

Expected output: two disulfide bonds (C2–C7 and C3–C12), correctly identified and visualised.

---

## How disulfide identification works

| Criterion  | Cutoff |
|------------|--------|
| Cα–Cα distance | < 6.5 Å |
| S–S distance | < 2.5 Å |

These geometric thresholds are derived from known disulfide bond geometries in the PDB and work across all cysteine‑rich scaffolds (ICK, Kunitz, EGF, etc.).

---

## Repository contents

- `FrameXplore.ipynb` – the main executable notebook.
- `CITATION.cff` – machine‑readable citation metadata.
- `LICENSE` – MIT license.
- `.gitignore` – ignores temporary and output files.

---

## Citing FrameXplore

If you use FrameXplore in your research, please cite:

Vijay, V. S. (2026). FrameXplore: Automated disulfide bond correction for cysteine-rich protein structures (v1.0.0). Zenodo. https://doi.org/10.5281/zenodo.20132827


Also cite the underlying ColabFold:
Mirdita, M. et al. ColabFold: making protein folding accessible to all. Nature Methods, 2022. https://doi.org/10.1038/s41592-022-01488-1


---

## License

FrameXplore is released under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## Acknowledgements

FrameXplore is built on **ColabFold** (Copyright (c) 2021 Sergey Ovchinnikov, MIT License).  
AlphaFold2 parameters are made available under CC BY‑NC 4.0 by DeepMind.

---

*Created by [Vidhu S Vijay](https://github.com/Vidhusv)*
