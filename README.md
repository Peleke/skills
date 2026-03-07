<div align="center">

# Hunter Pipeline

### Opportunity-to-Launch in Six Skills

[![Claude Code](https://img.shields.io/badge/Claude_Code-Skills-4DCFC9?style=for-the-badge&logo=anthropic&logoColor=white)]()
[![Agent Skills](https://img.shields.io/badge/Agent_Skills-v1.0-4DCFC9?style=for-the-badge)]()
[![TypeScript](https://img.shields.io/badge/TypeScript-Interfaces-3178C6?style=for-the-badge&logo=typescript&logoColor=white)]()
[![License](https://img.shields.io/badge/License-MIT-4ade80?style=for-the-badge)]()
[![Obsidian](https://img.shields.io/badge/Obsidian-Vault_Sync-7C3AED?style=for-the-badge&logo=obsidian&logoColor=white)]()

**Signal. Decision. Persona. Offer. Pitch. Ship.**

[Pipeline](#the-pipeline) · [Skills Catalog](#skills-catalog) · [Architecture](#architecture) · [Design System](#design-system) · [Getting Started](#getting-started)

---

</div>

## The Problem

Most "AI agent" tools automate fragments. Summarize a doc. Draft an email. Generate a landing page. None of them do the full loop: spot an opportunity in the wild, validate it against real evidence, understand who actually hurts, scope what to build, generate every launch asset, and track whether it worked.

Hunter Pipeline does the full loop. Six core skills, chained through a typed envelope contract, writing structured output to an Obsidian vault that doubles as a queryable database. Every claim traced to evidence. Every decision logged with kill criteria. Every asset deployable from the vault.

---

## The Pipeline

```
                                    ┌─────────────────┐
                                    │   wild-scan      │ ─── reddit-harvest
                                    │   (research)     │ ─── quote-to-persona
                                    └────────┬────────┘
                                             │ feeds
                                             ▼
┌──────────────┐    ┌──────────────┐    ┌──────────────┐    ┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│              │    │              │    │              │    │              │    │              │    │              │
│  signal-scan │───▶│ decision-log │───▶│persona-extract│──▶│  offer-scope │───▶│    pitch     │───▶│  hunter-log  │
│              │    │              │    │              │    │              │    │              │    │              │
│   Stage 1    │    │   Stage 2    │    │   Stage 3    │    │   Stage 4    │    │   Stage 5    │    │  Persistence │
│   Signals    │    │   Decide     │    │   Personas   │    │   Scope      │    │   Launch Kit │    │  Vault I/O   │
│              │    │              │    │              │    │              │    │              │    │              │
└──────────────┘    └──────────────┘    └──────┬───────┘    └──────────────┘    └──────┬───────┘    └──────────────┘
                                               │                                      │
                                               ▼                                      ▼
                                        ┌──────────────┐                   ┌────────────────────┐
                                        │swot-analysis │                   │  Output Skills     │
                                        │  (optional)  │                   │                    │
                                        │ stress-test  │                   │  slidev-deck       │
                                        └──────────────┘                   │  landing-page      │
                                                                           │  one-pager         │
                                                                           │  design-pass       │
                                                                           └────────────────────┘
```

Each stage consumes the output of the previous stage via a typed `PipelineEnvelope`. Every skill reads `_conventions.md` before executing, ensuring consistent vault paths, frontmatter schemas, and cross-reference syntax across the entire pipeline.

---

## Skills Catalog

### Core Pipeline

| | Skill | Description | Consumes | Produces |
|---|---|---|---|---|
| 📡 | **[signal-scan](skills/custom/signal-scan/)** | Scan a domain for product opportunities across 7 signal types | Domain + operator edge | Scored opportunities + ship candidates |
| ⚖️ | **[decision-log](skills/custom/decision-log/)** | Structured go/no-go decision with SDP scoring and pre-mortem | Signal scan output | Decision record + kill criteria |
| 👤 | **[persona-extract](skills/custom/persona-extract/)** | Evidence-based buyer personas from real community stories | Decision + signal data | Persona archetypes + Four Forces |
| 🎯 | **[offer-scope](skills/custom/offer-scope/)** | 1-day build spec with positioning, pricing, and distribution | Persona + SPEND data | Build spec + revenue model |
| 🚀 | **[pitch](skills/custom/pitch/)** | Complete go-to-market launch kit with deployable assets | Offer spec + all upstream | Landing page, posts, emails, deck |
| 📒 | **[hunter-log](skills/custom/hunter-log/)** | Persistence layer — vault I/O, kanban updates, session tracking | PipelineEnvelope (any) | Obsidian markdown + kanban card |

### Validation & Research

| | Skill | Description | Tier |
|---|---|---|---|
| 🔍 | **[swot-analysis](skills/custom/swot-analysis/)** | Evidence-grounded SWOT with verdict, risk registry, moat assessment | Validation |
| 🎯 | **[wild-scan](skills/custom/wild-scan/)** | Pain-quote harvester for the "From the Wild" content series | Research |
| 📡 | **[reddit-harvest](skills/custom/reddit-harvest/)** | Playwright-driven Reddit quote harvester with full metadata | Research |
| 🔬 | **[quote-to-persona](skills/custom/quote-to-persona/)** | Bridge wild-scan quotes into persona-extract-compatible archetypes | Research |

### Output & Deployment

| | Skill | Description | Tier |
|---|---|---|---|
| 🎬 | **[slidev-deck](skills/custom/slidev-deck/)** | Slidev presentations with inline hand-drawn SVGs | Output |
| 🌐 | **[landing-page](skills/custom/landing-page/)** | Single-file HTML landing page from pitch copy, zero deps | Output |
| 📄 | **[one-pager](skills/custom/one-pager/)** | Print-ready one-pager as React JSX, exported to PDF | Output |
| 🎨 | **[design-pass](skills/custom/design-pass/)** | Tiered aesthetic upgrades (CSS/SVG) for decks, pages, one-pagers | Output |

### Content & Distribution

| | Skill | Description | Tier |
|---|---|---|---|
| 📰 | **[content-planner](skills/custom/content-planner/)** | Scan GitHub + buildlog, generate Obsidian content plan | Content |
| 🎡 | **[linwheel-content-engine](skills/custom/linwheel-content-engine/)** | Drive LinWheel LinkedIn content pipeline via MCP tools | Content |
| 🎯 | **[linwheel-source-optimizer](skills/custom/linwheel-source-optimizer/)** | Optimize vault notes for LinWheel reshape quality | Content |
| 🏘️ | **[community-pitch](skills/custom/community-pitch/)** | Paid community plan with tiers, cadence, and economics | Content |
| 🎓 | **[skool-pitch](skills/custom/skool-pitch/)** | Skool-specific community design with gamification and launch playbook | Content |

### Utility & Infrastructure

| | Skill | Description | Tier |
|---|---|---|---|
| 🏗️ | **[inline-svg-architecture-diagrams](skills/custom/inline-svg-architecture-diagrams/)** | Production-quality SVG architecture diagrams with animations | Utility |
| ✍️ | **[chapter-generator](skills/custom/chapter-generator/)** | Generate tutorial chapters from structured specs | Utility |
| 🗺️ | **[curriculum-planner](skills/custom/curriculum-planner/)** | Interactive elicitation for tutorial series design | Utility |
| 🎫 | **[issue](skills/custom/issue/)** | Draft well-structured GitHub issues | Utility |
| 📚 | **[mkdocs-site-generator](skills/custom/mkdocs-site-generator/)** | Complete MkDocs site with GitHub Pages CI/CD | Utility |
| 🤖 | **[llms-txt-generator](skills/custom/llms-txt-generator/)** | Generate llms.txt for AI-queryable MkDocs docs | Utility |
| ✏️ | **[sketches](skills/custom/sketches/)** | Hand-drawn SVG sketches, wireframes, and diagrams | Utility |
| 🧠 | **[interview-prep](skills/custom/interview-prep/)** | Gap analysis and phased study plan for target roles | Utility |
| 🎯 | **[job-search](skills/custom/job-search/)** | Structured job search: scan, sort, brief, package, track | Utility |

---

## Core Pipeline Detail

### Stage 1: Signal Scan

Systematically scans a domain across **7 canonical signal types** (Pain, Demand, Spend, Sentiment, Competitive, Behavior, Audience) using real web search data. Every signal must have evidence -- actual quotes, specific numbers, URLs. Produces a scored opportunity ranking and concrete ship candidates.

**In** `Domain + operator edge + constraints`
**Out** `JSON scan + markdown summary` → `Signal-Scans/`

### Stage 2: Decision Log

Runs the Signal-to-Decision Pipeline (SDP) -- a 6-dimension scoring framework (Pain, Spend, Edge, Speed, Gap, Audience) with 3x/2x/1x weights. Includes reversibility check (Bezos two-way door), Helmer 7 Powers assessment, cognitive bias audit, and pre-mortem with at least 3 failure scenarios.

**In** `Signal scan output + operator preferences`
**Out** `Decision record + kill criteria + next-step hint` → `Decisions/`

### Stage 3: Persona Extract

Transforms decisions into evidence-based buyer personas using the Signal-to-Story Pipeline. Collects real pain stories and success stories via web search, maps decision points where products can intervene, runs Bob Moesta's Four Forces analysis (Push/Pull/Anxiety/Habit), and clusters into 3-4 behavioral archetypes.

**In** `Decision log + signal data`
**Out** `Persona archetypes + Four Forces + offer mapping` → `Personas/`

### Stage 4: Offer Scope

Converts persona insights into a shippable 1-day build spec. Applies Hormozi's value equation (Dream Outcome, Perceived Likelihood, Time Delay, Effort & Sacrifice), selects format based on consumption context, generates positioning copy using the persona's exact language, and models revenue with conservative assumptions.

**In** `Persona + SPEND signals + constraints`
**Out** `Build spec + positioning + distribution plan + revenue model` → `Offers/`

### Stage 5: Pitch

The synthesis layer. Generates the complete go-to-market launch kit: paste-ready landing page copy, platform-specific launch posts (80/20 value-first), GitHub product README, 5-email post-purchase sequence, hour-by-hour launch checklist, A/B test spec, kill criteria refinement, and a Slidev presentation. Deploys to a launchpad repo branch with PR and Vercel preview.

**In** `Offer spec + persona + SWOT + decision + signal scan`
**Out** `Landing page, posts, emails, README, deck, kanban` → `Pitches/` + launchpad branch

### Persistence: Hunter Log

Pure I/O layer. Receives any skill's `PipelineEnvelope`, renders Obsidian-compatible markdown with correct frontmatter, writes to the vault, updates session logs, and moves kanban cards. Does not analyze. Only formats and saves.

**In** `PipelineEnvelope (JSON)`
**Out** `Vault files + kanban updates + session tracking`

---

## Output Skills

| Skill | What It Produces | Triggered By |
|---|---|---|
| **slidev-deck** | Slidev markdown with extracted SVGs, speaker notes, design system | Pitch Phase 8 or standalone |
| **landing-page** | Single-file HTML, dark theme, mobile responsive, zero deps, < 30KB | Pitch Phase 3e or standalone |
| **one-pager** | Print-ready React JSX → PDF (8.5" x 11") | Post-pitch or standalone |
| **design-pass** | CSS/SVG upgrades across 3 tiers (high/medium/full) | Any visual asset |

---

## Design System

The `design-pass` skill applies aesthetic upgrades from a tiered technique catalog defined in `_design-conventions.md`:

| Tier | Techniques | Risk | Scope |
|---|---|---|---|
| **High** | Split-color headings, animated underline, v-click stagger, blur-to-sharp, blockquote slide-in | Zero | Pure CSS additions |
| **Medium** | High + dot grid bg, radial halo, glassmorphism, metric cards | Low | Wrapper elements |
| **Full** | Medium + gradient text, glow, shimmer, v-motion, custom transitions, SVG animations | Medium | Animations, browser caveats |

All pipeline visual assets share a color palette:

| Token | Value | Usage |
|---|---|---|
| Background | `#0d1117` | Page/slide background |
| Text | `#eee0cc` | Primary body text |
| Teal | `#4DCFC9` | Accent, links, highlights |
| Coral | `#e88072` | Alerts, emphasis |
| Muted | `#8b949e` | Secondary text, captions |
| Green | `#4ade80` | Success, positive signals |
| Red | `#f87171` | Kill criteria, warnings |
| Yellow | `#facc15` | Pending, attention |

---

## Architecture

### PipelineEnvelope

Every skill wraps its output in a typed envelope:

```json
{
  "skill": "signal-scan",
  "version": "1.0",
  "session_id": "session-2026-03-06-001",
  "timestamp": "2026-03-06T14:30:00Z",
  "input_refs": ["upstream-artifact-id"],
  "output": { }
}
```

### Vault-as-Database

The Obsidian vault is structured as a queryable database:

```
Admin/Product-Discovery/
├── Pipeline.kanban.md          # Master board: 7 columns from Scanned → Shipped/Killed
├── _index.md                   # Dataview queries
├── Signal-Scans/               # signal-scan output
├── Decisions/                  # decision-log output
├── Personas/                   # persona-extract output
├── SWOT/                       # swot-analysis output
├── Offers/                     # offer-scope output
├── Pitches/                    # pitch output + launch kanbans
├── Sessions/                   # session logs
└── Pipeline.md                 # Product tracker table
```

- **Folders** = tables
- **Frontmatter** = schema (type, date, status, tags, refs)
- **Wikilinks** = foreign keys
- **Dataview** = SQL
- **Kanban boards** = status columns

This is designed for mechanical migration to a real backend when the time comes.

### Conventions Contract

`_conventions.md` is loaded by every skill before execution. It defines:

- Canonical vault and skills directory paths
- Folder-to-type mapping (which skill writes where)
- Frontmatter schema per document type
- Valid statuses per type
- Tag hierarchy (`hunter/`, `content/`, `outreach/`)
- Cross-reference syntax (wikilinks, buildlog refs, GitHub refs)
- Pipeline kanban contract (which skill moves cards to which column)
- Prose quality gate (Bragi persona review for all human-facing copy)

---

## Getting Started

### Prerequisites

- [Claude Code](https://claude.com/claude-code) with skills support
- An Obsidian vault (iCloud-synced recommended)
- GitHub CLI (`gh`) for pitch deployment

### Install

Register the skills marketplace in Claude Code:

```bash
/plugin marketplace add anthropics/skills
```

Or clone directly:

```bash
git clone https://github.com/Peleke/skills.git
```

### Configure

Set vault and skills paths in `_conventions.md`:

```markdown
| Variable | Current Value |
|---|---|
| `${VAULT}` | `/path/to/your/obsidian/vault` |
| `${SKILLS_DIR}` | `/path/to/skills/skills/custom` |
```

### Run the Pipeline

```
"Scan DevOps education for product signals"     → signal-scan
"Which opportunity should I pursue?"            → decision-log
"Extract personas for this opportunity"         → persona-extract
"Scope an offer for the top persona"            → offer-scope
"Build the launch kit"                          → pitch
```

Each skill chains automatically. Or run any skill standalone with the right trigger phrase.

---

## Obsidian Integration

### Vault Structure

Pipeline output lands in `Admin/Product-Discovery/` with one folder per document type. Content briefs land in `Writing/Content-Briefs/`. Each file has structured frontmatter queryable by Dataview.

### Kanban Tracking

`Pipeline.kanban.md` tracks every product idea across 7 columns:

```
Signal Scanned → Decision Made → Persona Researched → Offer Scoped → Building → Shipped → Killed
```

Skills automatically move cards as the pipeline advances. The operator manually moves cards to "Building" (with launch date) and "Shipped" or "Killed".

### Cross-References

All documents link to their upstream artifacts via wikilinks and `*_ref` frontmatter fields. Dataview queries in `_index.md` surface active opportunities, recent decisions, and pipeline velocity.

### Content Seeds

The pitch skill writes `::linkedin`-prefixed content seeds to `Writing/Content-Briefs/`. These trigger the OpenClaw ambient pipeline: Obsidian → LinWheel → LinkedIn publication.

---

<div align="center">

**Built for the engineer who can build anything but never had a system for deciding what to build.**

[![Claude Code](https://img.shields.io/badge/Claude_Code-Skills-4DCFC9?style=for-the-badge&logo=anthropic&logoColor=white)]()

</div>
