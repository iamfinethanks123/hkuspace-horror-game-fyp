# Build & Run Guide

## Roaming SPACE — HKU SPACE KEC Horror Game (FYP)

---

## Table of Contents
1. [System Requirements](#1-system-requirements)
2. [Download the Game](#2-download-the-game)
3. [Running on Windows](#3-running-on-windows)
4. [Controls](#4-controls)
5. [Game Modes Quick Start](#5-game-modes-quick-start)
6. [Troubleshooting](#6-troubleshooting)
7. [For Developers (Running from Source)](#7-for-developers-running-from-source)

---

## 1. System Requirements

### Minimum
| Component | Requirement |
|---|---|
| OS | Windows 10 (64-bit) |
| CPU | Intel Core i5 / AMD Ryzen 5 (4 cores) |
| RAM | 8 GB |
| GPU | NVIDIA GeForce GTX 1060 / AMD RX 580 (4 GB VRAM) |
| Storage | 10 GB free disk space |
| DirectX | Version 11 |

### Recommended
| Component | Requirement |
|---|---|
| OS | Windows 10 / 11 (64-bit) |
| CPU | Intel Core i7 / AMD Ryzen 7 |
| RAM | 16 GB |
| GPU | NVIDIA GeForce RTX 2060 or above (8 GB VRAM) |
| Storage | 15 GB free disk space (SSD preferred) |
| DirectX | Version 12 |

> **Note:** macOS is not officially supported. The game has not been tested on macOS or Linux.

---

## 2. Download the Game

1. Click the download link below to access the game build:

   **[⬇️ Download Roaming SPACE (ZIP, ~7GB)](https://portland-my.sharepoint.com/:u:/g/personal/tsunwaiho6-c_my_cityu_edu_hk/IQB-77ERexq1R4pYpmJQbxc8Ac7-OAL4jcs0wKdPExZD5Ro?e=6GzXnT)**

2. You may be prompted to sign in with a Microsoft account. If access is restricted, contact the project team.

3. Click **Download** to save the ZIP file to your computer.

> **Important:** The ZIP file is approximately 7 GB. Ensure you have a stable internet connection and sufficient free storage before downloading.

---

## 3. Running on Windows

### Step 1: Extract the ZIP
1. Locate the downloaded `game.zip` file (usually in your `Downloads` folder).
2. Right-click the file and select **Extract All...**
3. Choose a destination folder (e.g., `C:\Games\RoamingSPACE\`) and click **Extract**.
4. Wait for the extraction to complete (may take several minutes).

### Step 2: Launch the Game
1. Open the extracted folder.
2. Double-click **`RoamingSPACE.exe`** to launch the game.
3. If Windows Defender SmartScreen appears, click **More info** → **Run anyway**.
   - This is expected for unsigned indie game builds.
4. The main menu will appear after a brief loading screen.

### Step 3: Configure Settings (Optional)
- On the main menu, click **Settings** to adjust:
  - Screen resolution
  - Graphics quality (Low / Medium / High)
  - Master / BGM / SFX volume
  - Mouse sensitivity

---

## 4. Controls

| Action | Key / Input |
|---|---|
| Move Forward | `W` |
| Move Backward | `S` |
| Move Left | `A` |
| Move Right | `D` |
| Look Around | Mouse |
| Sprint | Hold `Shift` |
| Interact / Confirm | `E` |
| Pause Menu | `Escape` |
| Close UI Panel | `E` or click |

---

## 5. Game Modes Quick Start

### Free Mode (Visit Mode)
1. From the main menu, select **Free Mode**.
2. A floor selection screen appears — click any floor to load it.
3. Explore freely. Look for glowing **Sightseeing Points** and press `E` to view real campus photos.
4. Use stairwells or elevators to move between floors.
5. Press `Escape` at any time to return to the menu.

### Horror Mode
1. From the main menu, select **Horror Mode**.
2. The game starts at the **Ground Floor**.
3. Explore the floor to find the **Question Terminal**.
4. Answer the question correctly to unlock the next floor.
5. If you answer incorrectly **3 times**, an enemy will spawn and chase you.
   - **Sprint** (`Shift`) to escape.
   - Reach a **Safe Room** (marked with a green light) to despawn the enemy.
6. Complete all floors to finish the game.

---

## 6. Troubleshooting

### Game does not start
- Ensure your GPU drivers are up to date.
- Verify that DirectX 11 or later is installed.
- Try running `RoamingSPACE.exe` as Administrator (right-click → **Run as administrator**).

### Low frame rate / stuttering
- Lower the graphics quality in **Settings** → **Graphics Quality**.
- Close background applications to free up RAM.
- If playing on a laptop, ensure it is plugged in and using the **High Performance** power plan.
- Floor 9F is the most demanding floor; frame rate drops here are a known issue.

### Black screen on startup
- Press `Alt + Enter` to toggle fullscreen/windowed mode.
- Try changing the screen resolution in the Settings menu.

### Game crashes during floor transition
- Ensure you have at least 10 GB of free disk space.
- Close other applications to free up RAM before loading a new floor.

### Audio not working
- Check that your system audio is not muted.
- In-game, go to **Settings** → **Audio** and ensure Master Volume is above 0.

### Cannot interact with objects
- Ensure you are close enough to the object (within ~3 metres in-game).
- Look directly at the object and press `E`.

---

## 7. For Developers (Running from Source)

If you are a developer and want to open the project in Unity:

### Prerequisites
- **Unity Editor** version 2021.3 LTS or later (recommended: 2022.3 LTS)
- **Blender** 3.x or later (for viewing/editing 3D models)
- **Git** (for version control)

### Steps
1. Clone this repository:
   ```bash
   git clone https://github.com/iamfinethanks123/hkuspace-horror-game-fyp.git
   ```
2. Download the full project assets from the [external download link](https://portland-my.sharepoint.com/:u:/g/personal/tsunwaiho6-c_my_cityu_edu_hk/IQB-77ERexq1R4pYpmJQbxc8Ac7-OAL4jcs0wKdPExZD5Ro?e=6GzXnT) and extract into the project folder.
3. Open **Unity Hub**, click **Add**, and select the project folder.
4. Open the project in Unity (first load may take several minutes to import assets).
5. Open the `MainMenu` scene from `Assets/Scenes/` to start from the beginning.

> **Note:** The `Library/` and `Temp/` folders are excluded from this repository via `.gitignore`. Unity will regenerate them automatically on first open.

---

*For technical architecture details, see [TECHNICAL.md](TECHNICAL.md).*  
*For testing and evaluation details, see [TESTING.md](TESTING.md).*
