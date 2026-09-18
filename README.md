**Mechanistic ODE Modeling, RACIPE Ensemble Analysis & Transcriptomic Validation**
--

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen.svg)]()
[![Research](https://img.shields.io/badge/Research-Computational%20Biology-purple.svg)]()
[![DOI](https://img.shields.io/badge/DOI-10.21203%2Frs.3.rs--10196893%2Fv1-blue.svg)](https://doi.org/10.21203/rs.3.rs-10196893/v1)

An integrated framework combining mechanistic ODE modeling, RACIPE ensemble analysis, and transcriptomic validation to map the phenotypic landscape of Epithelial-to-Mesenchymal Transition (EMT).

---
**Year:** 2023  
**License:** MIT  
**Author:** Sepideh Moafi

License: MIT
---
## 📖 Overview

This project integrates three complementary approaches to study EMT:

- **Mechanistic ODE modeling** (9-state Tian model)
- **RACIPE ensemble analysis** (10,000 randomized kinetic models)
- **Transcriptomic validation** (GSE69667 real data)

---

## 📊 Key Results

| Metric | Value |
|--------|-------|
| ODE Model Residual | 1.98 × 10⁻¹⁶ |
| RACIPE Models | 10,000 |
| Randomized Parameters | 510,000 |
| Epithelial States | 21.3% |
| Hybrid States | 38.5% |
| Mesenchymal States | 40.2% |
| EMT Score Range | 0.013 – 1.000 |
| Replicate Concordance | Pearson r = 0.9977 (p < 0.001) |
| Top Correlates | E-cadherin (r = −0.767), N-cadherin (r = +0.584) |

---

## 📁 Project Structure

```

RACIPE-EMT-Project/
├── README.md
├── requirements.txt
├── LICENSE
├── CITATION.cff
├── .gitignore
├── src/
│   ├── emt_model/
│   └── racipe/
├── data/
│   ├── raw/
│   └── processed/
├── figures/
├── notebooks/
└── manuscript/

```

---

## 🚀 Getting Started

### Installation

```bash
git clone https://github.com/AIResearcher20/RACIPE-EMT-Project.git
cd RACIPE-EMT-Project
pip install -r requirements.txt
```

Run the Analysis

Google Colab:

1. Open notebooks/RACIPE_EMT_Final_Analysis.ipynb
2. Upload the required CSV files
3. Runtime → Run all

Local Python:

```python
from src.emt_model import simulate_baseline
from src.racipe import run_racipe_batch

result = simulate_baseline()
print(f"Steady state residual: {result['residual']:.2e}")

results = run_racipe_batch(n_param_sets=10000, n_ic=100)
print(f"States: E={results['epithelial']:.1f}%, H={results['hybrid']:.1f}%, M={results['mesenchymal']:.1f}%")
```

---

📈 Figures

· Figure 1 — Replicate Concordance: figures/figure_analysis20_replicate_validation.png
· Figure 2 — RACIPE Phenotypic Landscape: figures/figure_state_distribution_final.png
· Figure 3 — Transcriptomic Comparison: figures/racipe_vs_real_comparison.png
· Figure 4 — Real Trajectory in RACIPE Space: figures/figure_real_trajectory_in_racipe_space.png

---

🔬 Methods Summary

Mechanistic ODE Model (Tian et al., 2013)

· 9 state variables: T, s, S, R₃, z, Z, R₂, E, N
· 43 intrinsic parameters
· Numerical residual: 1.98 × 10⁻¹⁶

RACIPE Ensemble

· 9 nodes, 11 regulatory edges
· 51 parameters per model
· 10,000 models × 100 initial conditions

Transcriptomic Validation

· Dataset: GSE69667 (A549 + TGF-β)
· 8 time points: 0–96 h
· 2 biological replicates
· Replicate concordance: Pearson r = 0.9977

---

📦 Dependencies

```
numpy>=1.21.0
pandas>=1.3.0
scipy>=1.7.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
```

---

📚 Citation

If you use this work in research, please cite:

```bibtex
@article{Moafi2023decoding,
  title={Decoding EMT Heterogeneity: An Integrative Framework Combining ODE Dynamics, RACIPE Ensembles, and Transcriptomic Validation},
  author={Moafi, Sepideh},
  year={2023},
  note={Manuscript in preparation}
}
```

---

📜 License

MIT License — see LICENSE for details.

---

🙏 Acknowledgments

· NCBI Gene Expression Omnibus for the GSE69667 dataset
· RACIPE developers (Huang et al., 2017, 2018)
· Tian EMT model authors (Tian et al., 2013)

---

👩🔬 Contact

Sepideh Moafi 
Independent Researcher
vaniakarimi20@gmail.com
github.com/AIResearcher20

```

---

