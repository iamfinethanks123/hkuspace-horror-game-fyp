# 🎮 Roaming SPACE — HKU SPACE KEC Horror Game

![Status](https://img.shields.io/badge/Status-Completed-success)
![Engine](https://img.shields.io/badge/Engine-Unity-black)
![Modeling](https://img.shields.io/badge/Modeling-Blender-orange)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-blue)
![License](https://img.shields.io/badge/License-MIT-green)

> A 3D first-person horror game built on a 1:1 scale model of the HKU SPACE Kowloon East Campus (KEC), developed as a Final Year Project for CCIT4080B at HKU SPACE Community College.

---

## ⬇️ Download & Play

> The full game build is hosted on OneDrive. No installation required — just download, unzip, and play!

**👉 [Download Full Game (game.zip)](https://portland-my.sharepoint.com/:u:/g/personal/tsunwaiho6-c_my_cityu_edu_hk/IQB-77ERexq1R4pYpmJQbxc8Ac7-OAL4jcs0wKdPExZD5Ro?e=6GzXnT)**

> **System Requirements:**
> - OS: Windows 10 / macOS 10.14 or above
> - RAM: 8 GB or above recommended
> - Storage: ~7 GB free space
> - GPU: Dedicated graphics card recommended for best experience

---

## 📖 Introduction

**Roaming SPACE** addresses a genuine problem faced by new students at HKU SPACE Community College: unfamiliarity with the campus structure of the Kowloon East Campus (KEC). Traditional orientation methods — such as single guided tours or static online resources — are unmemorable and unattractive.

Through **gamification**, our team transformed the KEC campus into an immersive 3D first-person game. Players can freely explore a meticulously recreated campus or challenge themselves in a horror mode filled with puzzles and monster chases — all while unconsciously memorizing the real campus layout.

---

## 🎮 Game Modes

### 🔵 Free Mode (Visit Mode)
Players navigate the KEC campus freely from a first-person perspective. Interactive **sightseeing spots** (marked with `!`) are placed in key rooms — clicking them displays **real photographs** of the actual campus facilities, bridging the gap between the virtual and real environments.

### 🔴 Horror Mode
The player becomes a **"Free-Rider"** whose GPA has been seized by the *GPA God* and *Offer God*. To escape, players must:
- Explore each floor of the campus
- Solve **diversified puzzles and question challenges**
- Collect all keys to reunite body and soul
- Evade an **AI-driven monster** that hunts the player — its speed scales with the number of questions answered incorrectly

The horror atmosphere is reinforced by **eerie lighting**, **low visibility**, and carefully designed **ambient sound effects**.

---

## ✨ Key Features

- **1:1 Campus Recreation** — ~70-80% accuracy restoration of all accessible KEC floors (G/F to 10/F)
- **First-Person Perspective** — maximizes immersion and exploration
- **Dual Game Modes** — catering to casual visitors and horror game enthusiasts alike
- **Real Photo Integration** — in-game sightseeing spots display actual campus photos
- **AI Chase Mechanism** — custom Unity NavMesh AI with dynamic difficulty scaling
- **Scene Layering Architecture** — independent floor scenes with teleportation system to optimize memory and loading performance
- **Unique Concept** — the first horror game to use HKU SPACE KEC as its game world

---

## 🛠️ Technologies Used

| Tool | Purpose |
|---|---|
| **Unity (C#)** | Game engine, scripting, AI behaviour, scene management |
| **Blender** | 3D modelling of campus floors, furniture, and props |
| **Unity NavMesh** | AI pathfinding for the monster chase mechanism |
| **Unity Addressables** | Scene layering and optimized asset loading |
| **GitHub** | Version control and project documentation |

---

## 🏗️ Project Architecture

```
Roaming SPACE
├── GROUND/          # Ground floor 3D model assets
├── 1F/              # 1st floor assets
├── 2F/              # 2nd floor assets
├── 3F/              # 3rd floor assets
├── Floorplan/       # Reference floor plan documents
├── 3DmodelShare/    # Shared 3D prop assets (chairs, desks, etc.)
└── [Full game available via download link above]
```

---

## 👥 Development Team — T3-7 Small Potatoes

| Member | Student ID | Responsibilities |
|---|---|---|
| **Ho Tsun Wai** | 20238849 | G/F–4/F modelling, Game programming, AI chase system, Horror & Free mode design |
| **Tang Pui Yin** | 20237812 | 5/F–6/F modelling, 3D prop assets, Level design |
| **Yeung Tsz Him** | 20237982 | 7/F–8/F modelling, Project management, Asset integration, Meeting minutes |
| **Yu Chun Hei** | 20238878 | 9/F–10/F modelling, Story concept, Full report writing |

---

## 📊 Project Timeline

| Milestone | Date | Description |
|---|---|---|
| Project Direction | Nov 2024 | Defined problem statement and solution |
| Campus Photography | Dec 2024 | Shot 50+ locations across all KEC floors |
| 3D Modelling (Blender) | Jan–Mar 2025 | Built floor-by-floor campus model |
| Unity Programming | Mar–Apr 2025 | Implemented game mechanics and horror mode |
| User Testing | Apr 2025 | Beta testing with secondary school students |
| Final Submission | Apr 29, 2025 | Submitted final report and game build |

---

## 📋 Testing & Results

The game was evaluated through a **user testing survey** with beta testers of varying ages:

- **70%** of testers reported improved familiarity with the KEC campus layout after playing
- **60%** of testers were satisfied with the horror elements (atmosphere, chase mechanics)
- Testers confirmed the game successfully replaces traditional monotonous orientation methods

---

## 🔭 Future Scope

- Complete missing campus floors (3/F and 4/F) using Blender and integrate via Unity
- Add **multi-language support** (English, Traditional Chinese, Simplified Chinese)
- Implement **door opening/closing mechanics** for improved realism
- Expand **AI behaviour tree** with multiple enemy modes
- Build a **leaderboard system** to track game completion speed
- Explore formal collaboration with HKU SPACE to deploy the game on the school network

---

## 📚 References

- Dumancic, M., Ruic, I. M. (2015). *Gamification in Education*. Informatologia, 48(3), 198–204.
- Garcia, M. B., et al. (2023). *A Playable 3D Virtual Tour for an Interactive Campus Visit Experience*. 2023 9th International Conference on Virtual Reality. https://doi.org/10.1109/ICVR57957.2023.10169768

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
