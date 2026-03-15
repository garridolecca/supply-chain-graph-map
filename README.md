# Supply Chain Network Explorer

An interactive dashboard combining **ArcGIS Maps SDK for JavaScript 5.0** with **D3.js force-directed graph visualization**, inspired by [dgraph-viewer](https://github.com/corewood-tech/dgraph-viewer).

## Live Demo

**[View Live App](https://garridolecca.github.io/supply-chain-graph-map/)**

## Screenshot

![Supply Chain Network Explorer](https://img.shields.io/badge/ArcGIS_JS-5.0-blue?style=flat-square) ![D3.js](https://img.shields.io/badge/D3.js-v7-orange?style=flat-square) ![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

## Overview

A single-page app that visualizes a global supply chain network across **21 locations** and **27 connections** spanning 5 node types:

| Type | Shape (Map) | Shape (Graph) | Examples |
|---|---|---|---|
| Factory | Diamond | Rotated square | Shenzhen, Detroit, Stuttgart, Chennai, Monterrey |
| Warehouse | Circle | Circle | Rotterdam, Singapore, Memphis, Dubai |
| Port | Triangle | Triangle | Shanghai, Los Angeles, Hamburg, Mumbai |
| Supplier | Square | Square | Taiwan Semiconductor, Korean Electronics |
| Retailer | Cross | Circle | NYC, London, Tokyo, São Paulo |

## Features

### Dual-View Visualization
- **Geographic view** — ArcGIS 5.0 dark basemap with supply route lines colored and sized by type/volume
- **Topological view** — D3.js force-directed graph with drag interaction and neighbor highlighting

### Cross-Highlighting
Click any node on the map or graph to:
- Highlight it and its direct neighbors in both views
- Zoom the map to the selected location
- Show detailed metrics in the inspector panel

### Graph Algorithms (from dgraph-viewer)
| Algorithm | What it does |
|---|---|
| **Degree Centrality** | Scales nodes by connection count |
| **PageRank** | Scales nodes by iterative importance score |
| **Betweenness Centrality** | Scales nodes by how often they sit on shortest paths |
| **Community Detection** | Colors nodes by detected community (label propagation) |
| **Shortest Path** | Highlights the BFS shortest path between two selected nodes |

### Inspector Panel
Shows per-node metrics: type, country, capacity, degree, in/out edges, total volume, PageRank score, and betweenness centrality.

### Toolbar
- **Toggle Map Links** — Show/hide supply route lines on the map
- **Fit Graph** — Re-energize the force simulation
- **Reset** — Clear all highlights and return to default view

## Tech Stack

- **[ArcGIS Maps SDK for JavaScript 5.0](https://developers.arcgis.com/javascript/latest/)** — Map rendering, web components (`<arcgis-map>`), Calcite Design System
- **[D3.js v7](https://d3js.org/)** — Force-directed graph layout, SVG rendering, drag interaction
- **[Calcite Components](https://developers.arcgis.com/calcite-design-system/)** — Shell layout, navigation, action bar, panels
- **Vanilla JavaScript** — No build step, no frameworks, single HTML file

## Getting Started

1. Clone the repo:
   ```bash
   git clone https://github.com/garridolecca/supply-chain-graph-map.git
   ```
2. Open `index.html` in a browser — no server or build step required.

## Inspired By

- **[dgraph-viewer](https://github.com/corewood-tech/dgraph-viewer)** — Graph algorithms (PageRank, betweenness centrality, community detection, BFS shortest path), force-directed layout patterns, node inspector panel, and cross-highlighting approach.

## License

MIT
