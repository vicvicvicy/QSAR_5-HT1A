# 5-HT1A QSAR Analysis

A Quantitative Structure-Activity Relationship (QSAR) project for predicting bioactivity of compounds against the 5-HT1A (serotonin 1a) receptor.

![5-HT1A receptor - Wikipedia](https://upload.wikimedia.org/wikipedia/commons/9/93/7e2y_putty_outline_and_ribbon.png)

## Overview

This project analyzes compounds from the ChEMBL database to build predictive models for 5-HT1A receptor binding activity (IC50 values).

## Background

The 5-HT1A receptor is a crucial therapeutic target in neuropharmacology due to its central role in serotonergic signaling and its involvement in numerous psychiatric and neurological conditions:

### Clinical Significance

- **Depression and Anxiety**: 5-HT1A receptors are primary targets for antidepressants and anxiolytics, including buspirone and newer SSRIs
- **Neurodegenerative Diseases**: Dysregulation of 5-HT1A signaling is implicated in Alzheimer's disease, Parkinson's disease, and other neurodegenerative disorders
- **Mood Disorders**: The receptor plays a key role in mood regulation, stress response, and emotional processing
- **Sleep Disorders**: 5-HT1A modulation affects sleep-wake cycles and circadian rhythms

### Drug Discovery Value

- **Validated Target**: Extensive clinical evidence supports 5-HT1A as an effective therapeutic target
- **Selectivity Challenges**: Understanding structure-activity relationships is crucial for developing selective compounds with fewer side effects
- **Polypharmacology**: Many successful CNS drugs interact with multiple serotonin receptor subtypes, making selectivity profiling essential

### QSAR Importance

QSAR modeling for 5-HT1A receptors enables:

- **Virtual Screening**: Rapid identification of promising drug candidates from large chemical libraries
- **Lead Optimization**: Rational design of compounds with improved potency and selectivity
- **ADMET Prediction**: Early assessment of drug-like properties to reduce late-stage failures
- **Mechanism Understanding**: Insights into molecular features driving receptor binding and activity

## Key Steps

- **Data Collection**: ChEMBL bioactivity data extraction for 5-HT1A receptor
- **Molecular Descriptors**: PaDEL descriptors and PubChem fingerprints
- **Data Processing**: Lipinski's Rule of Five filtering and pIC50 conversion
- **Visualization**: Distribution analysis and property correlations
- **Machine Learning**: QSAR model development for bioactivity prediction

## Dependencies

```bash
python -m pip install -U pandas numpy seaborn matplotlib scikit-learn lazypredict rdkit chembl_webresource_client
```

## Data

- **Source**: ChEMBL database bioactivity records for 5-HT1A receptor
- **Collection**: 664 compounds with IC50 binding affinity measurements
- **Analytics**: Molecular descriptor calculation (PaDEL), fingerprint generation (PubChem), Lipinski filtering, and pIC50 transformation for ML modeling

## Machine Learning

- **Approach**: Supervised regression modeling for bioactivity prediction
- **Features**: Molecular descriptors and chemical fingerprints as input variables
- **Target**: pIC50 values (negative log of IC50 concentrations)
- **Models**: Multiple algorithms evaluated using LazyPredict for rapid comparison and selection
- **Validation**: Cross-validation and performance metrics to assess model reliability

## Results & Chemical Features Analysis

- **Best Model**: Random Forest Regressor with R² performance metrics
- **Feature Selection**: Variance threshold filtering (>0.1) applied to reduce overfitting
- **Key Chemical Features**: Analysis of PubChem fingerprint bits revealed important structural patterns:
  - **N(:C)(:C)(:C)**: Nitrogen bonded to three aromatic carbons (bit 404)
  - **C(~C)(~C)(~H)(~N)**: Central carbon with mixed substituents (bit 338)
  - **Branched alkanes**: Seven-carbon chain structures (bit 697)
  - **O-C-C-C-C-N**: Linear oxygen-to-nitrogen chains (bit 682)
  - **O=C-N-C-N**: Carbonyl groups with nitrogen linkages (bit 647)
- **Insights**: Aromatic nitrogen systems and specific carbon chain patterns are critical for 5-HT1A binding affinity
