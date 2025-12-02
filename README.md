# 🌿 NovaNature

> **The Operating System for the Biosphere.**
> Digital management of biodiversity, reforestation, ecosystem restoration, and nature-based solutions (NbS).

[](https://www.google.com/search?q=https://github.com/novaeco-tech/novanature/actions)
[](https://opensource.org/licenses/MIT)
[](https://www.google.com/search?q=https://nature.novaeco.tech)

**NovaNature** is the Vertical Sector responsible for digitizing the natural world. While `NovaAgro` manages the *productive* land (farms), **NovaNature** manages the *regenerative* land (forests, wetlands, peatlands).

It provides the scientific proof required to turn "Nature" into an asset class. It connects physical sensors (microphones, satellites) with financial markets to validate Biodiversity Credits and Carbon Offsets with irrefutable data.

-----

## 🎯 Value Proposition

The voluntary carbon market is plagued by "Phantom Forests" and low-quality credits. **NovaNature** solves the trust crisis via **Digital MRV (Monitoring, Reporting, Verification)**:

1.  **Proof of Life:** Using AI to verify that a forest is actually diverse (birds, insects), not just a monoculture plantation.
2.  **Automated Auditing:** Replacing expensive manual site visits with continuous remote sensing (Satellite + IoT).
3.  **Regulatory Compliance:** Helping companies report against the **EU Nature Restoration Law** and **TNFD** (Taskforce on Nature-related Financial Disclosures).

-----

## 🏗️ Architecture (The Living Twin)

NovaNature acts as the geospatial database for natural assets. It relies heavily on background workers to process unstructured data (Audio, Imagery).

```mermaid
graph TD
    User((Ecologist)) -->|HTTPS| UI[NovaNature Dashboard]
    UI -->|REST| API[NovaNature API]
    
    subgraph "The Sensing Layer"
        API -->|Fetch Stream| Infra[NovaInfra (Sensors)]
        API -->|Fetch Sat Data| Sentinel[ESA/NASA API]
    end

    subgraph "The Analysis Layer"
        Infra -->|Audio Stream| Worker[Worker-Bioacoustics]
        Worker -->|Species List| API
        API -->|Tree Count| Mind[NovaMind (Computer Vision)]
    end

    subgraph "The Value Layer"
        API -->|Mint Bio-Credit| Trade[NovaTrade]
        API -->|Log Sequestration| Balance[NovaBalance]
        API -->|Verify Protected Status| Policy[NovaPolicy]
    end
```

### Integrated Services

  * **[NovaInfra](https://www.google.com/search?q=https://infrastructure.novaeco.tech):** Manages the hardware deployed in the wild—solar-powered microphones, camera traps, and soil moisture probes.
  * **[NovaMind](https://www.google.com/search?q=https://mind.novaeco.tech):** The ecologist AI. Used to count tree canopies from satellite imagery or identify specific frog species from audio.
  * **[NovaTrade](https://www.google.com/search?q=https://trade.novaeco.tech):** The marketplace. Once NovaNature proves a project is healthy, it mints "Biodiversity Tokens" here for sale.
  * **[Worker-Bioacoustics](https://www.google.com/search?q=https://bio.nature.novaeco.tech):** A specialized worker that digests massive audio files to calculate the "Acoustic Complexity Index" (ACI).

-----

## ✨ Key Features

### 1\. The "Living Ledger" (Plot Management)

A GIS interface to define and manage restoration zones.

  * **Geofencing:** Define the exact polygon of the protected area.
  * **Baseline:** Logs the initial state (Soil Carbon, Species Count) to prove "Additionality" later.

### 2\. Bio-Acoustic Monitoring

Integration with `novanature-worker-bioacoustics`.

  * **Listen:** Sensors record the forest soundscape 24/7.
  * **Detect:** Automatically flags the return of "Indicator Species" (e.g., a specific woodpecker) which proves the ecosystem is recovering.
  * **Alert:** Detects threats like chainsaws or gunshots (Poaching) and alerts rangers via `NovaPolicy`.

### 3\. Carbon + Biodiversity Stacking

Carbon isn't enough; we need diversity.

  * Calculates **Biomass Carbon** (tons/hectare) using LiDAR/Satellite data.
  * Multiplies value based on the **Biodiversity Score** (0.0 - 1.0). A forest with high biodiversity is worth *more* than a sterile tree farm.

### 4\. TNFD Reporting Engine

Automated disclosure for corporations.

  * "Your supply chain impacts 50 hectares of critical wetland."
  * "Your investment restored 20 hectares of pollinator corridor."

-----

## 🚀 Getting Started

We use **DevContainers** to provide a consistent development environment.

### Prerequisites

  * Docker Desktop
  * VS Code (with Remote Containers extension)

### Installation

1.  **Clone the repo:**
    ```bash
    git clone https://github.com/novaeco-tech/novanature.git
    cd novanature
    ```
2.  **Open in VS Code:**
      * Run `code .`
      * Click **"Reopen in Container"** when prompted.
3.  **Start the Sector:**
    ```bash
    make dev
    ```
      * **Dashboard:** http://localhost:3000 (Map View)
      * **API:** http://localhost:8000/docs

### Configuration (`.env`)

```ini
# Geospatial Settings
DEFAULT_PROJECTION=EPSG:4326
SATELLITE_PROVIDER=SENTINEL_2

# Integrations
NOVAMIND_URL=http://novamind-api:50051
NOVAINFRA_URL=http://novainfra-api:8000
WORKER_BIO_URL=http://novanature-worker-bioacoustics:8080
```

-----

## 📂 Repository Structure

This is a Monorepo containing the sector's specific logic.

```text
novanature/
├── api/                # Python/FastAPI (The Domain Logic)
│   ├── src/
│   │   ├── geo/        # PostGIS / GDAL wrappers
│   │   ├── carbon/     # Biomass estimation algorithms
│   │   └── species/    # Taxomony database & observation logs
├── app/                # React/Leaflet Frontend (The Dashboard)
│   ├── src/
│   │   ├── map/        # Interactive Satellite/Vector maps
│   │   └── audio/      # Spectrogram player for bioacoustics
├── website/            # Documentation (Docusaurus)
└── tests/              # Integration tests
```

-----

## 🧪 Testing

We use **Geospatial Simulation** for testing.

  * **Plot Logic:** `make test-geo`
      * Asserts that a "Protected Zone" polygon correctly rejects an overlap with an "Industrial Zone."
  * **MRV Pipeline:** `make test-mrv`
      * Simulates a stream of data: "New Tree Detected (Sat)" + "Birdsong Detected (Audio)" -\> Verifies that a "Biodiversity Credit" is minted in `NovaTrade`.

-----

## 🤝 Contributing

We need contributors with backgrounds in **Ecology**, **Geospatial Engineering (GIS)**, and **Bioacoustics**.
See [CONTRIBUTING.md](https://www.google.com/search?q=../.github/CONTRIBUTING.md) for details.

**Maintainers:** `@novaeco-tech/maintainers-sector-novanature`