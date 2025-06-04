# Hybrid method of node split algorithm

## Overview
This document outlines the version requirements and dependencies for the `nodesplit-hybrid` project. This research project implements hybrid node-splitting algorithms for citation network analysis, combining bibliographic coupling (BC), co-citation (CC), and direct citation (DC) methods for community detection in academic citation networks.

## Project Description
The project analyzes citation networks from the Microsoft Academic Graph (MAG) dataset using various node-splitting techniques:
- **BC (Bibliographic Coupling)**: Papers that cite similar references
- **CC (Co-citation)**: Papers that are cited together 
- **DC (Direct Citation)**: Direct citation relationships
- **Hybrid approaches**: Combinations of BC, CC, and DC methods

## Dependencies

### Python Environment
**Required Version**: Python 3.9+ (notebooks tested with Python 3.12.9)

### Essential Scientific Computing Stack
```python
# Core computation and data manipulation
pandas>=1.3.0                 # Data manipulation and analysis
numpy>=1.21.0                 # Numerical computing

# Graph analysis and network science
igraph-python>=0.9.0          # Fast graph processing (igraph)
leidenalg>=0.8.0              # Leiden clustering algorithm

# Clustering evaluation
clusim>=0.3.0                 # Clustering similarity metrics (NMI calculation)

# Visualization
matplotlib>=3.4.0            # Plotting and visualization

# Progress tracking and parallel processing
tqdm>=4.62.0                 # Progress bars (tqdm.notebook for Jupyter)

# Jupyter environment
jupyter>=1.0.0               # Notebook environment
ipykernel>=6.0.0             # IPython kernel

```

## Data Requirements

### Microsoft Academic Graph (MAG) Dataset
The project processes large-scale citation data from MAG:
- **Papers.txt**: Paper metadata
- **PaperReferences.txt**: Citation relationships  
- **FieldsOfStudy.txt**: Academic field classifications
- **PaperFieldsOfStudy.txt**: Paper-field associations

We used MAG Dump of Oct 3, 2019 in this study.

### Expected Data Structure
```
MAG_dataset/
├── mag/
│   ├── Papers.txt
│   └── PaperReferences.txt
└── advanced/
    ├── FieldsOfStudy.txt
    └── PaperFieldsOfStudy.txt
```

## Comments on the notebook files

1. `00_Preprocess_*.ipynb` - Data preprocessing
2. `01_HybridBC-CC-DC*.ipynb` - Main hybrid clustering algorithms
3. `02_NMI_TEST.ipynb` - Clustering evaluation
4. `03_Preprocess_GetCitationCounts.ipynb` - Citation analysis
5. `04_NMI_TEST_BY_METADATA*.ipynb` - Metadata-based analysis
6. `05_DC*.ipynb` - Direct citation analysis
7. `Figure*.ipynb` - Result visualization


## Output Files

The project generates various output files:
- `./Processed_data/*.tsv` - Processed MAG data
- `./Cluster_out/*.clu` - Clustering results
- `./MAG_L2_Similarity/*.tsv` - NMI evaluation results
- `./SubmissionFigures/` - Submission-ready figures

## Version Compatibility
**Tested Configurations:**
- Python 3.12.9 with conda environment
- pandas 1.5+, numpy 1.21+, matplotlib 3.4+
- igraph 0.10+, leidenalg 0.8+, clusim 0.3+
- Jupyter Lab/Notebook environment
