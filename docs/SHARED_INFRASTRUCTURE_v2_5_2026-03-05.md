# SHARED INFRASTRUCTURE REFERENCE
**Version:** 2.5
**Created:** 2026-02-25
**Updated:** 2026-03-05 (v2.5) — M8 COMPLETE: exemplar store seeded (15 gold/15 silver), 13 intelligence loops scheduled (n8n 1007–1019), ACCME providers ingested, NEXUS seeded (1,685 records), Schema Registry + API Resilience built (113/113 tests), IR-07 Intelligence Dashboard live, UI branch merged, shared-services committed (edff6c4), sync.sh clean, Azure client secret rotated, SHAREPOINT_DRIVE_ID resolved, git history cleaned (268MB removed), NEXUS historical grant merge complete (1,082 records, 88 funders, 157 TAs)
**Owner:** Lou Settembrino | Catalyst Medical Education
**Purpose:** Upload to ALL Claude Project Files. Gives every project chat awareness of shared tools, decisions, and conventions.
**Update protocol:** When anything changes, bump version, update date, re-upload to all 4 projects.

---

## COMPANY BOUNDARIES — READ FIRST

| Entity | Status | Scope |
|---|---|---|
| **Catalyst Medical Education, LLC** | Active — existing business | CME/IME grant-funded programs, ~$6.5M revenue |
| **TechCelerate** | Separate company | RT CE platform, separate LMS, ASRT-accredited |
| **CAMEOS/OMEOS** | Not yet formalized | Platform IP, internal system first |

**Critical rule:** Never mix TechCelerate into CAMEOS discussions or vice versa. Cross-project decisions go to the Catalyst Command Post.

---

## TOOL APPLICABILITY MATRIX

| Tool | CAMEOS | TechCelerate | Catalyst Website |
|---|---|---|---|
| Claude Code + Ralph-loop | ✅ | ✅ | ✅ |
| CLAUDE.md hierarchy | ✅ | ✅ | ✅ |
| GitHub repos + Actions | ✅ | ✅ | ✅ |
| Remote Control (`/rc`) | ✅ | ✅ | ✅ |
| Agent Teams | ✅ Critical | 🟡 When needed | 🟡 When needed |
| Custom Skills (Claude Code) | ✅ | ✅ | ✅ |
| Cowork Skills | ❌ | ✅ Content ops | 🟡 Review workflows |
| Cowork Scheduled Tasks | ❌ | ✅ Regulatory monitor | 🟡 Content review |
| PostToolUse auto-sync hook | ✅ | ✅ | ✅ |
| Supabase trace logging | ✅ Critical | 🟡 Nice to have | 🟡 Nice to have |
| Consensus Engine | ✅ | ❌ Overkill | ❌ |
| Model Router | ✅ | ❌ | ❌ |
| Exemplar Store | ✅ Critical — LIVE | ❌ | ❌ |
| Web Scraper (IR-01) | ✅ Critical | 🟡 Content freshness | 🟡 Living Website |
| PDF Intelligence (IR-02) | ✅ Critical | ❌ | ❌ |
| Schema Registry | ✅ Critical — LIVE | ❌ | ❌ |
| API Resilience Layer | ✅ Critical — LIVE | 🟡 Useful | ❌ |
| Prompt Registry | ✅ | ❌ | ❌ |
| Failure Taxonomy (15 codes) | ✅ | ❌ CAMEOS-specific | ❌ |
| Meta-Builder gates | ✅ | ❌ | ❌ |
| Phase Build Oracles | ✅ | ✅ Critical | ✅ |
| n8n workflows | ✅ 19 live | ✅ | ✅ |
| GitHub Actions CI/CD | ✅ | ✅ | ✅ |
| Uptime Robot | ✅ | ✅ | ✅ |
| UI/UX Pro Max Skill | ❌ | ❌ | ✅ Critical |
| Microsoft Graph MCP | ❌ | ❌ | ✅ (Living Website, post-launch) |
| Claude in Chrome | 🟡 Research | ✅ Scraping + form fill | 🟡 Content ops |
| Prompt Caching (API) | ✅ M6+ | ✅ Content pipeline | ❌ |

---

## MAC-MOLT — BUILD MACHINE

**Machine:** Apple Silicon Mac, dedicated build machine
**User:** automation-runner
**Projects root:** ~/Projects/
**CAMEOS-Drive:** ~/CAMEOS-Drive/

### Standard Invocation Pattern

```bash
caffeinate -i tmux new-session -s [session-name]
cd ~/Projects/[repo]
claude --dangerously-skip-permissions
```

`--chrome` is permanent default (configured 2026-03-04). `caffeinate` prevents sleep. tmux preserves session on disconnect. `--dangerously-skip-permissions` enables unattended builds per DEC-067.

**Quick health check after OS update or restart:**
```bash
tmux ls                                    # confirm sessions
pm2 status                                 # n8n should show online
ps aux | grep python3 | grep -v grep       # any active pipeline runs
```

**tmux quick reference:**
- Detach (leave running): `Ctrl+B` then `D`
- Reattach: `tmux attach -t [session-name]`
- Scroll up: `Ctrl+B` then `[`, arrow keys, `Q` to exit

### Confirmed Installed

| Tool | Version | Status | Notes |
|---|---|---|---|
| Claude Code | 2.1.58+ | ✅ Live | Max plan OAuth — NOT API key billing. `--chrome` default. |
| Python | 3.12 | ✅ Live | `/opt/homebrew/bin/python3.12` — ALWAYS use this, NOT system python3 (3.9) |
| n8n | 2.10.2 | ✅ Live | pm2 autostart, `http://localhost:5678` |
| Node.js | v25.6.1_1 | ✅ Live | |
| Git | Current | ✅ Live | All 4 repos configured |
| Homebrew | Current | ✅ Live | |
| Cowork | Current | ✅ Live | File edits only — never send run/execute commands |
| iTerm2 | Current | ✅ Live | Primary terminal |
| Microsoft 365 | Current | ✅ Active | Teams, SharePoint, OneDrive in use |
| Superpowers plugin | Current | ✅ User scope | Claude Code plugin |
| claude-mem plugin | Current | ✅ User scope | Claude Code plugin |
| Playwright | Current | ✅ Live | Chromium installed. Used by Web Scraper IR-01 |
| PyMuPDF (fitz) | Current | ✅ Live | Used by PDF Intelligence IR-02 |

---

## CLAUDE CODE ADVANCED FEATURES

### Agent Teams

**Status:** ✅ Enabled (2026-03-04)
**Config:** `~/.claude/settings.json` → `env.CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS = "1"`
**Proven pattern (M8):** W2 (loop scheduling) and W4 (schema registry + API resilience) both ran as 2-agent teams. File-lock based task claiming prevents race conditions.

**When to use:** 3+ distinct parallel tasks with no file overlap. Token cost is 3-4x single session.
**When NOT to use:** Single-file edits, simple tasks, learning/exploration.

### Custom Skills

**Status:** ✅ Deployed — 6 skills across 3 locations

| Skill | Location | Triggers on |
|---|---|---|
| `sprint-closure` | `~/.claude/skills/` | `/close`, session summary, handoff generation |
| `handoff-generator` | `~/.claude/skills/` | "create handoff", "prepare handoff", opening prompts |
| `cameos-governance` | `cameos-mono/.claude/skills/` | DEC references, FROZEN artifacts, HITL, governance |
| `proposal-pipeline` | `cameos-mono/.claude/skills/` | Pipeline runs, quality scoring, Shell-and-Guts |
| `intelligence-loop` | `cameos-mono/.claude/skills/` | L-## loops, Supabase intelligence, IR-## infrastructure |
| `shared-service-build` | `shared-services/.claude/skills/` | shared/ package components, import patterns |

### CAMEOS Specialist Subagents

**Status:** ✅ Deployed — 6 agents
**Location:** `~/Projects/cameos-mono/.claude/agents/`

| Agent | File | Purpose |
|---|---|---|
| Governance Checker | `governance-checker.md` | Verify FROZEN artifacts, DEC integrity, evaluator chain |
| Pipeline Runner | `pipeline-runner.md` | Execute 5-pass proposal pipeline |
| Quality Auditor | `quality-auditor.md` | Run quality_scorer_v2.py, auto_improve.py |
| Intelligence Builder | `intelligence-builder.md` | Build L-## loops, wire Supabase tables |
| Schema Validator | `schema-validator.md` | Validate pipeline data contracts |
| Supabase Ops | `supabase-ops.md` | Table creation, queries, schema checks |

### PostToolUse Auto-Sync Hook

**Status:** ✅ Active
**Hook script:** `~/.claude/hooks/auto-sync.sh`
**5-minute debounce.** Async — doesn't block Claude Code.

### Settings.json (Current State)

```json
{
  "env": {
    "CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS": "1"
  },
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [{"type": "command", "command": "~/.claude/hooks/force-push-block.sh", "timeout": 10}]
      },
      {
        "matcher": "Write|Edit|MultiEdit",
        "hooks": [{"type": "command", "command": "~/.claude/hooks/credential-guard.sh", "timeout": 10}]
      }
    ],
    "PostToolUse": [
      {
        "matcher": "Write|Edit|MultiEdit",
        "hooks": [{"type": "command", "command": "~/.claude/hooks/auto-sync.sh", "async": true, "timeout": 60}]
      }
    ]
  }
}
```

---

## GITHUB REPO STRUCTURE

All repos under `catalystmeded` GitHub org, local root `~/Projects/`.

| Repo | Purpose | Last Commit | Status |
|---|---|---|---|
| `cameos-mono` | CAMEOS pipeline code | `82bf0ff` (2026-03-05) | ✅ Clean — git history cleaned (268MB removed) |
| `shared-services` | Shared infrastructure layer | `edff6c4` (2026-03-05) | ✅ Clean — scraper + SI doc committed |
| `catalyst-mono` | Catalyst website build | 270bc80 | ✅ Clean |
| `techcelerate-mono` | TechCelerate platform | 2108c81 | ✅ Clean |

---

## SHARED SERVICES LAYER

**Repo:** `shared-services` | **Local:** `~/Projects/shared-services/`
**Restructure:** ✅ COMPLETE (2026-03-04). All components in `shared/` package.

**Current structure:**
```
~/Projects/shared-services/shared/
├── __init__.py
├── trace_logger/logger.py
├── consensus_engine/engine.py
├── model_router/router.py
├── exemplar_store/store.py
├── perplexity_client/client.py
├── scraper/scraper.py                  ← IR-01 COMPLETE
├── pdf_intelligence/extractor.py       ← IR-02 COMPLETE
├── schema_registry/                    ← NEW (M8 W4) ✅ LIVE
│   ├── registry.py
│   ├── pipeline_schemas.py
│   └── rfp_mappings/                   ← stub, funder-specific mapping configs
└── api_client/                         ← NEW (M8 W4) ✅ LIVE
    ├── client.py                       ← ResilientClient, exponential backoff
    └── decorators.py                   ← @resilient decorator
```

| Component | File | Status | Purpose |
|---|---|---|---|
| Trace Logger | `shared/trace_logger/logger.py` | ✅ Live + verified | Supabase pipeline logging |
| Consensus Engine | `shared/consensus_engine/engine.py` | ✅ Live | Claude-only mode |
| Model Router | `shared/model_router/router.py` | ✅ Live | Model selection routing |
| Exemplar Store | `shared/exemplar_store/store.py` | ✅ Live + POPULATED | 15 gold, 15 silver — wired to content_generator.py |
| Perplexity Client | `shared/perplexity_client/client.py` | ✅ Live | Citation verification |
| Web Scraper | `shared/scraper/scraper.py` | ✅ Live | Playwright + BS4, rate limiting |
| PDF Intelligence | `shared/pdf_intelligence/extractor.py` | ✅ Live | PyMuPDF + Claude Sonnet |
| **Schema Registry** | `shared/schema_registry/registry.py` | ✅ **NEW M8** | Validates all 5 pipeline pass schemas |
| **API Resilience Layer** | `shared/api_client/client.py` | ✅ **NEW M8** | Retry/fallback, exponential backoff, wired to Perplexity + PDF extractor |
| Prompt Registry | `shared/prompt_registry/` | ⬜ M9 | Version-controlled prompt library |

**Test suite:** 113/113 passing (2026-03-05)

---

## SUPABASE — DATABASE LAYER

**Project:** `catalyst-ai-platform` | **Region:** East US (N. Virginia)
**Status:** ✅ Live — 22 tables + 3 views

### Core Pipeline Tables (8)

`pipeline_traces`, `consensus_results`, `exemplar_store` (30 entries — 15 gold/15 silver), `failure_taxonomy`, `prompt_versions`, `observability_metrics`, `human_annotations`, `hitl_deltas` (19 columns, live 2026-03-05)

### Intelligence Tables (12)

`intelligence_events`, `opportunity_scores` (1,604 scores), `funder_fingerprints`, `kol_profiles`, `competitor_profiles`, `accme_providers` (**POPULATED M8**), `rems_programs` (100 programs, 28 flagged), `budget_calendar` (5 funders), `nexus_decisions` (**1,685 records — historical CRM seeded M8**), `adverse_event_signals` (20 signals), `congress_intelligence` (stub), `formulary_changes` (stub)

### Infrastructure Tables (2)

`scrape_cache` (24h TTL), `hitl_deltas` (**NEW M8** — HITL correction capture)

### Views (3)

`weekly_performance`, `failure_patterns`, `exemplar_effectiveness`

### Live Data Summary

| Table | Records | Notes |
|---|---|---|
| `exemplar_store` | 30 | 15 gold (≥0.90), 15 silver (0.85–0.89) — M8 seeded |
| `nexus_decisions` | 1,685 | Historical CRM load (1,082 from merge) + sprint data |
| `opportunity_scores` | 1,604 | Top: Lilly × Oncology × Live Symposium (56.4) |
| `adverse_event_signals` | 20 | FAERS 12-month; top: PREDNISONE 24,677 |
| `rems_programs` | 100 | 28 HCP-training flagged |
| `accme_providers` | Populated M8 | Sprint 7 ingestion via IR-02 |
| `hitl_deltas` | Live | Gold/Silver/Bronze tier capture |

---

## API KEYS STATUS

| Key | Env Var | Status | Notes |
|---|---|---|---|
| Anthropic | Max plan OAuth | ✅ Live | Claude Code — NOT API key billing |
| Anthropic API | `ANTHROPIC_API_KEY` | ✅ SET | Python API calls only |
| Supabase URL | `SUPABASE_URL` | ✅ SET | |
| Supabase Anon | `SUPABASE_ANON_KEY` | ✅ SET | |
| Supabase Service | `SUPABASE_SERVICE_KEY` | ✅ SET | |
| OpenAI | `OPENAI_API_KEY` | ✅ SET — all 3 repos | |
| Google AI Studio | `GOOGLE_API_KEY` | ✅ SET — all 3 repos | |
| Perplexity | `PERPLEXITY_API_KEY` | ✅ SET — all 3 repos | |
| GitHub PAT | `GITHUB_TOKEN` | ✅ SET — all 3 repos | |
| **Azure client secret** | In mcp.json + n8n ecosystem config | ✅ **ROTATED 2026-03-05** | SharePoint MCP auth |

**SHAREPOINT_DRIVE_ID:** ✅ Resolved and live in n8n (2026-03-05)

**CRITICAL — Max Plan vs API Billing:**
```bash
echo $ANTHROPIC_API_KEY  # Must return blank — if it returns a key, remove from ~/.zshrc immediately
```

---

## MCP CONFIGURATION

**Config file:** `~/.claude/.mcp.json` ✅ Valid JSON

| Server | Purpose | Status |
|---|---|---|
| Context7 | Library documentation | ✅ Configured |
| Supabase | Database operations | ✅ Configured |
| GitHub | Autonomous commits | ✅ Configured |
| Filesystem | File read/write | ✅ Configured |
| Microsoft Graph | Teams/SharePoint | ✅ Active — Azure secret rotated 2026-03-05 |

---

## n8n — WORKFLOW AUTOMATION

**Version:** 2.10.2 | **Status:** ✅ Running via pm2
**Access:** `http://localhost:5678` | **Autostart:** ✅ launchd plist

### All Live Workflows (19 total)

| Workflow ID | Name | Schedule | Channel | Status |
|---|---|---|---|---|
| 1001 | Daily Intelligence Digest | 6 AM daily | cameos-digest | ✅ Live |
| 1002 | PDUFA 90-Day Alert | 7 AM daily | cameos-alerts + Monday.com | ✅ Live |
| 1003 | Use-It-or-Lose-It Window | Sep/Oct/Nov 1 | cameos-alerts | ✅ Live |
| 1004 | NEXUS Decision Reminder | Monday 8 AM | cameos-alerts | ✅ Live |
| 1005 | Opportunity Score Monday Digest | Monday 6 AM | Teams/Slack | ✅ Live |
| 1006 | HITL Document Router | Event-triggered (DOCX upload) | cameos-alerts | ✅ Live |
| 1007 | L-13 SYNTHESIS Schedule | Sunday 11 PM | cameos-alerts on complete/error | ✅ Live M8 |
| 1008 | L-14 FINGERPRINT Schedule | Sunday 11 PM | cameos-alerts | ✅ Live M8 |
| 1009 | L-15 CONGRESS Schedule | Monday 5 AM | cameos-alerts | ✅ Live M8 |
| 1010 | L-16 SIGNAL Schedule | Daily 6 AM | cameos-alerts | ✅ Live M8 |
| 1011 | L-17 TEMPO Schedule | Monday 5 AM | cameos-alerts | ✅ Live M8 |
| 1012 | L-18 MANDATE MAP Schedule | Monday 6 AM | cameos-alerts | ✅ Live M8 |
| 1013 | L-19 VELOCITY Schedule | Daily 7 AM | cameos-alerts | ✅ Live M8 |
| 1014 | L-20 CLIFF WATCH Schedule | Tuesday 5 AM | cameos-alerts | ✅ Live M8 |
| 1015 | L-21 REMS RADAR Refresh | Monday 7 AM | cameos-alerts | ✅ Live M8 |
| 1016 | L-22 SENTINEL AE Refresh | Monday 7 AM | cameos-alerts | ✅ Live M8 |
| 1017 | L-23 KOL TRIANGLE Schedule | Tuesday 6 AM | cameos-alerts | ✅ Live M8 |
| 1018 | L-24 FORMULARY WATCH Schedule | Tuesday 6 AM | cameos-alerts | ✅ Live M8 |
| 1019 | L-07 APOLLO Schedule | Weekly Wednesday 6 AM | cameos-alerts | ✅ Live M8 |

**Workflow configs:** committed to `governance/n8n-workflows/`

**Planned (not yet built):**

| Workflow | Purpose | Project | Priority |
|---|---|---|---|
| 1020 | Monday CRM → NEXUS refresh | CAMEOS | High — define cadence before team onboarding |
| Monday Morning Ritual | 9am Teams nudge with weekly priorities | Cross-project | High |
| First Monday Monthly Checklist | Monthly maintenance trigger | Cross-project | High |
| New Vertical Launch | One-trigger: spec → content → load → SEO → email → social | TechCelerate | High (May 2026) |
| Weekly Content Monitor | Regulatory change scanner | TechCelerate | High (May 2026) |

### n8n Code Node Conventions (CRITICAL — do not deviate)

| Item | Rule |
|---|---|
| HTTP calls | Use `this.helpers.httpRequest()` — NOT native `fetch()` |
| Env access | `N8N_BLOCK_ENV_ACCESS_IN_NODE=false` in `~/n8n-ecosystem.config.js` |
| Webhook URL extraction | Use `cut -d= -f2-` not `cut -d= -f2` |
| Webhook URLs | Wrap in single quotes in curl |
| API version | Use `api-version=2024-10-01` — do NOT use `api-version=1` |

---

## CLAUDE CODE SETUP

| Item | Status | Notes |
|---|---|---|
| Version | 2.1.58+ | --chrome permanent default |
| Auth | ✅ Max plan OAuth | NOT API key billing |
| Agent Teams | ✅ Enabled | `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1` |
| Subagent model routing | ✅ Set | `CLAUDE_CODE_SUBAGENT_MODEL=claude-sonnet-4-6` in `~/.zshrc` |
| PostToolUse hook | ✅ Active | Auto-sync on file writes |
| Credential guard hook | ✅ Active | Blocks `.env`/`.key`/secret commits |
| Force-push block hook | ✅ Active | Blocks `git push --force` to main |
| Custom Skills | ✅ 6 deployed | 2 personal, 3 cameos-mono, 1 shared-services |
| Subagents | ✅ 6 deployed | cameos-mono/.claude/agents/ |
| Slash commands | ✅ 2 deployed | `/close`, `/status` |
| AgentShield scan | ✅ Run clean | `npx ecc-agentshield scan` |

---

## CLAUDE.MD HIERARCHY

```
~/.claude/CLAUDE.md                  ← Global rules (all repos) — v2.0 rewritten 2026-03-04
    ├── cameos-mono/CLAUDE.md        ← CAMEOS: oracle standards, failure taxonomy — v2.0
    ├── catalyst-mono/CLAUDE.md      ← Website: brand rules, WP structure — v2.0
    ├── techcelerate-mono/CLAUDE.md  ← TechCelerate: ASRT compliance, WP paths — v2.0
    └── shared-services/CLAUDE.md   ← Shared layer rules — v2.0
```

All 5 files rewritten v2.0 and committed 2026-03-04. Boris Cherny pattern: prune monthly, never just append.

---

## INTELLIGENCE LOOPS — FULL STATUS (Post-M8)

| Loop | Name | Status | n8n Workflow | Schedule |
|---|---|---|---|---|
| L-03 | PROMETHEUS | Existing/expanding | 1002 (PDUFA) | Daily 7 AM |
| L-07 | APOLLO | ✅ Scheduled M8 | 1019 | Wednesday 6 AM |
| L-08 | NEXUS | ✅ LIVE | — | Event-triggered + HITL delta |
| L-09 | CHRONOS | ✅ LIVE | — | CRM-sourced |
| L-13 | SYNTHESIS | ✅ Scheduled M8 | 1007 | Sunday 11 PM |
| L-14 | FINGERPRINT | ✅ Scheduled M8 | 1008 | Sunday 11 PM |
| L-15 | CONGRESS | ✅ Scheduled M8 | 1009 | Monday 5 AM |
| L-16 | SIGNAL | ✅ Scheduled M8 | 1010 | Daily 6 AM |
| L-17 | TEMPO | ✅ Scheduled M8 | 1011 | Monday 5 AM |
| L-18 | MANDATE MAP | ✅ Built + Scheduled M8 | 1012 | Monday 6 AM |
| L-19 | VELOCITY | ✅ Scheduled M8 | 1013 | Daily 7 AM |
| L-20 | CLIFF WATCH | ✅ Built + Scheduled M8 | 1014 | Tuesday 5 AM |
| L-21 | REMS RADAR | ✅ LIVE + Refresh M8 | 1015 | Monday 7 AM |
| L-22 | SENTINEL AE | ✅ LIVE + Refresh M8 | 1016 | Monday 7 AM |
| L-23 | KOL TRIANGLE | ✅ Scheduled M8 | 1017 | Tuesday 6 AM |
| L-24 | FORMULARY WATCH | ✅ Scheduled M8 | 1018 | Tuesday 6 AM |

**L-02 ORACLE, L-11 PHOENIX, L-12 FORGE:** M9 Sprint A — require accumulated NEXUS data first.

---

## NEXUS HISTORICAL DATA

**Source:** Merged from Monday.com CRM (board 8179275180) + Excel historical export
**Merge completed:** 2026-03-05 (Catalyst Strategy Project)
**Key file:** `nexus_historical_grants_2026-03-05.csv`
**Closure doc:** `CLOSURE_2026-03-05_NEXUS-GRANT-DATA-MERGE.md`

| Metric | Value |
|---|---|
| Total records loaded | 1,685 (1,082 from merge + sprint data) |
| Funders | 88 canonical (normalized from 268 raw) |
| Therapeutic areas | 157 canonical (normalized from 471 raw) |
| Date range | 7 years |
| Source tag | `monday_crm` / `excel_historical` / `both` |
| Blank funder records | 32 (Monday items — assigned to sales team) |

**Refresh cadence:** Define and build as n8n workflow 1020 before team onboarding.
**Architecture:** Excel/LAS = frozen historical (complete). Monday.com = live refresh source going forward.

---

## CAMEOS-DRIVE & SYNC

**Location:** `~/CAMEOS-Drive/`
**sync.sh:** ✅ `~/CAMEOS-Drive/automation-bin/sync.sh` — ran clean 2026-03-05
**Auto-sync:** ✅ PostToolUse hook active (5-min debounce)
**Manual sync:** Run before each build session and after any long gap.

---

## BUILD PATTERN — RALPH-LOOP (ALL PROJECTS)

```
Spec → Oracle → Generate → Evaluate → Iterate → Promote
```

- Spec first. No code before oracle exists.
- Oracle defines done.
- Two failed fixes = rewrite. Not a third attempt.
- Agent Teams standard for 3+ parallel tasks with no file overlap.

---

## CHAT STRUCTURE — WHERE DECISIONS LIVE

| Chat | Purpose |
|---|---|
| **Catalyst Command Post** | Master orchestrator. ALL cross-project decisions. W6 governance. |
| **CAMEOS M8 Orchestrator** | W1–W5 build execution tracking (M8 complete — archive after Lilly run) |
| **CAMEOS Agent Registry** | v2 agent architecture reconciliation (ChatGPT extraction in progress) |
| **CAMEOS project** | Active build sprint chat |
| **TechCelerate project** | LMS, ASRT, courses, payments |
| **Website Build chat** | WordPress conversion (opens when assets uploaded) |
| **IP Moat chat** | Trade secrets, evaluator chain patent potential |
| **Build Methodology** | Philosophy + stack decisions only. Never execution. |

---

## CROSS-PROJECT DECISIONS (updated 2026-03-05)

| Decision | Status |
|---|---|
| TechCelerate post-launch: blitz zero-accreditation compliance verticals | ✅ Approved |
| Automation machine build: May–Jun 2026 | ✅ Approved |
| CAMEOS/TC shared patterns → shared-services repo | ✅ Complete |
| Employer Dashboard: Sprint 4 (Sep–Oct 2026) | ✅ Approved |
| Entity structure: no change yet | ⬜ Holding |
| Brand scope (TechCelerate vs. new entity) | ❓ OPEN — decide before fall 2026 |
| Agent Teams as standard build methodology | ✅ Active — proven in M8 |
| M8 COMPLETE — all 5 windows done, 113/113 tests | ✅ 2026-03-05 |
| NEXUS historical grant merge (1,082 records, 88 funders) | ✅ 2026-03-05 |
| AWS hosting: defer until first external funder demo | ✅ Decision locked |
| Team access via Tailscale (not AWS yet) | ✅ Decision locked |
| Monday CRM → NEXUS refresh cadence | ❓ OPEN — define before team onboarding |
| CAMEOS Review product scoping | ⬜ M9 Sprint D |
| CAMEOS entity formalization | ⬜ After IP Moat memo |

---

## CROSS-PROJECT BACKLOG

### Infrastructure

| Item | Project | Priority | Status |
|---|---|---|---|
| Run sync.sh before each build session | All | Always | ✅ Auto-sync active |
| Tailscale setup — MAC-MOLT + team devices | CAMEOS | 🔴 High | ⬜ Before team access |
| n8n workflow 1020 — Monday CRM → NEXUS refresh | CAMEOS | 🔴 High | ⬜ Before team onboarding |
| Uptime Robot — add domains | All | Medium | ⬜ As domains identified |
| Google Search Console — verify all 3 sites | All | Medium | 🟡 In progress |
| Install UI/UX Pro Max Skill on MAC-MOLT | Website | Medium | ⬜ Before Website Build session |
| Cowork Weekly Regulatory Monitor scheduled task | TechCelerate | Medium | ⬜ 10 min browser setup |
| TechCelerate skills (3 Cowork) | TechCelerate | High | ⬜ May 2026 |
| TechCelerate subagents (4 Code) | TechCelerate | High | ⬜ May 2026 |
| Batch API for CAMEOS bulk proposals | CAMEOS | Medium | ⬜ M9 |
| Prompt caching for content pipeline | TechCelerate + CAMEOS | High | ⬜ May 2026 |

### CAMEOS

| Item | Priority | Status |
|---|---|---|
| Exemplar store population | ✅ COMPLETE M8 | 15 gold, 15 silver seeded |
| Schema Registry | ✅ COMPLETE M8 | 113/113 tests |
| API Resilience Layer | ✅ COMPLETE M8 | Wired to Perplexity + PDF extractor |
| IR-07 Intelligence Dashboard | ✅ COMPLETE M8 | 6 sections, live Supabase data |
| All 13 intelligence loops scheduled | ✅ COMPLETE M8 | n8n 1007–1019 |
| ACCME Sprint 7 data ingestion | ✅ COMPLETE M8 | accme_providers populated |
| NEXUS historical seeded | ✅ COMPLETE M8 | 1,685 records |
| L-07 APOLLO name fix | ✅ COMPLETE M8 | Loop name + 3 column corrections |
| **Lilly proposal** | 🔴 **NEXT** | First fully-instrumented end-to-end run |
| **Tailscale setup** | 🔴 **NEXT** | Required for team access |
| **n8n workflow 1020** | 🔴 **NEXT** | Monday CRM → NEXUS refresh cadence |
| Master Book session (Q11/Q12/F3 → §P.11/P.12) | 🟠 High | DEC-072 to assign |
| Budget integration (budget_agent.py wired) | 🟠 M9 P1 | Built, not wired |
| 32 blank funder records | 🟡 Medium | Assign to sales team (item IDs in closure doc) |
| IP Moat memo for lawyer | 🟡 High | Not started |
| CAMEOS entity formalization | ⬜ Strategic | After IP Moat memo |
| Human calibration study | ⬜ Critical | Most important unfinished governance item |
| AWS migration | ⬜ M9 | Defer until first external funder demo |

### TechCelerate

| Item | Priority | Status |
|---|---|---|
| ASRT accreditation submission | 🔴 April 25 deadline | In progress |
| Content generation pipeline (Claude API) | High — May 2026 | Not started |
| Course loading automation (WP REST API) | High — May 2026 | Not started |
| Programmatic SEO system | High — May 2026 | Not started |
| File sexual harassment state apps (CA, NY, IL) | High — May 2026 | Not started |
| n8n New Vertical Launch workflow | High — June 2026 | Not started |
| Employer Dashboard MVP | High — Sep 2026 | Not started |
| MailChimp → FluentCRM + SES | Medium | Planned |

### Strategy / Cross-Project

| Item | Priority | When |
|---|---|---|
| BLS OES data download | Low — free, 10 min | Now |
| Google Search Console setup | Medium — free | Now |
| Brand scope decision | Open | Before May 2026 |
| Cancel Asana ($324/yr) | Low | Any time |
| RNA team demo | Medium | After Lilly proposal confirmed clean |

---

## KEY REPO PATHS (do not rediscover)

```
~/Projects/cameos-mono/tools/packaging/                     ← 5-pass pipeline scripts
~/Projects/cameos-mono/tools/packaging/tracked_change_injector.py  ← Q11
~/Projects/cameos-mono/tools/packaging/delta_ingestion_pipeline.py ← Q12
~/Projects/cameos-mono/tools/intelligence/                  ← intelligence loop scripts
~/Projects/cameos-mono/pipeline-outputs/ensemble-best/      ← working input format
~/Projects/cameos-mono/pipeline-outputs/real-proposals/     ← M5/M6/M7 output
~/Projects/cameos-mono/golden-examples/extractions/         ← 104 JSON extractions
~/Projects/cameos-mono/governance/                          ← decision log, master book
~/Projects/cameos-mono/governance/intelligence/             ← Intelligence Architecture v2
~/Projects/cameos-mono/governance/n8n-workflows/            ← n8n workflow configs (19 exported)
~/Projects/cameos-mono/data/historical/                     ← nexus_historical_grants_2026-03-05.csv
~/Projects/cameos-mono/.claude/agents/                      ← 6 specialist subagents
~/Projects/cameos-mono/.claude/skills/                      ← 3 project skills
~/Projects/shared-services/shared/                          ← all shared components
~/Projects/shared-services/shared/schema_registry/          ← NEW M8
~/Projects/shared-services/shared/api_client/               ← NEW M8
~/Projects/shared-services/shared/scraper/                  ← IR-01
~/Projects/shared-services/shared/pdf_intelligence/         ← IR-02
~/Projects/shared-services/migrations/                      ← SQL migration scripts
~/.claude/skills/                                           ← 2 personal skills
~/.claude/hooks/auto-sync.sh                                ← PostToolUse auto-sync
~/.claude/settings.json                                     ← Agent Teams + hooks config
~/CAMEOS-Drive/automation-bin/sync.sh                       ← sync script
```

---

## OWNERSHIP DECISION MATRIX

| Component | Catalyst | TechCelerate | Shared-Services |
|---|---|---|---|
| WordPress + LMS + theme | | ✅ | |
| Course content (RT) | | ✅ hosts + sells | |
| Content generation pipeline (Claude API) | | ✅ | |
| CAMEOS pipeline + builds | ✅ | | |
| Shared trace logger, consensus, model router, schema registry, API resilience | | | ✅ |
| n8n workflows (TechCelerate) | | ✅ | |
| n8n workflows (Catalyst/CAMEOS) | ✅ | | |
| GitHub Actions CI/CD | ✅ per-repo | ✅ per-repo | ✅ per-repo |
| IP Moat / entity strategy | ✅ decides | | |
| NEXUS historical data | ✅ | | |
| AWS migration (when triggered) | ✅ | | |

**Decision rule:** Ownership ambiguity → bring to Catalyst Command Post before starting.

---

*Upload to: Catalyst Command Post, CAMEOS Project, TechCelerate Project, Infrastructure Setup chat*
*Re-upload when: major stack decision, new tool confirmed, or API key status changes*
*Previous versions: v1.1 (2026-02-25), v2.0 (2026-03-03), v2.1 (2026-03-03), v2.2 (2026-03-04), v2.3 (2026-03-04), v2.4 (2026-03-04)*
*Last updated: 2026-03-05 v2.5 — M8 COMPLETE: exemplar store seeded, 13 loops scheduled, ACCME ingested, NEXUS historical loaded (1,685 records), Schema Registry + API Resilience built, IR-07 dashboard live, Azure secret rotated, git history cleaned*
