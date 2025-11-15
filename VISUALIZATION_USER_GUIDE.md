# Chemical Degradation Network Visualization - User Guide

## Table of Contents
1. [Overview](#overview)
2. [Interface Components](#interface-components)
3. [Navigation Controls](#navigation-controls)
4. [Search and Filter Functions](#search-and-filter-functions)
5. [Query Mode](#query-mode)
6. [Understanding the Network](#understanding-the-network)
7. [Interactive Features](#interactive-features)
8. [Performance Optimization](#performance-optimization)
9. [Data Export](#data-export)
10. [Troubleshooting](#troubleshooting)
11. [Keyboard Shortcuts](#keyboard-shortcuts)
12. [Best Practices](#best-practices)

---

## Overview

The Chemical Degradation Network Visualization is an interactive web-based tool that displays complex chemical degradation pathways as network graphs. It visualizes the relationships between chemical compounds and their degradation products through hydroxyl radical reactions.

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
- **Chemical Group Filter**: Dropdown to filter by compound families
- **Layout Options**: Network arrangement algorithms
- **Display Settings**: Visual customization options

### 2. Query Panel (Blue Bar)
Secondary control panel for advanced queries:

- **Query SMILES Input**: Enter target compound for subnetwork analysis
- **Depth Selector**: Choose exploration depth (1-3 levels)
- **Confidence Threshold**: Filter predictions by confidence score
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
   - **Multiple Matches**: Shows first match

### Chemical Group Filtering

1. **Select Group from Dropdown**:
   ```
   Options include:
   - All (default)
   - phenol-based
   - benzene-based
   - N heterocyclic-based
   - aliphatic ring-based
   - And more...
   ```

2. **Apply Filter**:
   - Network updates to show only selected group
   - Edges connecting to other groups fade
   - Statistics update in info panel

3. **Clear Filter**:
   - Select "All" to show complete network
   - Or click "Reset View" button

### Edge Type Filtering

Control edge visibility using toggle buttons:

- **Real Edges** (Green):
  - Experimentally observed reactions
  - 100% confidence
  - Solid lines

- **Predicted Edges** (Blue):
  - Machine learning predictions
  - Variable confidence (30-99%)
  - Dashed lines

- **Cross-System Edges** (Orange):
  - Reactions from different systems
  - Modified confidence scores
  - Dotted lines

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
   
   **Confidence Threshold**:
   - `0.3`: Show more predictions (default)
   - `0.5`: Moderate filtering
   - `0.7`: High confidence only
   - `0.9`: Near-certain predictions

3. **Generate Network**:
   - Click "🔬 Generate Subnetwork"
   - Wait for processing (1-5 seconds)
   - View focused visualization

4. **Subnetwork Features**:
   - Central node highlighted
   - Radial layout from query compound
   - Depth levels shown by distance
   - Color gradient for confidence

### Returning to Full Network

- Click "📊 Show Full Network" button
- Or press 'F' key
- Restores complete visualization

---

## Understanding the Network

### Node Properties

#### Visual Encoding
- **Size**: Proportional to degree (connections)
- **Color**: Chemical group classification
- **Border**: 
  - Solid: Experimental compound
  - Dashed: Predicted intermediate
  - Bold: Selected/highlighted

#### Node Labels
- Displayed for high-degree nodes
- Show simplified names or formulas
- Full SMILES on click/hover

### Edge Properties

#### Visual Encoding
- **Color**:
  - Green: Real/experimental pathway
  - Blue: Predicted pathway
  - Orange: Cross-system transfer
  
- **Style**:
  - Solid: High confidence (>80%)
  - Dashed: Medium confidence (50-80%)
  - Dotted: Low confidence (<50%)
  
- **Thickness**: Proportional to confidence score
- **Opacity**: Indicates reaction frequency

#### Edge Direction
- Arrows point from reactant to product
- Bidirectional edges possible for reversible reactions

### Chemical Groups

The system classifies compounds into families:

| Group | Color | Description |
|-------|-------|-------------|
| Phenol-based | Red (#FF6B6B) | Compounds with phenolic structures |
| Benzene-based | Teal (#98D8C8) | Simple aromatic compounds |
| Macrocycle-based | Cyan (#4ECDC4) | Large ring structures |
| N heterocyclic | Blue (#85C1E2) | Nitrogen-containing rings |
| Aliphatic | Purple (#7209B7) | Non-aromatic cyclic compounds |
| Simple aliphatic | Magenta (#B5179E) | Linear/branched chains |

---

## Interactive Features

### Molecular Structure Popup

**Activation**: Click any node

**Display Content**:
- 2D molecular structure image
- SMILES notation
- Molecular formula (if available)
- Chemical group classification
- Degradation statistics

**Controls**:
- Click outside to close
- Drag to reposition
- Copy SMILES button

### Reaction Template Popup

**Activation**: Click any edge

**Display Content**:
- Reaction template visualization
- Template class (e.g., "Hydroxylation")
- SMIRKS pattern
- Confidence score
- Number of training examples
- Reaction conditions (if available)

**Template Classes**:
```
Common templates:
- Hydroxylation (•OH addition)
- H-abstraction (H removal)
- Ring opening
- Decarboxylation
- N-dealkylation
- Aromatic substitution
```

### Tooltip Information

**Node Hover**:
```
Compound: [Name/SMILES]
Group: [Chemical family]
Degree: [Number of connections]
Type: [Real/Predicted]
```

**Edge Hover**:
```
Reaction: [Source] → [Target]
Template: [Class name]
Confidence: [Score]
System: [UV/Ozone/etc.]
```

---

## Performance Optimization

### For Large Networks (>1000 nodes)

1. **Disable Physics**:
   - Toggle physics off after initial layout
   - Reduces CPU usage significantly
   - Allows smoother navigation

2. **Use Filtered Views**:
   - Work with chemical group subsets
   - Focus on specific reaction systems
   - Limit depth in queries

3. **Adjust Render Settings**:
   - Reduce edge smooth type
   - Disable shadows
   - Limit label display

### Loading Performance

**Initial Load**:
- Networks >3000 nodes may take 1-2 minutes
- Progress shown in loading overlay
- Physics stabilization runs automatically

**Optimization Tips**:
- Close other browser tabs
- Use Chrome/Firefox for best performance
- Ensure adequate RAM (4GB+ recommended)

---

## Data Export

### Network Data Export

1. **Export Options** (if available):
   - JSON format: Complete network structure
   - GraphML: For Cytoscape/Gephi import
   - CSV: Node and edge lists

2. **Screenshot Capture**:
   - Use browser print function (Ctrl+P)
   - Select "Save as PDF"
   - Or use screenshot tools

3. **Selected Data**:
   - Right-click node for SMILES copy
   - Select multiple nodes (Ctrl+Click)
   - Export selection only

---

## Troubleshooting

### Common Issues and Solutions

#### Network Won't Load
- **Check file size**: Large files need more time
- **Browser compatibility**: Use modern browsers
- **Clear cache**: Ctrl+Shift+R for hard refresh
- **Memory**: Close unnecessary applications

#### Search Not Working
- **Verify SMILES format**: Use canonical SMILES
- **Check for spaces**: Remove trailing spaces
- **Special characters**: Encode properly
- **Try alternatives**: Use InChI or name search

#### Slow Performance
- **Disable physics**: After layout stabilizes
- **Reduce visible nodes**: Use filters
- **Lower quality settings**: Adjust rendering
- **Hardware acceleration**: Enable in browser

#### Popup Windows Not Showing
- **Check popup blockers**: Disable for this site
- **JavaScript enabled**: Required for functionality
- **Click accuracy**: Ensure clicking on element
- **Z-index issues**: Refresh page

---

## Keyboard Shortcuts

### Navigation
- **Arrow Keys**: Pan view (↑↓←→)
- **+/-**: Zoom in/out
- **Home**: Fit network to screen
- **PageUp/PageDown**: Large zoom steps

### Selection
- **Ctrl+A**: Select all visible nodes
- **Shift+Click**: Add to selection
- **Ctrl+Click**: Toggle selection
- **Esc**: Clear selection

### Modes
- **F**: Show full network
- **Q**: Enter query mode
- **S**: Focus search box
- **R**: Reset view

### Display
- **L**: Toggle labels
- **P**: Toggle physics
- **E**: Toggle edges
- **G**: Cycle through layouts

---

## Best Practices

### Effective Exploration

1. **Start with Overview**:
   - View full network first
   - Identify major hubs
   - Note chemical group distributions

2. **Progressive Refinement**:
   - Filter by chemical groups
   - Increase confidence thresholds gradually
   - Focus on specific pathways

3. **Query Strategy**:
   - Begin with depth=1 for immediate products
   - Increase depth for pathway discovery
   - Adjust confidence based on needs

### Scientific Analysis

1. **Validation Approach**:
   - Prioritize high-confidence predictions
   - Cross-reference with literature
   - Consider reaction feasibility

2. **Pattern Recognition**:
   - Look for common transformation motifs
   - Identify degradation hotspots
   - Note persistent structures

3. **Comparative Analysis**:
   - Compare different starting compounds
   - Analyze system-specific differences
   - Evaluate pathway alternatives

### Presentation and Sharing

1. **Creating Figures**:
   - Arrange network for clarity
   - Hide unnecessary elements
   - Use consistent zoom levels
   - Export high-resolution images

2. **Highlighting Pathways**:
   - Select specific routes
   - Adjust colors for contrast
   - Add annotations if needed
   - Create multiple views

3. **Documentation**:
   - Record parameter settings
   - Note confidence thresholds
   - Save network states
   - Export underlying data

---

## Advanced Features

### Custom Layouts

**Force-Directed**:
- Natural clustering
- Good for small networks
- CPU intensive

**Hierarchical**:
- Shows degradation levels
- Clear parent-child relationships
- Best for tree-like structures

**Circular**:
- Equal node emphasis
- Clear edge patterns
- Good for dense networks

### Multi-Selection Operations

1. **Box Selection**:
   - Hold Shift + Drag
   - Selects enclosed nodes
   - Useful for subgraph extraction

2. **Path Selection**:
   - Ctrl+Click endpoints
   - Selects shortest path
   - Highlights degradation route

3. **Cluster Selection**:
   - Double-click hub node
   - Selects neighborhood
   - Shows local network

---

## Tips for Different Use Cases

### Research Applications
- Document confidence thresholds used
- Export data for statistical analysis
- Create reproducible visualizations
- Focus on mechanistic insights

### Educational Use
- Start with simple compounds
- Use step-by-step depth increase
- Highlight reaction templates
- Compare predicted vs. real pathways

### Regulatory Assessment
- Emphasize high-confidence predictions
- Track transformation products
- Identify persistent compounds
- Document degradation pathways

### Industrial Applications
- Focus on process-relevant compounds
- Analyze system-specific pathways
- Identify optimization opportunities
- Evaluate treatment effectiveness

---

## System Requirements

### Minimum Requirements
- **Browser**: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+
- **RAM**: 2GB available
- **Screen Resolution**: 1366x768
- **JavaScript**: Enabled
- **Internet**: For loading external libraries

### Recommended Specifications
- **Browser**: Latest Chrome or Firefox
- **RAM**: 4GB+ available
- **Screen Resolution**: 1920x1080 or higher
- **GPU**: Hardware acceleration enabled
- **Network**: Stable connection for large files

---

## Contact and Support

For technical issues, feature requests, or questions about the visualization tool, please:

1. Check this user guide first
2. Review the troubleshooting section
3. Contact the development team
4. Submit issues on GitHub

---

*Last Updated: 2024*  
*Version: 1.0.0*