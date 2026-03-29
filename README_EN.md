# 📄 Paper Glance

English (this page) | 中文说明: [README.md](README.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-blueviolet?logo=anthropic)](https://claude.ai)
[![Zero MCP Required](https://img.shields.io/badge/MCP-Not_Required-brightgreen)](https://claude.ai)

**Claude Skill: Your all-in-one paper copilot**

Upload any academic PDF and Claude can generate deep analysis, mindmaps, reviewer-style feedback, promo copy, and podcast scripts/audio. **Core features work out of the box with no extra plugins.**

---

## 📑 Table of Contents

- [Features](#-features)
- [Quick Start](#-quick-start)
  - [Install the Skill](#step-1-install-the-skill) ([Claude Desktop](#option-a-claude-desktop-gui-upload) · [Command Install](#option-b-claude-code--command-install) · [Manual Folder](#option-c-claude-code--manual-folder-placement))
  - [Use it](#step-2-use-it)
- [Feature Details](#-feature-details)
- [File Structure](#-file-structure)
- [FAQ](#-faq)
- [License](#-license)

---

## ✨ Features

| # | Feature | Description |
|---|---------|-------------|
| 1 | 📊 Deep Analysis | Structured academic breakdown of method, experiments, and novelty |
| 2 | 🧠 Mindmap | Mermaid mindmap + optional pipeline flowchart, rendered in chat |
| 3 | 🔍 Review Report | Professional format: Summary / Strengths / Weaknesses / Questions |
| 4 | 📢 Promo Scripts | Twitter/X post, blog-style summary, talk intro, email summary |
| 5 | 🎙️ Podcast Audio | Solo or dual-host script, optional one-click MP3 via TTS |

> Features 1-4 do not require MCP. Feature 5 falls back to text-only script mode when [TTS MCP](https://github.com/CatVinci-Studio/better-tts-mcp) is unavailable.

---

## 🚀 Quick Start

### Step 1: Install the Skill

> **What is a Skill?** A Skill is an instruction bundle that adds specialized capabilities to Claude. After installation, Claude detects and uses it automatically. Supported in **Claude Desktop** and **Claude Code (CLI / IDE extensions)**.

#### Option A: Claude Desktop (GUI Upload)

1. Click `Code -> Download ZIP`, or download from Releases.
2. In Claude Desktop, open `Customize` -> `Skills` -> `Upload a skill`.
3. Upload the zip file. Done ✅

#### Option B: Claude Code — Command Install

1. Clone or download this repository:
   ```bash
   git clone https://github.com/CatVinci-Studio/paper-glance-skill.git
   ```
2. Install the skill (choose one):

   **Global install** (available in all projects):
   ```bash
   claude install-skill /path/to/paper-glance-skill
   ```
   **Project-level install** (current project only):
   ```bash
   claude install-skill --project /path/to/paper-glance-skill
   ```

#### Option C: Claude Code — Manual Folder Placement

1. Clone or download this repository.
2. Copy the `paper-glance-skill` folder into the Claude Code skills directory:

   **Global** (available in all projects):
   ```bash
   cp -r paper-glance-skill ~/.claude/skills/
   ```
   **Project-level** (current project only):
   ```bash
   cp -r paper-glance-skill .claude/skills/
   ```
3. Restart your Claude Code session and you're good to go ✅

### Step 2: Use it

After installation, upload a paper PDF and send any message:

```text
"Help me read this paper"
"Generate a mindmap"
"Write a review"
"Create a promo post"
```

Claude will parse the paper and show the menu:

```text
📄 Paper loaded: "Attention Is All You Need" (2017)
> Replacing RNNs with self-attention, establishing the Transformer foundation.

What would you like to do with this paper?

  1  📊 Deep analysis
  2  🧠 Mindmap
  3  🔍 Review report
  4  📢 Promo scripts
  5  🎙️ Podcast audio
  0  Generate all
```

Reply with a number, or just describe what you want in natural language.

---

## 📦 Feature Details

### 1 · 📊 Deep Analysis
A structured academic interpretation covering motivation, method design, key innovations, experiment setup/results, limitations, and future directions.

### 2 · 🧠 Mindmap
Generates a radial mindmap by default (problem -> method -> experiments -> contributions -> limitations). You can also request a method pipeline diagram. Both are standard Mermaid and can be edited in [mermaid.live](https://mermaid.live).

### 3 · 🔍 Review Report
Outputs a conference/journal-style review:

| Section | Content |
|---------|---------|
| **Summary** | 3-5 objective sentences about problem, method, and conclusions |
| **Strengths** | 3-5 evidence-backed strengths |
| **Weaknesses** | 3-5 weaknesses, each with improvement suggestions |
| **Questions** | 3-5 questions for the authors |
| **Minor Comments** | Optional minor issues |
| **Decision** | Accept / Weak Accept / Borderline / Weak Reject / Reject + rationale |

### 4 · 📢 Promo Scripts
One-click generation for multiple formats: Twitter/X post (with hashtags), blog/social summary, academic talk opening, and email summary.

### 5 · 🎙️ Podcast Script + Audio
Converts paper content into podcast-ready narration:

- Solo host narration (science explainer style)
- Dual-host dialog (Host x Expert)

If `better-tts-mcp` is connected, it can generate MP3 directly. Otherwise it automatically falls back to text-only script mode.

- TTS project: `https://github.com/CatVinci-Studio/better-tts-mcp`

---

## 📁 File Structure

```text
paper-glance-skill/
├── SKILL.md                # Entry: paper parsing + feature menu
├── README.md               # Chinese README
├── README_EN.md            # English README
├── shared/
│   └── paper_core.md       # Shared extraction schema
└── modules/
    ├── 01_analysis.md      # Deep analysis
    ├── 02_mindmap.md       # Mindmap + flowchart
    ├── 03_review.md        # Review report
    ├── 04_promo.md         # Promo scripts
    └── 05_podcast.md       # Podcast script + audio
```

---

## ❓ FAQ

**Q: Do I need an API key or paid plugin?**
No. All core capabilities rely on Claude's native abilities.

**Q: Does it support English papers?**
Yes. It supports both Chinese and English papers, and output language can be specified.

**Q: Mermaid mindmap does not render in my client.**
Use the latest Claude Desktop version, or copy Mermaid code to [mermaid.live](https://mermaid.live).

**Q: Why wasn't MP3 generated for podcast mode?**
TTS MCP is likely not connected. In that case the skill falls back to script-only mode. Install and connect: `https://github.com/CatVinci-Studio/better-tts-mcp`

---

## 📄 License

MIT - free to use, modify, and share. PRs and issues are welcome.
