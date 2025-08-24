# 5-HT1A Receptor QSAR Analysis

A quantitative structure-activity relationship (QSAR) study for predicting the bioactivity of compounds against the serotonin 5-HT1A receptor using machine learning approaches.

## Overview

This project develops predictive models for 5-HT1A receptor binding affinity (IC50/pIC50 values) using molecular fingerprints and machine learning algorithms. The 5-HT1A receptor is a key target in neuropharmacology, particularly for antidepressants and anxiolytics.

## Dataset

- **Source**: ChEMBL database
- **Target**: Serotonin 1a (5-HT1a) receptor (CHEMBL214)
- **Compounds**: 663 bioactive molecules after Lipinski filtering
- **Activity**: IC50 binding affinity converted to pIC50 values
- **Features**: 881-bit PubChem molecular fingerprints

## Key Files

- `5-HT1A_qsar.ipynb` - Main analysis notebook
- `original_5HT1A_IC50_pIC50.csv` - Raw bioactivity data from ChEMBL (771 compounds)
- `processed_5HT1A_pIC50_Lipinski.csv` - Filtered dataset (663 compounds)
- `x_dataset_5HT1A.csv` - Feature matrix (PubChem fingerprints)
- `y_dataset_5HT1A.csv` - Target values (pIC50)
- `molecules.smi` - SMILES representations
- `*.pdf` - Visualization plots (molecular properties, distributions)

## Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
pip install rdkit lazypredict
pip install chembl_webresource_client
```

## Usage

1. **Data Collection**: Extract bioactivity data from ChEMBL for 5-HT1A receptor
2. **Preprocessing**: Apply Lipinski's rule of five for drug-likeness filtering
3. **Feature Generation**: Compute PubChem molecular fingerprints
4. **Model Training**: Build QSAR models using various ML algorithms
5. **Evaluation**: Assess model performance and interpretability

## Methodology

1. **Data Acquisition**: ChEMBL API to fetch 5-HT1A bioactivity data
2. **Data Cleaning**: Remove duplicates, standardize activity values
3. **Drug-likeness Filtering**: Apply Lipinski's rule of five
4. **Molecular Descriptors**: Generate PubChem fingerprints (881 bits)
5. **Machine Learning**: Multiple algorithms via LazyPredict
6. **Validation**: Cross-validation and performance metrics

## Results

The project includes visualizations for:
- Molecular weight and LogP distributions
- Hydrogen bond acceptor/donor profiles
- pIC50 activity distribution
- Feature importance analysis

## License

This project is for educational and research purposes.