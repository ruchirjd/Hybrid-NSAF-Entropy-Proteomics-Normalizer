# Hybrid NSAF-Entropy Proteomics Normalizer

## Overview
This Python script implements a sophisticated hybrid normalization approach for label-free quantitative proteomics data. It combines Normalized Spectral Abundance Factor (NSAF) with Shannon entropy-based sample complexity adjustment to provide robust protein abundance normalization.

## Features
- NSAF normalization accounting for protein length
- Shannon entropy-based sample complexity adjustment
- Support for multiple replicates
- Comprehensive quality control metrics
- Detailed output statistics and normalization factors

## Requirements
- Python 3.x
- pandas
- numpy
- scipy

## Installation
1. Clone this repository or download the script
2. Install required packages:
```bash
pip install pandas numpy scipy
```

## Input File Requirements
The input CSV file must contain:
- Columns starting with 'Spec' containing spectral count data
- A 'Length' column containing protein lengths
- Additional columns with protein metadata (optional)

Example input file format:
```
Protein_ID,Length,SpecCount1,SpecCount2,SpecCount3,...
protein1,450,10,12,11,...
protein2,300,5,6,4,...
```

## Usage
1. Run the script:
```bash
python Hybrid_approach_labelFreequant_Proteomics.py
```
2. When prompted, enter the path to your input CSV file
3. The script will generate a new file with the suffix '_hybrid_normalized.csv'

## Output
The output file includes:
1. Original columns from input file
2. NSAF values (*_NSAF)
3. Hybrid normalized values (*_hybrid_normalized)
4. Average hybrid normalized value
5. Coefficient of Variation across replicates (if multiple replicates present)
6. Sample entropy values (*_entropy)
7. Sample complexity weights (*_complexity_weight)

## Method Details
### NSAF Normalization
NSAF normalizes spectral counts by protein length and total sample abundance:
- SpC/L = Spectral counts / Protein length
- NSAF = (SpC/L) / Σ(SpC/L)

### Entropy-based Adjustment
The Shannon entropy calculation provides sample complexity adjustment:
- Entropy calculated for each sample using NSAF values
- Complexity weights derived from entropy values
- Final values adjusted using complexity weights

## Quality Control
- Shannon entropy for each sample
- Sample complexity weights
- Coefficient of variation across replicates (when applicable)

## Troubleshooting
Common issues:
- Missing 'Length' column: Ensure your input file has a column named 'Length'
- No 'Spec' columns: Verify spectral count columns start with 'Spec'
- File format issues: Confirm CSV format and column names

## Citation
If you use this tool in your research, please cite:
[Citation information to be added]

## License
[License information to be added]

## Contact
[Contact information to be added]
