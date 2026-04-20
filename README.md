# Modelling Organic Molecule Survival on Mars: Finding the Goldilocks Preservation Depth

**Kahini Desai** | April 2026

## Overview

This project models the survival of glycine (the simplest amino acid) on the Martian surface under combined UV photolysis, ionizing radiation, and thermal degradation. Using real rover data from NASA's Curiosity and Perseverance missions, it identifies the optimal subsurface depth for organic molecule preservation — the **Goldilocks depth**.

## Key Findings

| Result | Value |
|--------|-------|
| Theoretical Goldilocks depth | 0.81 cm |
| Real Curiosity UV corrected | 1.01 cm |
| Sol-by-sol range (Gale) | 0.81 – 1.11 cm |
| Gale Crater mean | 1.04 cm |
| Jezero Crater mean | 1.01 cm |
| Minimum effective shielding (refined model) | 0.71 cm |
| UV vs radiation dominance | 63 million × |

## Data Sources

- **Curiosity REMS** — 2,242,660 UV measurements across 100 sols at Gale Crater (769,179 after cleaning)
- **Perseverance MEDA-RDS** — 2,550,808 measurements across 53 sols at Jezero Crater
- All data from the [NASA Planetary Data System](https://pds-atmospheres.nmsu.edu/)

## Repository Contents

| File | Description |
|------|-------------|
| `Goldilocks_Preservation_Depth.ipynb` | Complete Jupyter notebook with all code, analysis, and explanatory text |
| `Mars_Organic_Survival_Report.pdf` | Full scientific report (7 sections, 6 figures, sensitivity analysis) |
| `download1.png` – `download7.png` | Publication-quality figures |

## Methods

The model combines three degradation mechanisms:

- **UV photolysis**: k_UV = σ × F_UV, attenuated by Beer-Lambert law with depth
- **Ionizing radiation**: k_rad = α × dose_rate, from Curiosity RAD measurements
- **Thermal degradation**: Arrhenius equation k = A × exp(-Ea/RT)

The Goldilocks depth minimises k_total(z) = k_UV(z) + k_rad(z) + k_thermal(z).

## How to Run

1. Open `Goldilocks_Preservation_Depth.ipynb` in [Google Colab](https://colab.research.google.com/)
2. Run all cells sequentially — data downloads automatically from NASA PDS
3. Requires: `numpy`, `pandas`, `matplotlib`, `scipy`

## References

- Gomez-Elvira, J. et al. (2012). REMS: The Environmental Sensor Suite for the Mars Science Laboratory Rover. *Space Science Reviews*, 170(1–4), 583–640.
- Rodriguez-Manfredi, J.A. et al. (2021). The Mars Environmental Dynamics Analyzer, MEDA. *Space Science Reviews*, 217(3), 48.
- Hassler, D.M. et al. (2014). Mars' Surface Radiation Environment. *Science*, 343(6169).
- Stalport, F. et al. (2009). Investigating the Photostability of Carboxylic Acids Exposed to Mars Surface UV Radiation Conditions. *Astrobiology*, 9(6), 543–549.
- Cockell, C.S. and Raven, J.A. (2004). Zones of Photosynthetic Potential on Mars and the Early Earth. *Icarus*, 169(2), 300–310.
- Pavlov, A.A. et al. (2012). Degradation of Organic Molecules in the Shallow Subsurface of Mars. *Geophysical Research Letters*, 39, L13202.
