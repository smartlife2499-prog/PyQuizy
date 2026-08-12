# 🐍 PyQuizy

**Interactive Python quiz app** with **500+ questions** across **10 topics**.

Mark questions as done, expand answers, copy questions, and your progress is saved locally (SQLite).

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![Flet](https://img.shields.io/badge/Flet-UI-blue)
![License](https://img.shields.io/badge/License-MIT-green)

---

## Features

- 10 topics × 50 questions each
- Real code / command questions with syntax highlighting
- Progress tracking (checkboxes) persisted in SQLite
- Copy question button
- Expandable “Show Answer” tiles
- Works as desktop, web, or Android app
- Clean navigation with proper Android back-button support

### Topics

1. Python Fundamentals and Setup  
2. Python Basics and Syntax  
3. Operators and Expressions  
4. Control Flow and Loops  
5. Data Structures and Collections  
6. Functions and Modular Code  
7. Error Handling and Exceptions  
8. File I/O and Working with Files  
9. Object Oriented Programming (OOP)  
10. Iterators, Generators, and Advanced Functions  
11. Regular Expressions and String Processing  
12. Working with External Libraries and APIs  
13. Concurrency and Parallelism  

*(Some topics may be slightly over/under 50 depending on the data set.)*

---

## Project structure

```
PyQuizy/
├── main.py                 # Full application source
├── assets/
│   └── logo.png            # App icon (window / favicon / adaptive)
├── pyproject.toml          # Project metadata + Flet build settings
├── requirements.txt        # Minimal dependency list
├── .github/
│   └── workflows/
│       ├── build.yml               # Multi-platform builds
│       └── build-apk-simple.yml    # Simple APK-only workflow
├── .gitignore
└── README.md
```

---

## Quick start (local development)

```bash
# 1. Clone
git clone https://github.com/YOUR_USERNAME/PyQuizy.git
cd PyQuizy

# 2. Create virtual environment (recommended)
python -m venv .venv
source .venv/bin/activate      # Windows: .venv\Scripts\activate

# 3. Install
pip install -r requirements.txt
# or
pip install "flet[all]"

# 4. Run
flet run main.py
# or
python main.py
```

The app window should open. Progress is stored in `pyquizy_progress.db` next to `main.py`.

---

## Building packages (local)

You need the Flet CLI and (for mobile/desktop) Flutter tooling.

```bash
# Install Flet with all extras
pip install "flet[all]"

# Android APK
flet build apk

# Android App Bundle (for Play Store)
flet build aab

# Windows
flet build windows

# macOS
flet build macos

# Linux
flet build linux

# Web (static site)
flet build web
```

Output appears under the `build/` directory.

---

## GitHub Actions – automated builds

Two workflows are included:

| Workflow | What it builds | When it runs |
|----------|----------------|--------------|
| `build.yml` | Linux, macOS, Windows, APK, AAB, Web | Push / PR / manual |
| `build-apk-simple.yml` | APK only (official Flet action) | Manual or version tags |

### How to use

1. Create a new repository on GitHub.
2. Push this whole folder:
   ```bash
   git init
   git add .
   git commit -m "Initial commit – PyQuizy"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/PyQuizy.git
   git push -u origin main
   ```
3. Go to the **Actions** tab of your repository.
4. Select **Build PyQuizy** → **Run workflow**.
5. When finished, download the artifacts (zip files for each platform).

> **Note:** First runs can take 10–30 minutes because Flutter / Android SDK are downloaded and cached.

---

## App icon

`assets/logo.png` is used as:

- Desktop window / taskbar icon
- Browser favicon (web)
- Android adaptive icon base

You can replace it with any square PNG (recommended 512×512 or larger).  
Background color for Android adaptive icons is set in `pyproject.toml` (`#FFD43B` – Python yellow).

---

## Customization

- **Add / edit questions** → edit the big `QUIZ_DATA` dictionary in `main.py`.
- **Change window size / theme** → look at the top of `main()`.
- **App name / org / version** → edit `pyproject.toml`.
- **Build number** → automatically set by GitHub Actions run number, or pass `--build-number` to `flet build`.

---

## License

MIT – feel free to use, modify, and distribute.

---

Made with ❤️ and Flet for Python learners.
