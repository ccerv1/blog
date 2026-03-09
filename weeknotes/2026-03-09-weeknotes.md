# Weeknotes: March 2–8, 2026

My focus this past week has been on chaining together workflows so agents can execute end-to-end data projects. I'm getting pretty good results with my test cases, but struggling to handle some real-world ingestion jobs. Every API is a snowflake.

---

## Process Upgrades

- **Unsupervised agents.** I had a 14 hour flight with good wifi and used it to build an orchestrator that manages multi-step data projects (ingest data, build models, create a notebook). It currently taps into 20+ custom skills, including a /babysitter to monitor for stuck states and a /housekeeper to clean up when a project is complete.

- **MCP nirvana.** We've been wrapping all of our API calls in MCP tools. This means a workflow is now just a series of tool calls. I'm still wrestling with good systems for polling jobs (and kicking off parallel work while waiting for a job to complete) and intelligent backtracking when a job fails or delivers bad data.

- **Multi-agent document production.** I used three agents in parallel on a research and writing project: one stripped the template and created a new one, one researched and drafted new content, one populated the final document and cleaned it up. First time I've used parallel agents on writing rather than code.

## New Experiments

- **Writing aides.** I got fed up with the slop I was getting when asking Claude to write memos. Plus, it was tedious editing and then manually adding exhibits. So I built a script that read through all of my public and private writing, categorized it, and distilled different styles for different types of docs and audiences. Right now it's good for technical explanations, but not for other stuff. For instance, it failed miserably with this post — so I'm handrolling it. I am, however, using it to generate the session evidence for this post.

- **Time tracking.** Had Claude estimate my weekly time allocation across projects based on completed tickets, then compared it to my own manual log. It underweighted context-switching and overweighted long sessions. Not accurate enough to replace the spreadsheet, but useful for spotting weeks where reality drifted from the plan.

## Good Reads

- **[Tech is Going to Get Much Bigger](https://www.notboring.co/p/tech-is-going-to-get-much-bigger)** — 2023 piece that feels very relevant in 2026. Packy McCormick argues that as energy, intelligence, and dexterity approach zero marginal cost, the entire $45T global labor market becomes addressable by tech-native companies.
- **[Mozilla Data Collective](https://datacollective.mozillafoundation.org/datasets)** — 470+ community-controlled datasets. It's heavy on minority language corpora and speech datasets. Interesting as a model for open data commons: share data, retain ownership, control who uses it downstream.
- **[Jamie Quint essay](https://x.com/jamiequint/status/2029705203457609785)** — Makes the case that semantic layers are dead, replaced by AI agents that investigate raw source truth at query time. The "quirk store" concept (a pgvector-backed knowledge base of learned corrections) is clever — it's basically institutional knowledge that accrues automatically. Claims one hire replaced five planned ones.

## This Week in Numbers

### By the Numbers

- 778 messages across 43 sessions
- Longest session had 121 messages
- Usage up ~12% from last week (692 msgs / 45 sessions)

### What I Did

| Activity | Share |
|----------|-------|
| Skill & agent building | 33% |
| Data modeling, analysis & SQL | 35% |
| Debugging & code reviews | 11% |
| Research & writing | 8% |
| Notebook dev | 7% |
| Other | 6% |

### Work Schedule

- Peak hours: 7am, 11am, 4pm
- Busiest day: Thursday (211 msgs); quietest: Saturday (6 msgs)
- Saturday and Sunday were basically off

### Trends

- Skill & agent building dominated the non-conversational work — consistent with the orchestrator push
- The dominant workflow loop is: write skill → test in orchestrator → hit edge case → fix → repeat
- Client project work accounts for ~40% of messages, with the rest being platform/tooling/skill development
- Heavy /mcp usage reflects all the tool-wrapping work this week
