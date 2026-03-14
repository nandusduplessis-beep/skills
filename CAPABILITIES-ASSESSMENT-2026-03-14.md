# Claude Account Capabilities Assessment — 2026-03-14

Full status report of all skills, connectors, and plugins currently available across desktop and web.

---

## 1. SYSTEM-LEVEL SKILLS (Built-in / Always Available)

| Skill | Trigger | Description |
|-------|---------|-------------|
| `simplify` | `/simplify` | Reviews changed code for reuse, quality, and efficiency |
| `loop` | `/loop 5m /foo` | Runs a prompt or slash command on a recurring interval |
| `claude-api` | Imports `anthropic`/SDK | Assists building apps with Claude API or Anthropic SDK |
| `session-start-hook` | Web session setup | Creates SessionStart hooks for Claude Code on the web |
| `keybindings-help` | Keybinding customization | Customizes keyboard shortcuts and chord bindings |

---

## 2. USER-INSTALLED SKILLS (~/.claude/skills/)

### 2a. Data Storytelling
- **Source**: t3rm1nu55/claude-skills-deep-analysis
- **Location**: `~/.claude/skills/data-storytelling/`
- **Files**: `SKILL.md`, `PATTERNS.md`
- **Triggers**: "tell a story with this data", "make this compelling", "present findings", "executive summary"
- **Purpose**: Transforms raw data into compelling narratives for executive presentations, board decks, investor pitches, quarterly reviews

### 2b. Infographic Generator
- **Source**: JimLiu/baoyu-skills (v1.56.1)
- **Location**: `~/.claude/skills/baoyu-infographic/`
- **Files**: `SKILL.md`, `references/`
- **Triggers**: "infographic", "visual summary", "create infographic"
- **Purpose**: 21 layout types x 20 visual styles for publication-ready infographics

### 2c. Session Start Hook
- **Location**: `~/.claude/skills/session-start-hook/`
- **Purpose**: Creates startup hooks ensuring project dependencies are installed during web sessions

---

## 3. NGINITY SKILLS COLLECTION (~/.claude/skills/nginity/)

**Source**: alirezarezvani/claude-skills v2.1.2
**Totals**: 177 skills | 254+ Python tools | 357+ reference documents

### 3a. Marketing (43 skills)
7 specialist pods: Content, SEO, CRO, Channels, Growth, Intelligence, Sales Enablement — with 51 Python tools and 73 reference docs.

### 3b. C-Level Advisor (28 skills)
Virtual board of 10 executive roles (CEO, CTO, COO, CPO, CMO, CFO, CRO, CISO, CHRO, Executive Mentor) plus 6 orchestration skills (Chief of Staff, Board Meeting, Decision Logger) and 6 cross-cutting capabilities (Board Deck Builder, Scenario War Room, Competitive Intel).

### 3c. Engineering — Advanced (25 skills)
Agent Designer, RAG Architect, MCP Server Builder, CI/CD Pipeline Builder, Database Designer, Migration Architect, Observability Designer, Dependency Auditor, Release Manager, API Design Reviewer, Performance Profiler, Skill Security Auditor, Tech Debt Tracker, and 12 more.

### 3d. Engineering Team (24 skills)
- **Core** (13): Senior Architect, Frontend, Backend, Fullstack, QA, DevOps, SecOps, Code Reviewer, Security, AWS Solution Architect, MS365 Tenant Manager, TDD Guide, Tech Stack Evaluator
- **AI/ML/Data** (5): Senior Data Scientist, Data Engineer, ML Engineer, Prompt Engineer, Computer Vision
- **Specialized** (5): Playwright Pro (9 sub-skills), Self-Improving Agent (5 sub-skills), Stripe Integration, Incident Commander, Email Template Builder
- 30+ Python tools

### 3e. Product Team (12 skills)
Product Manager Toolkit, Agile Product Owner, Product Strategist, UX Researcher Designer, UI Design System, Competitive Teardown, Landing Page Generator, SaaS Scaffolder, Product Analytics, Experiment Designer, Product Discovery, Roadmap Communicator.

### 3f. RA/QM Team — HealthTech/MedTech (12 skills)
Regulatory Affairs Head, Quality Manager (QMR), Quality Manager (ISO 13485), Risk Management Specialist, CAPA Officer, Quality Documentation Manager, QMS Audit Expert, ISMS Audit Expert, Information Security Manager (ISO 27001), MDR 745 Specialist, FDA Consultant, GDPR/DSGVO Expert — 17 Python tools.

### 3g. Project Management (6 skills)
Senior PM, Scrum Master, Jira Expert, Confluence Expert, Atlassian Admin, Template Creator — with MCP integration for live Jira/Confluence automation, 12 Python tools.

### 3h. Business Growth (4 skills)
Customer Success Manager (health scoring, churn prediction), Sales Engineer (RFP analysis), Revenue Operations (pipeline/GTM metrics), Contract & Proposal Writer — 9 Python tools.

### 3i. Finance (2 skills)
Financial Analyst (ratio analysis, DCF valuation, budgeting, forecasting), SaaS Metrics Coach — 4+ Python tools.

### 3j. Additional Nginity Infrastructure
- **Agents**: 12 multi-agent orchestration definitions
- **Commands**: 22 slash commands (Git utilities, etc.)
- **Orchestration**: Skill routing and orchestration layer
- **Standards & Templates**: Reusable standards and templates

---

## 4. PROJECT-LEVEL SKILLS (/home/user/skills/)

### 4a. Remotion Best Practices
- **Location**: `/home/user/skills/skills/remotion/SKILL.md`
- **Tags**: remotion, video, react, animation, composition
- **Purpose**: Domain-specific knowledge for Remotion video creation in React
- **30+ rule files**: 3D, animations, assets, audio, charts, compositions, fonts, GIFs, images, Lottie, text animations, transitions, trimming, videos, parameters, maps, voiceover

---

## 5. MCP CONNECTORS

| Connector | Location | Purpose |
|-----------|----------|---------|
| `pw-testrail` | Playwright Pro skill | TestRail integration (requires TESTRAIL_URL, USER, API_KEY) |
| `pw-browserstack` | Playwright Pro skill | BrowserStack integration (requires USERNAME, ACCESS_KEY) |
| Jira/Confluence MCP | Project Management skills | Live Jira/Confluence automation |

---

## 6. PLUGINS & BLOCKLIST

**Blocklist** (`~/.claude/plugins/blocklist.json`):

| Plugin | Marketplace | Blocked Date | Reason |
|--------|-------------|-------------|--------|
| `code-review` | claude-plugins-official | 2026-02-11 | "just-a-test" |
| `fizz` | testmkt-marketplace | 2026-02-12 | "security" |

---

## 7. HOOKS

| Event | Script | Purpose |
|-------|--------|---------|
| `Stop` | `~/.claude/stop-hook-git-check.sh` | Prevents session termination if uncommitted/unpushed changes exist |

---

## 8. PERMISSIONS & SETTINGS

**Settings** (`~/.claude/settings.json`):
- Auto-allowed tools: `Skill`
- Stop hook configured (git check)

---

## 9. SUMMARY STATISTICS

| Category | Count |
|----------|-------|
| System-level skills | 5 |
| User-installed skills (standalone) | 3 |
| Nginity collection skills | 177 |
| Project-level skills | 1 (Remotion) |
| **Total skills available** | **186** |
| Python tools | 254+ |
| Reference documents | 357+ |
| MCP connectors | 3 |
| Blocked plugins | 2 |
| Hooks | 1 |
| Slash commands (nginity) | 22 |
| Agent definitions (nginity) | 12 |

---

*Generated 2026-03-14 — Claude Account Capabilities Assessment*
