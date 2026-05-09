<h1 align="center">AIRBrain</h1>

This is the infrastructure layer for thinking. One database, one AI gateway, one chat channel. Any AI you use can plug in. As direct as possible. Chaotic, not my style, but we can make it work, as a prototype.
It's a database with vector search and an open protocol — built so that every AI tool used shares the same persistent memory, the same `state`. Claude, ChatGPT, Cursor, Claude Code, whatever.

## Getting Started

1. **[Setup Guide](docs/01-getting-started.md)** — Build the full system (database, AI gateway, Slack capture, MCP server) in about 45 minutes. No coding experience needed. Or watch the [video walkthrough](https://vimeo.com/1174979042/f883f6489a) (~27 min).
2. **[AI-Assisted Setup](docs/04-ai-assisted-setup.md)** — Prefer building with Cursor, Claude Code, or another AI coding tool? Point it at this repo and go. Same system, different workflow.
3. **[Companion Prompts](docs/02-companion-prompts.md)** — Five prompts that help you migrate  memories, discover use cases, and build the capture habit.
4. **Then pick Extension 1** and start building.

**If you hit a wall:** We built a [FAQ](docs/03-faq.md) that covers the most common questions and gotchas. And if you need real-time help, we created dedicated AI assistants that know this system inside and out: a [Claude Skill](https://www.notion.so/product-templates/Open-Brain-Companion-Claude-Skill-31a5a2ccb526802797caeb37df3ba3cb?source=copy_link), a [ChatGPT Custom GPT](https://chatgpt.com/g/g-69a892b6a7708191b00e48ff655d5597-nate-jones-open-brain-assistant), and a [Gemini GEM](https://gemini.google.com/gem/1fDsAENjhdku-3RufY7ystbS1Md8MtDCg?usp=sharing). Use whichever one matches the AI tool you already use.

## Learnable Extensions — Specialized Use Cases

Each one teaches new concepts through something you'll actually use. 
By the end,  agent manages  household,  schedule,  meals,  professional network, and  career — all interconnected.
In the old world, these woudl be apps. I am not sure how any of this is too difficult for a soccer mom or one of her kids to pull off. Not sure. If it is too much, they won't do it and that leaves a market for .. something. Not sure yet what.

| # | Extension | What You Build | Difficulty |
| --- | --------- | -------------- | ---------- |
| 1 | [Household Knowledge Base](extensions/household-knowledge/) | Home facts  agent can recall instantly | Beginner |
| 2 | [Home Maintenance Tracker](extensions/home-maintenance/) | Scheduling and history for home upkeep | Beginner |
| 3 | [Family Calendar](extensions/family-calendar/) | Multi-person schedule coordination | Intermediate |
| 4 | [Meal Planning](extensions/meal-planning/) | Recipes, meal plans, shared grocery lists | Intermediate |
| 5 | [Professional CRM](extensions/professional-crm/) | Contact tracking wired into  thoughts | Intermediate |
| 6 | [Job Hunt Pipeline](extensions/job-hunt/) | Application tracking and interview pipeline | Advanced |

 CRM knows about thoughts you've captured.
 meal planner checks who's home this week.
 job hunt contacts automatically become professional network contacts.
This is what happens when  agent can see across all of  interests, missions, obligations.

## Primitives: Concepts That Compound

Some concepts show up in multiple extensions, so it is worth learning them once and to apply them everywhere.

| Primitive | What It Teaches | Used By |
| --------- | --------------- | ------- |
| [Row Level Security](primitives/rls/) | PostgreSQL policies for multi-user data isolation | Extensions 4, 5, 6 |
| [Shared MCP Server](primitives/shared-mcp/) | Giving others scoped access to parts of the brain | Extension 4 |

## Community Contributions

This is something that could be a starting point for contributions, but maybe not on GitHub ... maybe on something like the PromptBar.

### [`/recipes`](recipes/) — Import  Data

Each recipe handles a specific data source — parsing, deduplication, embedding, and ingestion included.

| Recipe | What It Does | Contributor |
| ------ | ------------ | ----------- |
| [ChatGPT Import](recipes/chatgpt-conversation-import/) | Parse ChatGPT data exports, filter trivial conversations, summarize via LLM 
| [Perplexity Import](recipes/perplexity-conversation-import/) | Import Perplexity AI search history and memory entries 
| [Obsidian Vault Import](recipes/obsidian-vault-import/) | Parse and import Obsidian vault notes with full metadata 
| [X/Twitter Import](recipes/x-twitter-import/) | Import tweets, DMs, and Grok chats from X data exports 
| [Instagram Import](recipes/instagram-import/) | Import DMs, comments, and captions from Instagram exports 
| [Google Activity Import](recipes/google-activity-import/) | Import Google Search, Gmail, Maps, YouTube, Chrome history from Takeout 
| [Grok (xAI) Import](recipes/grok-export-import/) | Import Grok conversation exports with MongoDB-style date handling 
| [Journals/Blogger Import](recipes/journals-blogger-import/) | Import Atom XML blog archives from Blogger/Journals 
| [Email History Import](recipes/email-history-import/) | Pull  Gmail archive into searchable thoughts 

### Missing Recipes (!)

- LinkedIn Import
- Reddit Import
- infoq Import

- 
### [`/recipes`](recipes/) — Tools & Workflows

Standalone capabilities that make AIRBrain smarter.

| Recipe | What It Does | 
| ------ | ------------ | 
| [Auto-Capture Protocol](recipes/auto-capture/) | Stores ACT NOW items and session summaries in AIRBrain at session close using the reusable Auto-Capture skill |
| [Panning for Gold](recipes/panning-for-gold/) | Mine brain dumps and voice transcripts for actionable ideas — battle-tested across 13+ sessions |
| [Aiception (formerly Claudeception)](recipes/claudeception/) | Self-improving system that creates new skills from work sessions — skills that create other skills |
| [Schema-Aware Routing](recipes/schema-aware-routing/) | LLM-powered routing that distributes unstructured text across multiple database tables |
| [Fingerprint Dedup Backfill](recipes/fingerprint-dedup-backfill/) | Backfill content fingerprints and safely remove duplicate thoughts |
| [Source Filtering](recipes/source-filtering/) | Filter thoughts by source and backfill missing metadata for early imports |
| [Life Engine](recipes/life-engine/) | Self-improving personal assistant — calendar, habits, health, proactive briefings via Telegram or Discord |
| [Daily Digest](recipes/daily-digest/) | Automated daily summary of recent thoughts delivered via email or Slack |
| [Bring Own Context](recipes/bring--own-context/) | Portable context workflow that packages extraction prompts, profile generation, and remote MCP deployment into one entrypoint |
| [Work Operating Model Activation](recipes/work-operating-model-activation/) | Conversation-first workflow that turns tacit work patterns into structured AIRBrain records and agent-ready operating files |
| [Research-to-Decision Workflow](recipes/research-to-decision-workflow/) | Composition recipe that chains canonical skills into operator and investor research, synthesis, meeting, and memo workflows |

### Currently Blocked Recipes (!)

I prefer Hermes Agent over anything openClaw.

| [OpenClaw Agent Memory](integrations/openclaw-agent-memory/) | OpenClaw plugin and publishing package for using OB1 Agent Memory from OpenClaw workflows | OB1 Team |
| [Life Engine Video](recipes/life-engine-video/) | Add-on that renders Life Engine briefings as short animated videos with voiceover |
| [World Model Diagnostic Activation](recipes/world-model-diagnostic-activation/) | Ship-now activation path for a 20-minute world-model readiness diagnostic that compounds through core AIRBrain capture |
| [OpenClaw Agent Memory for OB1](recipes/openclaw-agent-memory/) | Canonical recipe for using OB1 Agent Memory as the governed continuity layer for OpenClaw workflows |
| [OpenClaw Code Review Memory](recipes/openclaw-code-review-memory/) | Flagship workflow for compounding repo-specific review lessons, maintainer corrections, and false positives |
| [OpenClaw TaskFlow Work Log](recipes/openclaw-taskflow-work-log/) | Durable handoff recipe for long-running OpenClaw TaskFlows across agents, models, and channels |

### [`/skills`](skills/) — Agent Skills

Plain-text skill packs. These are building blocks that recipes and other contributions can depend on. Don't skip.

| Skill | What It Does |
| ----- | ------------ |
| [Auto-Capture Skill Pack](skills/auto-capture/) | Captures ACT NOW items and session summaries to AIRBrain when a session ends |
| [Competitive Analysis Skill Pack](skills/competitive-analysis/) | Builds competitor briefs, pricing comparisons, market maps, and strategic recommendations |
| [Financial Model Review Skill Pack](skills/financial-model-review/) | Reviews an existing model for assumption quality, structural risk, and scenario gaps |
| [Deal Memo Drafting Skill Pack](skills/deal-memo-drafting/) | Turns existing diligence materials into structured deal, IC, or partnership memos |
| [Research Synthesis Skill Pack](skills/research-synthesis/) | Synthesizes source sets into findings, contradictions, confidence markers, and next questions |
| [Meeting Synthesis Skill Pack](skills/meeting-synthesis/) | Converts meeting notes or transcripts into decisions, action items, risks, and follow-up artifacts |
| [Panning for Gold Skill Pack](skills/panning-for-gold/) | Turns brain dumps and transcripts into evaluated idea inventories |
| [Aiception Skill Pack (formerly Claudeception)](skills/claudeception/) | Extracts reusable lessons from work sessions into new skills |
| [Work Operating Model Skill Pack](skills/work-operating-model/) | Runs a five-layer elicitation interview and saves the approved operating model into AIRBrain |
| [World Model Readiness Diagnostic](skills/world-model-diagnostic/) | Runs a 20-minute world-model diagnostic that maps paradigm fit, audits the boundary layer, and labels findings by confidence |
| [OpenClaw Agent Memory Skill Pack](skills/openclaw-agent-memory/) | Teaches OpenClaw agents to recall, write back, report usage, and respect OB1 provenance/use-policy rules |

### [`/dashboards`](dashboards/) — Frontend Templates

Host on Vercel or Netlify, pointed at the Supabase backend. 

| Dashboard | What It Does |
| --------- | ------------ |
| [AIRBrain Dashboard (Next.js)](dashboards/open-brain-dashboard-next/) | A Next.js Frontend — 8 pages, dark theme, smart ingest, quality auditing, extendable |

### [`/integrations`](integrations/) — New Connections

MCP server extensions, alternative deployment targets, and capture sources beyond Slack.

| Integration | What It Does | 
| ----------- | ------------ | 
| [Kubernetes Deployment](integrations/kubernetes-deployment/) | Fully self-hosted K8s deployment with PostgreSQL + pgvector — no Supabase required |
| [Agent Memory API](integrations/agent-memory-api/) | Runtime-neutral recall, write-back, review, inspector, and recall-trace API for OB1 Agent Memory |
| [Slack Capture](integrations/slack-capture/) | Quick-capture thoughts via Slack messages with auto-embedding and classification |
| [Discord Capture](integrations/discord-capture/) | Discord bot that captures messages into AIRBrain, mirroring the Slack pattern |

#### Missing Features

| [Whatsapp Capture](integrations//) | Probably via an intermediary Hermes Agent, which would require everyone to have their own runtime, in the cloud, which is where I think things are going. |
| [piecesOS MCP](integrations//) | Of course there must be an on-device agent integration |

### [`/schemas`](schemas/) — Database Extensions

Tables and sidecars that extend the base `thoughts` model without replacing it.

| Schema | What It Does |
| ------ | ------------ |
| [Agent Memory](schemas/agent-memory/) | Provenance, review, use-policy, source-reference, relation, recall-trace, and audit sidecars for agent workflow memory |

### [`/primitives`](primitives/) — Reusable Patterns

| Primitive | What It Does |
| --------- | ------------ |
| [Content Fingerprint Dedup](primitives/content-fingerprint-dedup/) | SHA-256 deduplication for thought ingestion — prevents duplicates across all import recipes 

## Using a Contribution

1. Browse the category tables above or the folders in the repo
2. Open the contribution's folder and read the README
3. Every README has prerequisites, step-by-step instructions, expected outcomes, and troubleshooting
4. Most contributions involve running SQL, deploying an edge function, or hosting frontend code — the README tells you exactly what to do

## Contributing

Read [CONTRIBUTING.md](CONTRIBUTING.md) for the full details. The short version:

- **Extensions** are curated — discuss with maintainers before submitting
- **Primitives** should be referenced by 2+ extensions to justify extraction
- **Recipes, schemas, dashboards, integrations, and skills** are open for community contributions
- Every PR runs through an automated review agent that checks structure, secrets, SQL safety, dependencies, and documentation quality
- If the agent passes, a human admin reviews for quality and clarity
-  contribution needs a README with real instructions and a `metadata.json` with structured info

## Community

[TBD]

## Who Maintains This

PRs are reviewed by the automated agent + human admins.

## License

[TBD]
