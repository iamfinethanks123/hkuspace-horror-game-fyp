# Technical Documentation

## Roaming SPACE — HKU SPACE KEC Horror Game (FYP)

---

## Table of Contents
1. [System Architecture Overview](#1-system-architecture-overview)
2. [Scene Management & Floor Design](#2-scene-management--floor-design)
3. [Player Controller](#3-player-controller)
4. [Sightseeing Point System](#4-sightseeing-point-system)
5. [Horror Mode & AI Enemy System](#5-horror-mode--ai-enemy-system)
6. [Audio System](#6-audio-system)
7. [UI & Game Flow](#7-ui--game-flow)
8. [Performance Optimisation](#8-performance-optimisation)
9. [Known Limitations](#9-known-limitations)

---

## 1. System Architecture Overview

Roaming SPACE is built on the **Unity game engine** using **C#** as the primary scripting language. The project follows a scene-based architecture where each floor of the KEC campus is represented as an independent Unity Scene.

```
Game Entry
    └── Main Menu Scene
          ├── [Free Mode] → Floor Selection UI → Load Floor Scene
          └── [Horror Mode] → Ground Floor Scene → Sequential Floor Progression

Floor Scenes (Independent)
    ├── GroundFloor.unity
    ├── 1F.unity
    ├── 2F.unity
    ├── 3F.unity
    ├── 4F.unity
    ├── 5F.unity
    ├── 6F.unity
    ├── 7F.unity
    ├── 8F.unity
    ├── 9F.unity
    └── 10F.unity
```

### Core Systems
| System | Description |
|---|---|
| SceneManager | Handles async scene loading and transitions between floors |
| PlayerController | First-person movement, interaction, and camera control |
| SightseepingPoint | Triggers real photo display at landmark locations |
| EnemyAI | NavMesh-based pathfinding and pursuit logic |
| GameManager | Global state management (mode, score, health) |
| AudioManager | Singleton audio controller for BGM and SFX |
| UIManager | HUD, menus, and popup management |

---

## 2. Scene Management & Floor Design

### Why Separate Scenes Per Floor?
Loading every floor as a single scene would require all 3D models, textures, and assets (~7.9 GB) to be in memory simultaneously, which would cause crashes on mid-range hardware. Splitting into scenes ensures:
- Only one floor's assets are loaded at a time.
- Smooth performance on the minimum hardware spec (GTX 1060, 8GB RAM).
- Independent development and testing of each floor.

### Floor Transition System
Each floor contains **Teleport Trigger Zones** placed at stairwells and elevators. When the player enters a trigger zone:
1. A loading screen is displayed.
2. The current scene is unloaded asynchronously (`SceneManager.UnloadSceneAsync`).
3. The target floor scene is loaded asynchronously (`SceneManager.LoadSceneAsync`).
4. The player's spawn position is set to the corresponding entry point of the new floor.

### 3D Modelling Approach
- All campus environments were modelled in **Blender** using reference photographs and architectural floor plans collected from on-site visits.
- Models were exported as `.fbx` files and imported into Unity.
- Modular design was used where possible (e.g., reusable corridor segments, door frames) to reduce total polygon count.

---

## 3. Player Controller

The player uses a standard **First-Person Controller** built from scratch in C#:

| Feature | Implementation |
|---|---|
| Movement | `CharacterController.Move()` with WASD input |
| Camera Look | Mouse delta mapped to camera X/Y rotation with clamping |
| Interaction | Raycast from camera center, max range 3 units, detects `IInteractable` interface |
| Sprinting | Shift key multiplies move speed by 1.6x |
| Footstep Audio | Step triggered every N units walked, random clip from pool |

---

## 4. Sightseeing Point System

This is one of the key educational features of the game.

### How It Works
1. Specific landmark locations on each floor contain a **SightseepingPoint** component.
2. When the player approaches and presses `E`, a full-screen UI panel appears.
3. The panel displays a **real photograph** of that exact location taken on-site.
4. A brief description of the location is shown (e.g., "This is the 3F Computer Lab — Room 301").
5. The player presses `E` again or clicks to dismiss the panel and resume exploration.

### Educational Goal
By pairing the 3D virtual reconstruction with real photos, players build a mental model that transfers to the real campus. Studies on spatial memory suggest that dual-coding (virtual + photographic) improves recall compared to maps alone.

---

## 5. Horror Mode & AI Enemy System

### Game Loop
```
Start Horror Mode
    └── Player must find and answer questions on each floor
          ├── Correct Answer → Proceed to next floor
          └── Wrong Answer (3 strikes) → Enemy Spawns
                ├── Enemy pursues player via NavMesh
                ├── Player caught → Jump scare + Game Over screen
                └── Player reaches safe room → Enemy despawns, continue
```

### AI Enemy Design
| Property | Detail |
|---|---|
| Navigation | Unity NavMesh Agent with baked navigation mesh per floor |
| Detection | Sphere overlap check radius 15 units; line-of-sight raycast |
| Chase Speed | 4.5 m/s (player walk: 3.0 m/s, sprint: 4.8 m/s) |
| State Machine | Idle → Patrol → Alert → Chase → Return |
| Audio Cue | Heartbeat SFX increases frequency as enemy gets closer |
| Lighting | Flicker shader applied to lights near enemy position |

### Difficulty Considerations
- The enemy is slightly slower than a sprinting player to ensure the game is escapable.
- Safe rooms are distributed every 2–3 corridors to prevent frustration.
- Horror elements are kept atmospheric rather than relying solely on jump scares.

---

## 6. Audio System

Audio is managed by a singleton **AudioManager** that persists across scene loads.

| Category | Details |
|---|---|
| Background Music | Looping ambient track per mode (calm for Free Mode, tense for Horror Mode) |
| SFX | Footsteps, door opens, UI clicks, jump scare stings |
| Enemy Audio | Proximity-based heartbeat using `AudioSource` volume curve |
| Mixer | Unity Audio Mixer with Master, BGM, and SFX groups for independent volume control |

---

## 7. UI & Game Flow

| Screen | Purpose |
|---|---|
| Main Menu | Mode selection, settings, credits |
| Floor Selection (Free Mode) | Grid of floor thumbnails, click to load |
| HUD | Minimal: current floor indicator, interaction prompt |
| Sightseeing Panel | Full-screen photo + description overlay |
| Question Panel (Horror Mode) | Multiple-choice question with timer |
| Game Over Screen | Cause of death, retry option |
| Pause Menu | Resume, settings, quit |

---

## 8. Performance Optimisation

| Technique | Details |
|---|---|
| Scene Splitting | One scene per floor; only active floor is in memory |
| Occlusion Culling | Unity's built-in occlusion culling baked for each floor |
| LOD (Level of Detail) | Distant objects swap to lower-poly versions |
| Texture Compression | All textures compressed to DXT1/DXT5 format |
| Static Batching | Non-moving environment meshes batched to reduce draw calls |
| Audio Compression | BGM as Vorbis streaming; SFX as compressed in-memory clips |

---

## 9. Known Limitations

| Issue | Notes |
|---|---|
| Floors 4F–9F not in repo | Too large for GitHub; included in the downloadable ZIP |
| NavMesh on complex geometry | Some narrow corridors may cause enemy pathfinding to stall |
| No multiplayer | Single-player only; multiplayer was out of scope for FYP |
| macOS build not tested | Primary target is Windows PC; macOS compatibility unverified |
| Mobile not supported | Scene complexity exceeds mobile GPU capabilities |

---

*For build and run instructions, see [BUILD_AND_RUN.md](BUILD_AND_RUN.md).*  
*For testing and evaluation details, see [TESTING.md](TESTING.md).*
