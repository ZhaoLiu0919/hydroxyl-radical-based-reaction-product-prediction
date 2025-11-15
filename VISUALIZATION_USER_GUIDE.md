# Chemical Degradation Network Visualization - User Guide

## Overview

The Chemical Degradation Network Visualization is an interactive web-based tool that displays complex chemical degradation pathways as network graphs. It visualizes the relationships between chemical compounds and their degradation products through degradation reactions.

### Key Capabilities
- **Large-scale visualization**: Handles networks with thousands of nodes and edges
- **Interactive exploration**: Click, zoom, and navigate through chemical structures
- **Multi-mode viewing**: Full network or focused subnetwork analysis
- **Chemical group classification**: Color-coded compounds by structural families
- **Reaction template display**: View transformation patterns between compounds
- **Real-time search**: Find specific compounds instantly

---

## Interface Components

### 1. Control Panel (Top Bar)
Located at the top of the interface with a dark background, containing:

- **Search Box**: Text input for SMILES string search
- **Search Button**: Initiates compound search
- **Reset View**: Returns to default zoom and position
- **Edge Visibility Toggles**: Show/hide different edge types

### 2. Query Panel (Blue Bar)
Secondary control panel for advanced queries:

- **Query SMILES Input**: Enter target compound for subnetwork analysis
- **Direction Selector**: Choose exploration direction (Upstream, downstream, and both)
- **Depth Selector**: Choose exploration depth (1-10 levels)
- **Generate Subnetwork**: Create focused visualization
- **Show Full Network**: Return to complete network view

### 3. Main Visualization Area
Central white canvas displaying the network graph with:

- **Nodes**: Represent chemical compounds
- **Edges**: Represent degradation reactions
- **Interactive elements**: Clickable nodes and edges

### 4. Information Panel (Bottom)
Status bar showing:
- Current network statistics (nodes/edges count)
- Selected element information
- Interaction hints

### 5. Mode Indicator (Top Left)
Displays current viewing mode:
- 📊 Full Network Mode
- 🔬 Query Subnetwork Mode

### 6. Legend Panel (Right Side)
Color-coded guide for chemical groups:
- Lists all compound families
- Shows associated colors
- Scrollable for long lists

---

## Navigation Controls

### Mouse Controls

#### Basic Navigation
- **Left Click + Drag**: Pan across the network
- **Scroll Wheel**: Zoom in/out
- **Double Click on Background**: Zoom in at clicked location
- **Right Click + Drag**: Box selection (if enabled)

#### Node Interactions
- **Single Click on Node**: 
  - Selects the node
  - Displays molecular structure popup
  - Shows SMILES string
  - Highlights connected edges

- **Double Click on Node**:
  - Centers view on the node
  - Zooms to optimal level
  - Shows immediate neighbors

- **Hover over Node**:
  - Displays tooltip with compound name
  - Shows degree (number of connections)
  - Indicates chemical group

#### Edge Interactions
- **Click on Edge**:
  - Displays reaction template popup
  - Shows transformation pattern
  - Displays confidence score
  - Shows reaction class

- **Hover over Edge**:
  - Highlights the edge
  - Shows source and target compounds
  - Displays edge weight/confidence

### Navigation Buttons
Located in the lower right corner:

- **➕ Zoom In**: Increases magnification
- **➖ Zoom Out**: Decreases magnification  
- **🏠 Fit**: Auto-fits entire network in view
- **⬆⬇⬅➡ Arrow Keys**: Pan in directions

---

## Search and Filter Functions

### SMILES Search

1. **Enter SMILES String**:
   - Type or paste SMILES in search box
   - Supports canonical and non-canonical formats
   - Case-sensitive for stereochemistry

2. **Execute Search**:
   - Click "🔍 Search" or press Enter
   - System standardizes SMILES automatically
   - Highlights matching node if found

3. **Search Results**:
   - **Found**: Node highlighted in red, view centers on it
   - **Not Found**: Alert message with suggestions

---

## Query Mode

### Generating Subnetworks

1. **Enter Query Compound**:
   - Input SMILES in Query Panel
   - Verify structure is valid

2. **Set Parameters**:
   
   **Depth Level**:
   - `1`: Direct products only
   - `2`: Products and their products
   - `3`: Three-step degradation pathways
   - `up to 10`
   
   **Direction**:
   - `Upstream`: Parent only
   - `Downstream`: Product only
   - `Both`: Both parent and product

3. **Generate Network**:
   - Click "🔬 Generate Subnetwork"
   - Wait for processing (1-5 seconds)
   - View focused visualization

4. **Subnetwork Features**:
   - Central node highlighted
   - Radial layout from query compound
   - Depth levels shown by distance

### Returning to Full Network

- Click "📊 Show Full Network" button
- Restores complete visualization

---
## Interactive Features

### Molecular Structure Popup

**Activation**: Click any node

**Display Content**:
- 2D molecular structure image
- SMILES notation
- Chemical group classification
- Degradation degree (in/out)

### Reaction Template Popup

**Activation**: Click any edge

**Display Content**:
- Reaction template visualization
- SMIRKS pattern
- Template class distribution
- Reaction type
