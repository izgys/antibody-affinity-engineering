# Antibody Affinity Engineering with AI + Structure-Based Modeling

**Author:** Iker Zapirain Gysling  
**Project Type:** Computational Antibody Design + AI + Structural Bioinformatics  
**Status:** 🚧 In Progress  

---

## Project Overview

This project explores the use of **AI-based protein design** tools and **structure-based scoring** to improve the binding affinity of an antibody to its antigen. We focus on the **CDR (complementarity-determining regions)**, especially **CDR-H3**, where mutations are generated using **ProteinMPNN** and/or **ESM-IF1**, and the resulting mutants are structurally modeled and scored for **binding affinity** and **developability**.

The workflow is designed to showcase a realistic, portfolio-ready approach to **antibody engineering**, combining generative AI, structure prediction, and molecular evaluation.

---

## Objectives

- Model a known **SARS-CoV-2 antibody-antigen complex** structure
- Extract and analyze **VH/VL domains** and **CDR regions**
- Generate sequence variants using **ProteinMPNN** or **ESM-IF1**
- Predict 3D structures of mutant antibodies using **IgFold** or **AlphaFold-Multimer**
- Estimate changes in **binding affinity (ΔΔG)** using tools like **FoldX**
- Evaluate **developability metrics**: hydrophobicity, aggregation risk, charge, etc.
- Visualize and compare mutations at the antibody-antigen interface

---

## Tools and Technologies

| Tool/Library              | Purpose                                               |
|---------------------------|-------------------------------------------------------|
| **ProteinMPNN / ESM-IF1** | AI-based mutation generation / inverse folding        |
| **IgFold / AlphaFold-Multimer** | Structure prediction for antibody variants     |
| **FoldX / EvoEF2**        | Binding affinity estimation (ΔΔG)                     |
| **TAP / Biopython**       | Developability metric computation                     |
| **PyMOL / matplotlib**    | Visualization of interfaces and results               |
| **SAbDab / AB-Bind**      | Data sources for antibody structures and benchmarks   |

---

## Antibody Target

- **Antibody-Antigen Complex:** SARS-CoV-2 spike RBD bound to a neutralizing antibody
- **Example PDB ID:** [7BZ5](https://www.rcsb.org/structure/7BZ5)
- **Why this target?** The SARS-CoV-2 spike protein is a highly studied and therapeutically relevant antigen, and 7BZ5 provides a high-resolution complex suitable for modeling and benchmarking AI-driven antibody optimization workflows.


---

## Workflow Summary

```mermaid
graph TD
    A[Start: SARS-CoV-2 Antibody-Antigen Complex 7BZ5] --> B[Extract VH/VL + CDR Regions]
    B --> C[Generate Mutations with ProteinMPNN / ESM-IF1]
    C --> D[Predict 3D Structures of Mutants]
    D --> E[Score Binding Affinity (ΔΔG) with FoldX]
    E --> F[Assess Developability Metrics]
    F --> G[Rank and Select Best Variants]
    G --> H[Visualize Mutations and Interface Contacts]
```

---

## Repository Structure

```
antibody-affinity-engineering/
│
├── README.md                      ← This file
├── data/
│   ├── input_pdb/                 ← Raw antibody-antigen complex (e.g., 7BZ5)
│   └── sequences/                 ← Extracted VH/VL sequences and CDRs
├── modeling/
│   ├── run_igfold.py              ← Structure prediction for mutants
│   └── predicted_structures/
├── mutation_design/
│   ├── mpnn_input/                ← Input files for ProteinMPNN/ESM-IF1
│   └── mpnn_output/               ← Generated sequences
├── scoring/
│   ├── foldx/                     ← ΔΔG calculation scripts and outputs
│   └── developability/            ← TAP and biophysical evaluations
├── notebooks/
│   └── analysis.ipynb             ← Visual summaries and benchmarking
├── visualization/
│   ├── pymol_sessions/            ← Visual comparison of interfaces
│   └── plots/                     ← Affinity scores, contact maps, etc.
└── results/
    ├── top_variants.csv           ← Final ranked variants
    └── summary_report.md
```

---

## Key Analyses

- **Binding ΔΔG Predictions**: Estimate changes in binding free energy due to CDR mutations using tools like FoldX or EvoEF2.
- **CDR Loop Interaction Mapping**: Analyze how mutations affect key paratope-epitope contacts at the antibody-antigen interface.
- **Developability Filters**: Screen mutants based on properties like isoelectric point, aggregation propensity, and hydrophobicity.
- **Visualization**: Compare wild-type and mutant structures using PyMOL; generate heatmaps and structural overlays to interpret binding changes.


---

## Future Improvements

- Integrate **RosettaDock** or **DeepAbDock** for improved antibody-antigen docking refinement  
- Extend pipeline to include **multiple antibody-antigen pairs** to generalize and benchmark  
- Explore **fine-tuning CDR-specific generative models** for loop design  
- Build an interactive **Streamlit or Dash interface** to explore top-ranked variants  

---

## Learning Outcomes

- Apply state-of-the-art **AI tools** (ProteinMPNN, ESM-IF1) for rational antibody design  
- Perform **structure-based evaluation** of binding affinity changes (ΔΔG)  
- Use antibody-specific numbering and modeling tools for **VH/VL/CDR analysis**  
- Integrate antibody developability considerations into your design pipeline  
- Build a clean, modular, and portfolio-ready computational antibody design workflow  

---

## Example Visuals (To Be Added)

- [ ] ΔΔG vs Mutation Position plots  
- [ ] Wild-type vs mutant interface visualizations  
- [ ] Heatmaps of binding affinity changes  
- [ ] Developability radar plots (e.g., charge, solubility, aggregation risk)  

---

## License and Citation

This project is for academic and portfolio purposes.  

---
