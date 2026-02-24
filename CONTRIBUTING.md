# Contributing to Roaming SPACE

Thank you for your interest in contributing to **Roaming SPACE — HKU SPACE KEC Horror Game (FYP)**!

This project was developed as a Final Year Project (CCIT4080B) at HKU SPACE Community College. While the core development phase is complete, we welcome feedback, bug reports, and suggestions for future improvements.

---

## How to Contribute

### 1. Reporting Bugs

If you find a bug while playing the game:
1. Go to the [Issues](https://github.com/iamfinethanks123/hkuspace-horror-game-fyp/issues) tab.
2. Click **New Issue**.
3. Use the following template:

```
**Bug Description:**
A clear description of what the bug is.

**Steps to Reproduce:**
1. Go to...
2. Do...
3. See error...

**Expected Behaviour:**
What you expected to happen.

**Actual Behaviour:**
What actually happened.

**System Specs:**
- OS: (e.g., Windows 10)
- GPU: (e.g., NVIDIA GTX 1060)
- RAM: (e.g., 16 GB)

**Screenshots (if applicable):**
Attach any screenshots here.
```

### 2. Suggesting Improvements

Have an idea to make the game better? Open an issue with the label `enhancement` and describe:
- What the improvement is.
- Why it would benefit players.
- Any relevant examples or references.

### 3. Contributing Code

If you would like to contribute code changes:

1. **Fork** this repository.
2. **Clone** your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/hkuspace-horror-game-fyp.git
   ```
3. Create a **new branch** for your feature or fix:
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. Make your changes in Unity (C# scripts, scene adjustments, etc.).
5. **Commit** with a clear message:
   ```bash
   git commit -m "Add: brief description of your change"
   ```
6. **Push** to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```
7. Open a **Pull Request** against the `main` branch of this repository.

---

## Code Style Guidelines

| Rule | Detail |
|---|---|
| Language | C# (Unity scripting) |
| Naming | PascalCase for classes and methods; camelCase for variables |
| Comments | XML doc comments for public methods |
| Scene changes | One scene per floor; do not merge floor scenes |
| Assets | Place new assets in the correct `Assets/` subdirectory |
| `.gitignore` | Never commit `Library/`, `Temp/`, `Logs/`, or build outputs |

---

## Commit Message Format

Please follow this format for commit messages:

```
<Type>: <Short description>

[Optional: longer description]
```

**Types:**
- `Add` — New feature or file
- `Fix` — Bug fix
- `Update` — Change to existing feature
- `Remove` — Deletion of file or feature
- `Docs` — Documentation only changes
- `Refactor` — Code restructure without behaviour change

**Examples:**
```
Add: SightseepingPoint component for Floor 4F
Fix: Enemy AI stalling in 3F narrow corridor
Docs: Update TECHNICAL.md with audio system details
```

---

## Contact

For questions or collaboration inquiries, please open an issue on this repository.

---

*HKU SPACE Community College — T3-7 Small Potatoes — FYP CCIT4080B*
