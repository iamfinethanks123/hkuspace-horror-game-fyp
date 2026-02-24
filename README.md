# 🎮 Roaming SPACE — HKU SPACE KEC Horror Game

![Status](https://img.shields.io/badge/Status-Completed-success)
![Engine](https://img.shields.io/badge/Engine-Unity-black)
![Modeling](https://img.shields.io/badge/Modeling-Blender-orange)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-blue)
![License](https://img.shields.io/badge/License-MIT-green)

> A 3D first-person horror game built on a 1:1 scale model of the HKU SPACE Kowloon East Campus (KEC), developed as a Final Year Project for CCIT4080B at HKU SPACE Community College.

---

## ⬇️ Download & Play

> Due to the massive scale of the high-fidelity 3D assets (~7.9GB), the raw Unity project files are not hosted on GitHub to preserve repository performance. Instead, you can download the fully compiled, playable game directly from our secure educational OneDrive.

**👉 [Download Full Game Build (game.zip)](https://portland-my.sharepoint.com/:u:/g/personal/tsunwaiho6-c_my_cityu_edu_hk/IQB-77ERexq1R4pYpmJQbxc8Ac7-OAL4jcs0wKdPExZD5Ro?e=6GzXnT)**

> **System Requirements:**
> - **OS:** Windows 10 / macOS 10.14 or above
> - **RAM:** 8 GB or above recommended
> - **Storage:** ~7 GB free space required for extraction
> - **GPU:** Dedicated graphics card strongly recommended for rendering real-time lighting and high-res textures.

---

## 📖 Project Overview

**Roaming SPACE** was engineered to solve a genuine problem faced by new students at HKU SPACE Community College: unfamiliarity with the complex campus structure of the Kowloon East Campus (KEC). Traditional orientation methods — such as single guided tours or static online floor plans — are often unmemorable and fail to engage students.

By leveraging **gamification**, our team transformed the KEC campus into a highly immersive 3D first-person game. Players can freely explore a meticulously recreated 1:1 campus or challenge themselves in a tense "Horror Mode" filled with puzzles and AI-driven monster chases. This approach allows players to unconsciously memorize the real campus layout while experiencing an adrenaline-pumping gameplay loop.

For deeper insights into how this game was built, please explore our documentation:
- 📄 [Game Design Document (GDD)](docs/Game_Design_Document.md)
- ⚙️ [Technical Architecture](docs/Technical_Architecture.md)
- 📝 [Post-Mortem & Development Reflection](docs/Post_Mortem.md)

---

## 🎮 Core Game Modes

### 🔵 Free Mode (Virtual Tour)
Designed for casual exploration. Players navigate the KEC campus freely from a first-person perspective. Interactive **Sightseeing Spots** (marked with `!`) are placed in key rooms. Clicking them displays **real-life reference photographs** of the actual campus facilities, bridging the gap between the virtual construct and the real environment.

### 🔴 Horror Mode (Survival Challenge)
The player takes on the persona of a **"Free-Rider"** whose academic destiny (GPA) has been seized by the elusive *GPA God* and *Offer God*. To escape the nightmare, players must:
- Navigate the darkened, eerie corridors of KEC.
- Solve **diversified puzzles and academic-themed questions**.
- Collect hidden keys to reunite body and soul.
- Evade a relentless **AI-driven monster**. The monster's movement speed dynamically scales based on the number of questions the player answers incorrectly.

The horror atmosphere is heavily reinforced by **dynamic low-visibility lighting**, **eerie ambient soundscapes**, and sudden chase sequences.

---

## ✨ Key Technical Features

- **1:1 Campus Recreation** — Achieved ~70-80% architectural accuracy of all accessible KEC floors (G/F to 10/F) using custom Blender models and real-world floor plans.
- **Dynamic AI Chase Mechanism** — Utilized Unity NavMesh to build an AI that calculates the shortest path to the player dynamically.
- **Scene Layering Architecture** — To handle the massive 7GB+ asset load, the campus was divided into independent floor scenes. A custom teleportation system loads and unloads floors dynamically to optimize RAM usage.
- **Immersive Real-Photo Integration** — Seamlessly blends 3D environments with 2D high-res real-world photography for educational purposes.

---

## 👥 Development Team (T3-7 Small Potatoes)

| Member | Student ID | Core Responsibilities |
|---|---|---|
| **Ho Tsun Wai** | 20238849 | Game Programming (C#), AI Chase System Engine, Core Gameplay Loop, G/F–4/F 3D Modelling |
| **Tang Pui Yin** | 20237812 | Level Design, 5/F–6/F 3D Modelling, Shared Prop Asset Creation |
| **Yeung Tsz Him** | 20237982 | Project Management, Asset Integration, 7/F–8/F 3D Modelling |
| **Yu Chun Hei** | 20238878 | Narrative & Concept Design, Documentation, 9/F–10/F 3D Modelling |

---

## 🔭 Future Scope

While the core FYP requirements have been met successfully, the technical roadmap for future iterations includes:
- **Unity Addressables Integration:** To further optimize scene loading and reduce memory overhead.
- **Multi-language Support:** Implementation of a localization system (English, Traditional Chinese, Simplified Chinese) for international students.
- **Expanded AI Behavior Trees:** Adding patrol, investigate, and ambush states to the monster AI to reduce predictability.
- **Official Deployment:** Exploring formal collaboration with HKU SPACE to deploy the executable on the school's internal orientation network.

---

## 📄 License
This educational project is open-sourced under the [MIT License](LICENSE). Note that the license applies to the structural code and documentation; real-world photos and campus architectural likenesses remain the property of HKU SPACE.
