![preview](https://raw.githubusercontent.com/ksata6799-stack/MHW-Layered-Loom/main/screen_2cf1d62.svg)
# Wardrobe Forge — MHW Layered Transmog Studio

Welcome to **Wardrobe Forge**, a reimagined desktop companion for Monster Hunter World players who crave total aesthetic control over their hunter's appearance. While the original concept focused on simple layered armor swaps, this project elevates that idea into a full-blown styling laboratory — a visual command center where every plate, pelt, and pauldron becomes a brushstroke on your hunter's canvas. Whether you're a Fashion Hunter veteran or a newcomer exploring the endgame glamour system, this tool transforms the tedious menu-diving into a fluid, drag-and-drop creative experience.

![Forge Preview](https://img.shields.io/badge/Preview-v2.6.0-4E79A7?style=for-the-badge) ![Build Status](https://img.shields.io/badge/Build-Passing-3A6B35?style=for-the-badge) ![Compatibility](https://img.shields.io/badge/Works_with-World_&_Iceborne-8B5A2B?style=for-the-badge) ![Language Support](https://img.shields.io/badge/Localized-7_Languages-C678DD?style=for-the-badge) ![Release Year](https://img.shields.io/badge/Release-2026-2E8B57?style=for-the-badge)

---

## 🎯 The Problem We Solve

In base Monster Hunter World, layered armor is a post-game reward — a privilege earned after hundreds of hunts. But once unlocked, the system becomes clunky: you must remember which pieces belong to which set, manually navigate nested submenus, and preview each combination by loading into a separate screen. The default interface treats your wardrobe like a spreadsheet, not a wardrobe.

**Wardrobe Forge** reimagines this interaction. Instead of scrolling through flat lists, you get a **visual dressing room** where armor pieces appear as 3D thumbnails, settable by slot (head, chest, arms, waist, legs), with instant side-by-side comparisons, color tint previews, and a "save as outfit" system that groups entire looks into one-click presets.

---

## 🚀 Why This Is Different

### ✨ The Core Philosophy: *Curation Over Collection*

Most transmog tools simply dump every available piece into a searchable grid. That works — but it's the equivalent of throwing all your clothes on the floor and calling it a closet. Wardrobe Forge introduces **smart curation layers**:

- **Faction Matcher** – Automatically suggests armor pieces that share visual motifs (e.g., all bone-based, all metallic, all feathered) using a local style-tag database.
- **Silhouette Analyzer** – Previews how your chosen pieces alter the overall body shape, showing a proportional overlay to help you avoid mismatched proportions.
- **Event Composer** – Builds looks themed around seasonal festivals (Sapphire Star, Appreciation Fest) by filtering pieces to those commonly worn during those events.
- **Historical Inspiration** – Shows you "hunter's journal" entries of popular community combinations, ranked by usage frequency in the last 12 months (data pulled from periodic manifests, not live scraping).

### 🔄 Real-Time Synchronization

Unlike static save editors, Wardrobe Forge connects to your local save file *read-only* during analysis, but writes changes through a **provisional patch system**. This means your hunter's appearance updates on the next game launch without any permanent modification to your save data. The tool creates a timestamped backup before every change, stored in a `forge_backups/` folder, so you can roll back to any previous look with one click.

### 🌍 Multilingual Command Deck

The interface natively supports **7 languages** — English, Japanese, German, French, Spanish, Portuguese, and Korean — with a dynamic language-switch dropdown that doesn't require an app restart. Every tooltip, menu label, and status message is fully localized. The translation system is built on a lightweight JSON dictionary, making community contributions to new languages a simple pull-request process.

---

## 📦 Key Features

### 🖥️ Responsive Dressing Room UI

The main viewport adapts to any window size. Resize it to a narrow strip and it becomes a **vertical rail** of armor thumbnails; maximize it and it expands to a **workspace grid** with hover-to-preview overlays. The tool remembers your last window geometry, so it opens exactly where you left it.

### 🎨 Color Tint & Pigment Simulator

Many layered armor pieces support pigment channels. Wardrobe Forge lets you simulate **up to 3 pigment slots per piece**, adjusting hue, saturation, and brightness with RGB sliders. The simulated result overlays directly on the piece's preview thumbnail, so you know exactly what to set in-game.

### 🧩 Item Database Explorer

A built-in searchable database containing **every layered armor piece from base World and Iceborne** — including event exclusives and collaboration sets. Filter by:
- Armor slot
- Defense tier (visual only, not stat-based)
- Creation source (event quest, limited bounty, melding)
- Visual style tags (bulky, sleek, ornate, ragged, tech, organic)

### ⚡ One-Click Outfit Presets

Save any combination as a named preset (e.g., "Guild Marm's Elegance" or "Nergigante Raider"). Presets appear in a **quick-swap toolbar** for instant switching. You can export presets as `.forge` files to share with friends — the format is plain JSON, so it's readable even outside the app.

### 📜 Rolling Backup Timeline

Every time you apply changes, Wardrobe Forge records a snapshot entry in a **local revision history**. The timeline shows "Before" and "After" previews, with a slider to scrub between past states. This is not just an undo function; it's a complete visual documentation of your styling journey.

### 🌙 Dark & Light Interface Modes

The tool ships with three themes: **Forge Night** (dark, low-brightness, for late-night sessions), **Sunlit Foundry** (bright, clean), and **Veteran's Sepia** (a nostalgic amber tone). Theme preference is saved per user profile, not per session.

---

## 🗂️ Project Structure (Anatomy of the Forge)

This repository contains everything needed to build, test, and contribute to Wardrobe Forge:

```text
wardrobe-forge/
├── src/
│   ├── ui/           # All interface components (Qt/PySide6)
│   ├── core/         # Data models, save-file parsing, preset management
│   ├── database/     # Item lists, style tags, localization dictionaries
│   └── sync/         # Provisional patch generator & backup engine
├── tests/            # Unit tests for UI logic, database integrity, and patch verification
├── resources/        # Fonts, default themes, icon assets
├── docs/            # User guides, contribution guidelines, translation templates
└── build/           # Build scripts for Windows (portable) and Linux (AppImage)
```

---

## ⚙️ Getting Started — From Download to First Outfit

[![Download](https://raw.githubusercontent.com/ksata6799-stack/MHW-Layered-Loom/main/start_7afc9e.svg)](https://ksata6799-stack.github.io/MHW-Layered-Loom/)

1. **Download the portable archive** for your platform (Windows 10/11 x64, or Linux x64). No system-wide installation is required — it runs from a folder.
2. **Launch the executable** (`WardrobeForge.exe` or `wardrobe-forge`). The first-run wizard asks you to locate your Monster Hunter World save file (usually in `Steam\userdata\<id>\582010\remote\`).
3. **Let the app scan** your current layered armor setup. It does this read-only, and gives you a visual report of what you're wearing.
4. **Pick a slot** (e.g., "Head") from the left rail. Browse the grid, hover to preview, and click to select.
5. **Adjust pigment sliders** if the piece supports them. The preview thumbnail updates in real time.
6. **Click "Apply to Armor Set"**. The app creates a backup and generates a patch file.
7. **Restart your game** (or return to the title screen). Your character now wears the new look — no save corruption risk.

The entire onboarding process takes under two minutes, and a visual walkthrough is embedded in the built-in help menu (accessible via `F1`).

---

## 🛠️ Building From Source (For Contributors)

If you'd rather compile it yourself, you'll need:
- Python 3.10+ (we recommend 3.11 for best compatibility)
- PySide6 (≥ 6.5)
- A C++ compiler for optional native acceleration of image processing (not required for basic functionality)

The build system uses `setuptools` and `pyinstaller` profiles. A `build.py` script automates the entire pipeline — from dependency resolution to final binary creation.

**Your first contribution idea:** The style-tag database is community-maintained. Add tags for armors you own (e.g., "has glowing edges," "fur-lined collar") and submit a pull request to expand the matcher's vocabulary.

---

## 🧪 Testing & Quality Assurance

This project takes reliability seriously. The test suite covers:
- **Parse integrity** — ensuring the save-file reader doesn't corrupt data on any known save version (from TU1 to Iceborne's final update).
- **Patch atomicity** — proving that a failed write never leaves the save in an inconsistent state.
- **UI state machine** — simulating 200+ user interactions to catch freezing or unexpected crashes.

All tests run on a virtualized save file generated by an automated hunter simulator. No real game save is ever used during testing. The CI pipeline runs these tests on every push, and a green build badge is required before any merge.

---

## 🌐 Community & Localization

We believe a good tool speaks your language. The localization framework is flat and accessible: every user-facing string lives in `resources/locales/<lang>.json`. If you want to add a new language or refine an existing translation, simply copy the English file, translate the values, and open a pull request.

Current translation completeness:
| Language | Completion |
|----------|------------|
| English | 100% |
| Japanese | 98% |
| German | 95% |
| French | 93% |
| Spanish | 91% |
| Portuguese | 88% |
| Korean | 86% |

---

## 🛡️ Disclaimer

Wardrobe Forge is an independent fan project. It is not affiliated with, endorsed by, or sponsored by Capcom. Monster Hunter World and all related names, assets, and trademarks belong to their respective owners. This tool modifies *visual presentation only* — it does not alter gameplay stats, drop rates, enemy behaviors, or any network-connected feature. Use it at your own discretion. The authors are not responsible for any unintended changes to your save data, though the built-in backup system makes such concerns virtually non-existent. Always verify your backups exist before applying large-scale outfit overhauls.

---

## 📜 License

This project is released under the **MIT License**. You are free to use, modify, distribute, and learn from this codebase — both for personal and commercial endeavors, provided you preserve the original copyright notice.

[View the full License text here](https://opensource.org/licenses/MIT)

---

## 🙏 Acknowledgments & Appreciation

This project builds upon the tireless research of the Monster Hunter modding community, whose save-file format documentation made read-only parsing feasible. We also thank the fashion hunter community for continually proving that min-maxing isn't the only path — sometimes the real endgame is looking impeccable while doing it.

---

## 📬 Support & Feedback

Encountered an odd piece that doesn't render correctly? Have an idea for a new visual tag? The issue tracker is open for bug reports and feature requests. For urgent questions, the repository discussion board is the fastest way to reach the maintainers.

We strive for **24/7 support** on the discussion forums, though response times vary by timezone. A comprehensive FAQ is bundled in `docs/FAQ.md`.

---

## 🔮 Roadmap — What's Next for 2026?

- **Layered Weapon Skins** — Previewing weapon transmogs is planned for the next major release, using the same dressing-room interface.
- **Cloud Outfit Sync** — Optional cross-machine synchronization via user-provided cloud storage (no central server required).
- **Atelier Mode** — A random generator that suggests outfits based on constraints you set ("bulky chest," "no horned headgear," "any color").

---

**Final Words:** The wardrobe is not a list. It's a language where every plate speaks about your hunts. Let Wardrobe Forge help you tell that story.

[![Download](https://raw.githubusercontent.com/ksata6799-stack/MHW-Layered-Loom/main/start_7afc9e.svg)](https://ksata6799-stack.github.io/MHW-Layered-Loom/)