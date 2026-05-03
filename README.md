# FUSION.AI — Strategic Multi-Source Intelligence Dashboard

A real-time, web-based intelligence fusion platform that unifies **OSINT**, **HUMINT**, and **IMINT** data onto a single interactive geospatial map — creating a true **Common Operating Picture** for analysts and decision-makers.

---

## Live Demo

> Open `index.html` directly in any modern browser (Chrome / Edge recommended).  
> Internet connection required for map tiles to load.

---

## Problem Statement

Modern intelligence analysts are forced to toggle between multiple tools — database viewers, spreadsheets, and image galleries — to piece together a complete picture. This leads to:

- **Delayed reaction times** due to fragmented data
- **Lack of situational awareness** without a unified view
- **No geospatial anchoring** of intelligence to physical locations

**FUSION.AI** solves this by ingesting all three intelligence types onto one unified terrain map with instant hover-and-view inspection.

---

## Tech Stack & Architecture

| Layer | Technology | Role |
|---|---|---|
| Geospatial Map | Leaflet.js | Interactive terrain map with custom node markers |
| Data Ingestion | HTML5 File API | Drag-and-drop CSV / JSON / JPG / JPEG support |
| Visualization | Chart.js | Node distribution doughnut chart |
| OSINT Source | MongoDB / AWS S3 | Cloud-based open source intelligence ingestion |
| HUMINT Source | CSV / JSON Upload | Manual field report ingestion |
| IMINT Source | JPG / JPEG Upload | Satellite and aerial imagery ingestion |
| Fusion Engine | Cross-modal correlation | Confidence scoring across all three sources |

---

## Key Features

- **Unified Geospatial Map** — All OSINT, HUMINT, and IMINT nodes plotted as color-coded interactive markers on a real terrain map
- **Hover-and-View Popups** — Hovering over any node instantly shows metadata: coordinates, confidence score, source, and timestamp — without navigating away
- **Click for Full Detail** — Clicking any node opens a full inspector modal with imagery placeholder and complete intelligence report
- **Drag & Drop Ingestion** — Drop CSV/JSON files (auto-classified as HUMINT) or JPG/PNG images (auto-classified as IMINT) directly onto the dashboard
- **Source Filter** — Toggle between OSINT / HUMINT / IMINT / All views instantly
- **Live Node Injection** — Inject new intelligence nodes in real time
- **Intelligence Timeline** — Chronological feed of all ingested events
- **Threat Assessment Panel** — Fusion engine confidence scores across all source types
- **Node Distribution Chart** — Live doughnut chart showing source breakdown

---

## System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    Data Ingestion Layer                  │
│  ┌───────────────┐  ┌──────────────┐  ┌─────────────┐  │
│  │  MongoDB / S3 │  │  CSV / JSON  │  │ JPG / JPEG  │  │
│  │    (OSINT)    │  │   (HUMINT)   │  │   (IMINT)   │  │
│  └───────┬───────┘  └──────┬───────┘  └──────┬──────┘  │
└──────────┼─────────────────┼─────────────────┼──────────┘
           │                 │                 │
┌──────────▼─────────────────▼─────────────────▼──────────┐
│                  Intelligence Fusion Engine              │
│         Cross-modal Confidence Scoring & Tagging        │
│              Corroboration Detection (FUSED nodes)      │
└──────────────────────────┬──────────────────────────────┘
                           │
┌──────────────────────────▼──────────────────────────────┐
│            Geospatial Visualization Layer               │
│   Leaflet.js Map · Color-coded Markers · Hover Popups  │
└─────────────────────────────────────────────────────────┘
```

---

##  Intelligence Node Types

| Type | Color | Source | Description |
|---|---|---|---|
| OSINT | 🔵 Cyan | MongoDB / AWS S3 | Open source signals, social media, AIS data |
| HUMINT | 🟢 Green | CSV / JSON upload | Field agent reports, contact reports |
| IMINT | 🟠 Orange | JPG / JPEG upload | Satellite imagery, aerial reconnaissance |
| FUSED | 🟣 Purple | Fusion Engine | Triple-corroborated high-confidence nodes |

---

##  How to Run

### Option 1 — Local (Instant)
```bash
# Download and open directly
open index.html       # macOS
start index.html      # Windows
```
No server or installation needed. Requires internet for map tiles.

### Option 2 — GitHub Pages (Live Link)
1. Fork or clone this repository
2. Go to **Settings → Pages → Source → main branch**
3. Live URL: `https://yourusername.github.io/intelligence-dashboard`

---

##  Project Structure

```
intelligence-dashboard/
│
├── index.html        # Complete dashboard (single-file application)
└── README.md         # Project documentation
```

---

## 🔬 How the Fusion Engine Works

### Confidence Scoring
Each node is scored based on:
- **Source reliability** — MongoDB/S3 OSINT vs manual upload
- **Corroboration count** — how many independent sources confirm the node
- **Data freshness** — timestamp recency weighting

### FUSED Node Creation
When two or more source types (e.g. OSINT + HUMINT, or HUMINT + IMINT) report activity in the same geographic zone within a time window, the fusion engine creates a **FUSED node** with an elevated confidence score.

### Drag & Drop Classification
| File Type | Auto-classified As |
|---|---|
| `.csv` | HUMINT — Field Report |
| `.json` | HUMINT — Structured Data |
| `.jpg` / `.jpeg` / `.png` | IMINT — Imagery Asset |

---

## Screenshots

> Dashboard running in browser — unified terrain map with OSINT, HUMINT, and IMINT nodes, hover popups, and intelligence timeline.

---

## 👤 Author

Built as part of an AI/ML engineering assessment.  
Stack: HTML5 · JavaScript · Leaflet.js · Chart.js · File API · Fusion Engine

---

## License

MIT License — free to use and modify.
