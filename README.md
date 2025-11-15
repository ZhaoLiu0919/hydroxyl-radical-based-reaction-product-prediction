# Hydroxyl Radical Based Reaction Product Prediction

[![Python](https://img.shields.io/badge/Python-3.7%2B-blue)](https://www.python.org/)
[![RDKit](https://img.shields.io/badge/RDKit-2022.03%2B-orange)](https://www.rdkit.org/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

## Overview

This project provides a machine learning-based tool for predicting chemical degradation products from hydroxyl radical (•OH) reactions. It uses molecular fingerprinting, template-based reaction prediction, and network analysis to generate comprehensive degradation pathways for organic compounds.

The model employs a confidence scoring system that considers molecular similarity, reaction template frequency, and reaction system consistency to predict likely degradation products and visualize them as interactive network graphs.

## Features

- 🔬 **Template-Based Reaction Prediction**: Utilizes extracted reaction templates from experimental data
- 🧪 **Molecular Similarity Analysis**: Employs Tanimoto similarity with molecular fingerprints
- 📊 **Confidence Scoring**: Multi-factor confidence calculation for prediction reliability
- 🌐 **Interactive Network Visualization**: HTML-based interactive degradation pathway networks
- 🎯 **System-Specific Predictions**: Support for different reaction systems (UV-based, Ozone-based, etc.)
- ⚡ **Optimized Performance**: Pre-computed fingerprints and indexed reaction database

## Installation

### Prerequisites

- Python 3.7 or higher
- pip package manager

### Required Dependencies

```bash
pip install rdkit-pypi
pip install pandas numpy
pip install networkx
pip install pickle
```

### Quick Install

```bash
# Clone the repository
git clone https://github.com/yourusername/hydroxyl-radical-based-reaction-product-prediction.git
cd hydroxyl-radical-based-reaction-product-prediction

# Install dependencies
pip install -r requirements.txt
```

## Project Structure

```
hydroxyl-radical-based-reaction-product-prediction/
│
├── Product_prediction.ipynb     # Main Jupyter notebook for predictions
├── degradation_model.pkl        # Pre-trained model and reaction database
├── Chemical_degradation_network.html  # Reaction library
└── README.md                    # This file
```

## Usage

### Option 1: Jupyter Notebook (Recommended)

1. Launch Jupyter Notebook:
```bash
jupyter notebook Product_prediction.ipynb
```

2. Run the notebook cells to initialize the model:
```python
from Product_prediction import OptimizedPredictiveDegradationNetwork

# Load the pre-trained model
network = OptimizedPredictiveDegradationNetwork(from_pickle='degradation_model.pkl')

# Start interactive prediction
network.query_predictive_network()
```

### Option 2: Command Line

```bash
python Product_prediction.py
```

### Option 3: Python Script

```python
from Product_prediction import OptimizedPredictiveDegradationNetwork

# Initialize the predictor
predictor = OptimizedPredictiveDegradationNetwork('degradation_model.pkl')

# Build prediction network for a specific compound
G, edge_info = predictor.build_predictive_network(
    center_smiles='CC(C)C(=O)O',  # Your compound SMILES
    max_depth=2,                   # Search depth (1-5)
    confidence_threshold=0.3,       # Confidence threshold (0-1)
    query_reaction_type='UV-based'  # Reaction system (optional)
)

# Generate visualization
html_content = predictor.generate_predictive_network_html(
    center_smiles='CC(C)C(=O)O',
    max_depth=2,
    confidence_threshold=0.3,
    reaction_type='UV-based',
    G=G,
    edge_info=edge_info
)

# Save to file
with open('output.html', 'w') as f:
    f.write(html_content)
```

## Input Parameters

### Required
- **SMILES String**: Chemical structure in SMILES format
  - Example: `CC(C)C(=O)O` for isobutyric acid

### Optional
- **Reaction System**: Specific degradation system
  - Options: `UV-based`, `Ozone-based`, `Catalyst-based`, or leave empty for all systems
- **Confidence Threshold**: Minimum confidence for predictions (0.0 - 1.0)
  - Default: 0.3
  - Higher values = fewer but more reliable predictions
- **Search Depth**: Number of degradation steps to predict (1-5)
  - Default: 2
  - Higher values = more comprehensive but potentially less accurate pathways

## Output

The tool generates an interactive HTML visualization containing:

- **Network Graph**: Visual representation of degradation pathways
  - Green solid lines: Experimentally observed pathways (100% confidence)
  - Blue dashed lines: Predicted pathways
  - Line thickness: Proportional to confidence level
- **Node Information**: 
  - Chemical structures (hover to view)
  - SMILES strings
  - Molecular properties
- **Edge Information**:
  - Reaction templates
  - Confidence scores
  - Source reaction systems

## Model Architecture

### Confidence Score Calculation

The model uses a weighted combination of three factors:

```
Confidence = α × Similarity + β × Template_Frequency + γ × System_Consistency
```

Where:
- **α**: Weight for molecular similarity
- **β**: Weight for template frequency
- **γ**: Weight for reaction system consistency

## Visualization Features

The generated HTML network includes:

- **Interactive Controls**:
  - Search by SMILES or compound name
  - Filter by confidence level
  - Hide/show different edge types
  - Zoom and pan navigation
- **Network Statistics**:
  - Total nodes and edges
  - Real vs. predicted pathways
  - Average confidence scores
- **Export Options**:
  - Download network data
  - Save as image
```


**Note**: This tool is for research purposes only. Always validate predictions with experimental data or domain expertise before making critical decisions.
