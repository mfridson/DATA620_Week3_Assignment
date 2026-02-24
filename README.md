# Assignment 3: Graph Visualization

## Overview
This project analyzes a social network graph using Python and NetworkX, calculating key network metrics and generating visualizations suitable for tools like Gephi.

## Dataset
The analysis uses a subset of the **Facebook Social Network** from the Stanford SNAP dataset:
- Source: https://snap.stanford.edu/data/ego-Facebook.html
- Subset: First 150 nodes and their connections
- **150 nodes, 603 edges**

## Graph Metrics

### Required Metric: Diameter
- **Diameter: 2** - The maximum shortest path between any two nodes in the network

### Additional Metrics
| Metric | Value |
|--------|-------|
| Average Path Length | 1.95 |
| Radius | 1 |
| Density | 0.054 |
| Average Degree | 8.04 |
| Max Degree | 149 |
| Average Clustering Coefficient | 0.64 |
| Transitivity | 0.21 |

### Key Findings
1. **Small World Property**: The low diameter (2) and short average path length (1.95) indicate a small-world network where any two people are connected by at most 2 hops.

2. **Hub Structure**: Node 0 is a central hub with degree 149 (connected to all other nodes) and the highest betweenness centrality (0.87), acting as a bridge in the network.

3. **High Clustering**: The average clustering coefficient of 0.64 indicates that nodes tend to form tightly-knit groups (friends of friends are likely to be friends).

## Files
- `graph_analysis.py` - Main analysis script
- `requirements.txt` - Python dependencies
- `graph_visualization.png` - Generated visualization with 4 plots
- `analysis_results.txt` - Detailed metrics output
- `graph.gexf` - Graph export for Gephi (recommended)
- `nodes.csv` / `edges.csv` - CSV exports for Gephi

## Installation & Usage

```bash
# Install dependencies
pip install -r requirements.txt

# Run analysis
python graph_analysis.py
```

## Visualizations

The script generates `graph_visualization.png` containing:
1. **Network Graph** - Node size = degree, color = betweenness centrality
2. **Degree Distribution** - Histogram of node degrees
3. **Clustering Coefficient Distribution** - Local clustering values
4. **Betweenness Centrality Distribution** - Node importance measures

## Gephi Visualization

For Part 3 of the assignment, import `graph.gexf` into Gephi:
1. Open Gephi and select "Open" > `graph.gexf`
2. Apply a layout algorithm (ForceAtlas2 recommended)
3. Size nodes by "degree" attribute
4. Color nodes by "betweenness" attribute
5. Export visualization for the video presentation

## Requirements
- Python 3.8+
- NetworkX 3.0+
- Matplotlib 3.7+
- NumPy 1.24+
