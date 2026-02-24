# Roaming SPACE — HKU SPACE KEC Horror Game (FYP)

![Status](https://img.shields.io/badge/Status-Completed-success)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-blue)
![Engine](https://img.shields.io/badge/Engine-Unity-black)
![Modeling](https://img.shields.io/badge/Modeling-Blender-orange)
![License](https://img.shields.io/badge/License-MIT-green)

> **Course:** CCIT4080B Final Year Project — HKU SPACE Community College  
> **Team:** T3-7 Small Potatoes  
> **Year:** 2025–2026  

---

## Table of Contents
1. [Project Overview](#-project-overview)
2. [Background & Motivation](#-background--motivation)
3. [Game Modes](#-game-modes)
4. [Campus Floors Covered](#-campus-floors-covered)
5. [Tech Stack](#-tech-stack)
6. [Repository Structure](#-repository-structure)
7. [Download & Run](#-download--run)
8. [Screenshots & Floor Plans](#-screenshots--floor-plans)
9. [Documentation](#-documentation)
10. [Team](#-team)
11. [License](#-license)

---

## Project Overview

**Roaming SPACE** is a 3D first-person horror-exploration game built in Unity that recreates the **HKU SPACE Kowloon East Campus (KEC)** at a 1:1 scale. It was developed as a Final Year Project to address a genuine problem: new students at KEC frequently get lost because the campus layout is non-intuitive, spread across multiple floors with overlapping corridors.

By wrapping campus navigation inside an engaging horror game, the project turns a tedious orientation exercise into a memorable experience — players learn where the library, classrooms, and facilities are because survival depends on it.

---

## Background & Motivation

### Problem Statement
Many freshmen at HKU SPACE KEC report feeling disoriented during their first weeks. Traditional orientation methods (printed maps, guided tours) are passive and easily forgotten.

### Proposed Solution
A gamified, self-paced 3D exploration tool that:
- Reconstructs every major floor of KEC using reference photography and architectural floor plans.
- Embeds **"Sightseeing Points"** — in-game hotspots that display real photographs of the actual location, bridging the virtual and real worlds.
- Provides a **Horror Mode** that raises stakes: getting lost means being chased by an enemy AI, reinforcing spatial memory through adrenaline.

### Target Users
- Prospective and incoming students at HKU SPACE KEC.
- Event participants visiting the campus for the first time.

---

## Game Modes

### 1. Free Mode (Visit Mode)
| Feature | Details |
|---|---|
| Objective | Freely explore the campus at your own pace |
| Sightseeing Points | Interactive hotspots showing real campus photos |
| Threat | None — safe exploration |
| Best For | Orientation, first-time visitors |

### 2. Horror Mode
| Feature | Details |
|---|---|
| Objective | Solve floor-based puzzles and questions |
| Failure Condition | Wrong answers / getting caught triggers enemy chase |
| AI Enemy | Pathfinding-based pursuit with dynamic lighting & sound |
| Atmosphere | Ambient horror audio, flickering lights, jump scares |
| Best For | Returning players, engagement and replay value |

---

## Campus Floors Covered

| Floor | Key Locations Modelled |
|---|---|
| Ground Floor | Entrance lobby, reception, main corridors |
| 1F | Classrooms, student common areas |
| 2F | Administrative offices, meeting rooms |
| 3F | Computer labs, study rooms |
| 4F–9F | Lecture theatres, faculty offices, library |
| 10F | Rooftop / upper facilities |

Each floor is implemented as a **separate Unity Scene** and connected via teleport triggers to manage memory and performance.

---

## Tech Stack

| Category | Tool / Technology |
|---|---|
| Game Engine | Unity (C#) |
| 3D Modelling | Blender |
| Version Control | Git + GitHub |
| Asset Management | Unity Asset Store + custom models |
| Build Target | Windows (PC Standalone) |
| AI Navigation | Unity NavMesh |
| Audio | Unity Audio Mixer |

---

## Repository Structure

```
hkuspace-horror-game-fyp/
├── 1F/                  # Floor 1 reference photos & floor plan assets
├── 2F/                  # Floor 2 reference photos & floor plan assets
├── 3F/                  # Floor 3 reference photos & floor plan assets
├── 10F/                 # Floor 10 reference photos & floor plan assets
├── Floorplan/           # Architectural floor plan scans used for modelling
├── docs/
│   ├── TECHNICAL.md     # Architecture, scene design, AI system
│   ├── TESTING.md       # Testing approach, evaluation, known issues
│   └── BUILD_AND_RUN.md # How to run the downloaded build
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

> **Note:** The full Unity project (7.9 GB, including all 3D models, textures, and audio) is hosted externally due to GitHub file size limits. See [Download & Run](#-download--run) below.

---

## Download & Run

### Playable Build (Recommended)

The complete game build is available for download via the link below:

**[⬇️ Download Roaming SPACE (ZIP, ~7GB)](https://portland-my.sharepoint.com/:u:/g/personal/tsunwaiho6-c_my_cityu_edu_hk/IQB-77ERexq1R4pYpmJQbxc8Ac7-OAL4jcs0wKdPExZD5Ro?e=6GzXnT)**

### System Requirements
| Requirement | Minimum | Recommended |
|---|---|---|
| OS | Windows 10 | Windows 10/11 |
| CPU | Intel i5 / AMD Ryzen 5 | Intel i7 / AMD Ryzen 7 |
| RAM | 8 GB | 16 GB |
| GPU | NVIDIA GTX 1060 | NVIDIA RTX 2060 or above |
| Storage | 10 GB free | 15 GB free (SSD preferred) |

### Quick Start
1. Download and extract the ZIP file to your local drive.
2. Open the extracted folder and run `RoamingSPACE.exe`.
3. Select your preferred game mode from the main menu.
4. Use `WASD` to move, `Mouse` to look around, `E` to interact.

For detailed instructions, see [docs/BUILD_AND_RUN.md](docs/BUILD_AND_RUN.md).

---

## Screenshots & Floor Plans

Reference photographs and floor plans used during the modelling process are stored in the `/1F`, `/2F`, `/3F`, `/10F`, and `/Floorplan` directories of this repository. These document the real-world locations that were recreated in the game.

---

## Documentation

| Document | Description |
|---|---|
| [TECHNICAL.md](docs/TECHNICAL.md) | System architecture, scene management, AI design, performance optimisation |
| [TESTING.md](docs/TESTING.md) | Testing methodology, user evaluation, known issues, future improvements |
| [BUILD_AND_RUN.md](docs/BUILD_AND_RUN.md) | Step-by-step instructions to run the game |
| [CONTRIBUTING.md](CONTRIBUTING.md) | How to contribute to this project |

---

## Team

**T3-7 Small Potatoes** — HKU SPACE Community College, 2025–2026

| Role | Responsibilities |
|---|---|
| Unity Development | Scene building, scripting (C#), AI system |
| 3D Modelling | Blender modelling of campus interiors and exteriors |
| Game Design | Mode design, puzzle design, UX flow |
| Documentation | Technical writing, evaluation, project management |

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

Real campus photographs included in this repository are used solely for academic and non-commercial purposes.

---

*HKU SPACE Community College — Final Year Project CCIT4080B*
