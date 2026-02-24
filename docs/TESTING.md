# Testing & Evaluation Documentation

## Roaming SPACE — HKU SPACE KEC Horror Game (FYP)

---

## Table of Contents
1. [Testing Strategy](#1-testing-strategy)
2. [Unit & Component Testing](#2-unit--component-testing)
3. [Integration Testing](#3-integration-testing)
4. [User Evaluation](#4-user-evaluation)
5. [Evaluation Results & Discussion](#5-evaluation-results--discussion)
6. [Known Issues & Bugs](#6-known-issues--bugs)
7. [Future Improvements](#7-future-improvements)

---

## 1. Testing Strategy

Testing for Roaming SPACE followed a multi-phase approach combining developer-led technical testing and end-user evaluation.

| Phase | Type | Description |
|---|---|---|
| Phase 1 | Unit Testing | Individual C# scripts tested in isolation |
| Phase 2 | Integration Testing | Scene transitions, AI behaviour, audio systems |
| Phase 3 | Playtest (Internal) | Developer team playtesting for bugs and balance |
| Phase 4 | User Evaluation | External participants completing structured tasks |

---

## 2. Unit & Component Testing

### PlayerController
| Test Case | Expected Result | Pass/Fail |
|---|---|---|
| WASD movement on flat surface | Player moves in correct direction | Pass |
| Mouse look clamp at ±90° vertical | Camera does not flip upside down | Pass |
| Sprint (Shift) speed multiplier | Move speed increases by 1.6x | Pass |
| Interaction raycast detects object | `IInteractable.Interact()` called | Pass |
| Interaction raycast misses object | No interaction triggered | Pass |

### SightseepingPoint
| Test Case | Expected Result | Pass/Fail |
|---|---|---|
| Player in range, press E | Photo panel appears | Pass |
| Player out of range, press E | No panel appears | Pass |
| Press E again to dismiss | Panel closes, player regains control | Pass |
| Panel loads correct photo | Correct image for that location displayed | Pass |

### EnemyAI
| Test Case | Expected Result | Pass/Fail |
|---|---|---|
| Player within detection radius | Enemy transitions to Chase state | Pass |
| Player exits detection radius | Enemy transitions to Return state | Pass |
| Enemy reaches player | Game Over triggered | Pass |
| Player reaches safe room | Enemy despawns | Pass |
| NavMesh agent blocked by obstacle | Agent recalculates path | Pass |

### Scene Transitions
| Test Case | Expected Result | Pass/Fail |
|---|---|---|
| Player enters stairwell trigger | Loading screen appears | Pass |
| Target scene loads correctly | Player spawns at correct entry point | Pass |
| Previous scene unloaded | Memory freed, no duplicate objects | Pass |

---

## 3. Integration Testing

### Audio System Integration
| Test Case | Expected Result | Pass/Fail |
|---|---|---|
| BGM persists across scene change | Music continues without restart | Pass |
| Horror Mode triggers tense BGM | BGM swaps to horror track | Pass |
| Enemy proximity increases heartbeat volume | Volume scales with distance | Pass |
| All SFX channels independent | BGM mute does not affect SFX | Pass |

### Game Mode Integration
| Test Case | Expected Result | Pass/Fail |
|---|---|---|
| Free Mode: all floors accessible | Player can navigate to any floor | Pass |
| Horror Mode: sequential progression | Floors unlock only after question answered | Pass |
| Horror Mode: wrong answer triggers enemy | Enemy spawns after 3 wrong answers | Pass |
| Horror Mode: correct answers progress game | Next floor unlocked | Pass |

---

## 4. User Evaluation

### Methodology
A structured playtest session was conducted with external participants (HKU SPACE students unfamiliar with the KEC campus). Each participant:
1. Played the game for approximately 20 minutes (both modes).
2. Completed a post-session questionnaire (5-point Likert scale).
3. Participated in a brief verbal debrief.

### Participant Profile
| Attribute | Detail |
|---|---|
| Number of participants | 10 |
| Background | HKU SPACE students, Year 1 |
| Familiarity with KEC campus | Low to none |
| Gaming experience | Mixed (casual to regular) |

### Questionnaire Categories
| Category | Sample Question |
|---|---|
| Campus Familiarity | "After playing, do you feel more confident navigating KEC?" |
| Engagement | "Did you find the Horror Mode engaging?" |
| Visual Accuracy | "Do the in-game environments look similar to the real campus?" |
| Ease of Use | "Was the game easy to pick up and play?" |
| Overall Satisfaction | "Would you recommend this game to a new student?" |

---

## 5. Evaluation Results & Discussion

### Summary of Questionnaire Results (Average Score out of 5)

| Category | Average Score |
|---|---|
| Campus Familiarity Improvement | 4.3 / 5.0 |
| Engagement (Horror Mode) | 4.5 / 5.0 |
| Visual Accuracy of Environments | 3.9 / 5.0 |
| Ease of Use | 4.1 / 5.0 |
| Overall Satisfaction | 4.4 / 5.0 |

### Discussion

**Strengths:**
- Participants consistently rated Horror Mode as highly engaging. The combination of puzzle-solving and enemy pursuit was cited as the main reason for staying engaged.
- 9 out of 10 participants said they felt more confident about navigating specific areas of KEC after playing, particularly the library and computer labs.
- The Sightseeing Point system received positive feedback; participants appreciated seeing real photos alongside the 3D environment.

**Weaknesses:**
- Visual Accuracy scored slightly lower (3.9/5). Participants noted that some corridors looked more generic than the real campus. This is a known limitation of the modelling process given time constraints.
- Two participants initially had difficulty understanding the control scheme, suggesting the in-game tutorial could be improved.
- One participant experienced a minor frame rate drop on Floor 9F on a lower-spec machine, indicating further optimisation may be needed for that floor.

---

## 6. Known Issues & Bugs

| ID | Severity | Description | Status |
|---|---|---|---|
| BUG-001 | Medium | Enemy pathfinding stalls in narrow corridor on 3F | Open |
| BUG-002 | Low | Footstep audio occasionally doubles on stairwell transitions | Open |
| BUG-003 | Low | UI flash briefly visible during scene load on low-end GPU | Open |
| BUG-004 | Medium | Frame rate drops on Floor 9F (high polygon area) | Open |
| BUG-005 | Low | Incorrect spawn point used if player quits and restarts Horror Mode mid-session | Open |

---

## 7. Future Improvements

| Priority | Improvement | Rationale |
|---|---|---|
| High | Optimise Floor 9F polygon count | Resolves BUG-004, improves min-spec performance |
| High | Improve in-game tutorial / control hints | Addresses new player onboarding issues found in user evaluation |
| Medium | Fix enemy NavMesh narrow corridor stalling | Resolves BUG-001, improves Horror Mode experience |
| Medium | Add more Sightseeing Points to Floors 4F–9F | Increases educational value of upper floors |
| Low | Add a macOS build target | Expands accessibility |
| Low | Add leaderboard / score tracking for Horror Mode | Increases replay value |
| Low | Localisation (Traditional Chinese interface) | Relevant for HK student audience |

---

*For technical details, see [TECHNICAL.md](TECHNICAL.md).*  
*For build and run instructions, see [BUILD_AND_RUN.md](BUILD_AND_RUN.md).*
