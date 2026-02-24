# Roaming SPACE - HKU SPACE KEC Horror Game (FYP)

![Status](https://img.shields.io/badge/Status-Completed-success)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-blue)
![Engine](https://img.shields.io/badge/Engine-Unity-black)
![Modeling](https://img.shields.io/badge/Modeling-Blender-orange)

## 📖 Introduction
**Roaming SPACE** is a 3D first-person game developed as a Final Year Project (CCIT4080B) at HKU SPACE Community College. It uses the Kowloon East Campus (KEC) as a 1:1 scale map blueprint. The project aims to gamify the campus navigation experience, helping freshmen familiarize themselves with the KEC structure in an immersive and memorable way, replacing traditional, monotonous orientation methods.

## ⬇️ Download the Game (Playable Build)
Due to GitHub's file size limits, the complete playable build (approximately 7GB, including all 1:1 3D models, high-resolution textures, and audio assets) is hosted externally.

👉 **[Download Roaming SPACE (ZIP)](https://portland-my.sharepoint.com/:u:/g/personal/tsunwaiho6-c_my_cityu_edu_hk/IQB-77ERexq1R4pYpmJQbxc8Ac7-OAL4jcs0wKdPExZD5Ro?e=6GzXnT)**

*Note: Extract the ZIP file to your local drive and run the executable to play.*

## 🎮 Game Modes
The game features two distinct modes to cater to different player experiences:

### 1. Free Mode (Visit Mode)
- **Objective:** Freely explore the KEC campus without any time pressure or threats.
- **Features:** Navigate through different floors (G/F to 10/F). Interactive exclamation marks ("sightseeing spots") in rooms display real-life photos of the actual campus facilities, bridging the gap between the virtual model and the real-world environment.

### 2. Horror Mode
- **Objective:** Survive, solve puzzles, and save your GPA!
- **Story:** Players take on the role of a "Free-Rider" whose grades have been paused by the "GPA God" and "Offer God". You must find all the keys to reunite your body and soul.
- **Features:** Immersive horror atmosphere with eerie lighting, low visibility, and gloomy sound effects. The core mechanic involves answering questions or solving puzzles in classrooms. Failing to do so triggers an AI-controlled monster chase, where the monster's speed scales with the number of incorrect answers.

## ✨ Key Features & Technical Highlights
- **1:1 Campus Recreation:** A highly detailed 3D restoration of the HKU SPACE KEC (approximately 70-80% accuracy of accessible areas).
- **Scene Layering Architecture:** To optimize memory usage and loading times for a massive map, the campus is divided into independent scenes per floor, connected by teleportation scripts.
- **Dynamic AI Pathfinding:** The monster chase mechanism utilizes shortest-path tracking algorithms constrained within specific nav-mesh areas to ensure fair but challenging gameplay.
- **Atmospheric Rendering:** Custom lighting setups in Unity combined with spatial audio design to create a genuine psychological horror experience.

## 📚 Documentation
To understand the technical depth and development process of this project, please refer to the following documents:
- [Technical Architecture (`docs/TECHNICAL.md`)](docs/TECHNICAL.md) - Details on scene management, AI logic, and 3D modeling workflow.
- [Testing & Evaluation (`docs/TESTING.md`)](docs/TESTING.md) - QA processes, beta tester feedback, and performance metrics.
- [Build & Run Guide (`docs/BUILD_AND_RUN.md`)](docs/BUILD_AND_RUN.md) - Instructions for running the downloaded build.

## 🛠️ Technologies Used
- **Game Engine:** Unity (C#)
- **3D Modeling & Texturing:** Blender
- **Version Control:** Git & GitHub

## 👥 Development Team (T3-7 Small Potatoes)
- **Tang Pui Yin** - 5/F & 6/F modeling, 3D assets, Level Design
- **Ho Tsun Wai** - G/F to 4/F modeling, Lead Game Programming, AI Chase Mechanism, Core Systems
- **Yeung Tsz Him** - 7/F & 8/F modeling, Project Management, Asset Integration
- **Yu Chun Hei** - 9/F & 10/F modeling, Story Conceptualization, Technical Documentation

*Special thanks to all beta testers and HKU SPACE students who provided valuable feedback during development!*

## 🚀 Future Scope
- Implementation of Unity Addressables for seamless, loading-screen-free floor transitions.
- Multi-language localization support (English, Traditional Chinese, Simplified Chinese).
- Expansion of the AI behavior tree to include unpredictable patrol routes and hiding mechanics.
- Integration into the official HKU SPACE orientation program.