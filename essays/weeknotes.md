### Weeknotes: an experiment in measuring my own work

*March 2026*

I spend my days building systems that measure other people's work. In March 2026, I pointed the instruments at myself.

The setup: for three weeks, I had Claude read through my session history and draft a weekly report — what I shipped, what I experimented with, what I read, and a statistical breakdown of where my time actually went. I edited the drafts by hand (the writing aide I built for this "failed miserably," as I noted at the time) but the evidence was compiled programmatically: message counts, session lengths, activity categories, peak working hours.

Three weeks of data was enough to learn a few things.

**The numbers don't lie, and they're a little embarrassing.** Week one: peak hours at 7am, 11am, and 4pm, weekends off. Week two, with deadlines: peaks at 10pm, 12pm, and 4am, no days off. The time-tracking experiment from week one foreshadowed this — when I had Claude estimate my weekly time allocation and compared it to my own manual log, the two disagreed in ways that were more informative than either number alone.

**Building is cheap; refining is expensive.** The consistent theme across all three weeks. Claude is miraculously good at getting something out of the gate and tedious at polishing it. Week one was building an orchestrator on a 14-hour flight. Week two was paying the polish tax on hard deadlines. Week three was containerizing everything so the whole system could run unsupervised with more peace of mind.

**Measurement changes behavior slowly, and honesty about it is the point.** Writing "no real days off this week" in a public document does more for your calendar than any productivity app.

I paused the practice after three weeks. The raw entries follow, preserved as written.

---

## Weeknotes: March 2–8, 2026

My focus this past week has been on chaining together workflows so agents can execute end-to-end data projects. I'm getting pretty good results with my test cases, but struggling to handle some real-world ingestion jobs. Every API is a snowflake.

---

### Process Upgrades

- **Unsupervised agents.** I had a 14 hour flight with good wifi and used it to build an orchestrator that manages multi-step data projects (ingest data, build models, create a notebook). It currently taps into 20+ custom skills, including a /babysitter to monitor for stuck states and a /housekeeper to clean up when a project is complete.

- **MCP nirvana.** We've been wrapping all of our API calls in MCP tools. This means a workflow is now just a series of tool calls. I'm still wrestling with good systems for polling jobs (and kicking off parallel work while waiting for a job to complete) and intelligent backtracking when a job fails or delivers bad data.

- **Multi-agent document production.** I used three agents in parallel on a research and writing project: one stripped the template and created a new one, one researched and drafted new content, one populated the final document and cleaned it up. First time I've used parallel agents on writing rather than code.

### New Experiments

- **Writing aides.** I got fed up with the slop I was getting when asking Claude to write memos. Plus, it was tedious editing and then manually adding exhibits. So I built a script that read through all of my public and private writing, categorized it, and distilled different styles for different types of docs and audiences. Right now it's good for technical explanations, but not for other stuff. For instance, it failed miserably with this post — so I'm handrolling it. I am, however, using it to generate the session evidence for this post.

- **Time tracking.** Had Claude estimate my weekly time allocation across projects based on completed tickets, then compared it to my own manual log. It underweighted context-switching and overweighted long sessions. Not accurate enough to replace the spreadsheet, but useful for spotting weeks where reality drifted from the plan.

### Good Reads

- **[Tech is Going to Get Much Bigger](https://www.notboring.co/p/tech-is-going-to-get-much-bigger)** — 2023 piece that feels very relevant in 2026. Packy McCormick argues that as energy, intelligence, and dexterity approach zero marginal cost, the entire $45T global labor market becomes addressable by tech-native companies.
- **[Mozilla Data Collective](https://datacollective.mozillafoundation.org/datasets)** — 470+ community-controlled datasets. It's heavy on minority language corpora and speech datasets. Interesting as a model for open data commons: share data, retain ownership, control who uses it downstream.
- **[Jamie Quint essay](https://x.com/jamiequint/status/2029705203457609785)** — Makes the case that semantic layers are dead, replaced by AI agents that investigate raw source truth at query time. The "quirk store" concept (a pgvector-backed knowledge base of learned corrections) is clever — it's basically institutional knowledge that accrues automatically. Claims one hire replaced five planned ones.

### This Week in Numbers

#### By the Numbers

- 778 messages across 43 sessions
- Longest session had 121 messages
- Usage up ~12% from last week (692 msgs / 45 sessions)

#### What I Did

| Activity | Share |
|----------|-------|
| Skill & agent building | 33% |
| Data modeling, analysis & SQL | 35% |
| Debugging & code reviews | 11% |
| Research & writing | 8% |
| Notebook dev | 7% |
| Other | 6% |

#### Work Schedule

- Peak hours: 7am, 11am, 4pm
- Busiest day: Thursday (211 msgs); quietest: Saturday (6 msgs)
- Saturday and Sunday were basically off

#### Trends

- Skill & agent building dominated the non-conversational work — consistent with the orchestrator push
- The dominant workflow loop is: write skill → test in orchestrator → hit edge case → fix → repeat
- Client project work accounts for ~40% of messages, with the rest being platform/tooling/skill development
- Heavy /mcp usage reflects all the tool-wrapping work this week

---

## Weeknotes: March 9–15, 2026

I had a few hard deadlines this past week, so most of my time went to polishing. Claude is miraculously good at helping you build something out of the gate. It is tedious at refining.

Relatedly: while many AI businesses are using input-based pricing (ie, metering usage or seats), the real value will be in some form of verifiable outcome-based pricing. The opportunity is tracking outcomes that are not just cost savings / productivity gains.

---

### Process Upgrades

- **I'm starting to treat skill changes like code changes.** After hastily trying to compress a few of my largest skills docs, I noticed my workflows weren't performing as well as they used to. I wrote something halfway between an eval and a regression test, confirmed the degradation, and reverted.

- **Breaking ground on the data catalog.** I built a v1 system for documenting public data models — schema, lineage, business logic, best practices — so agents can reference them during analysis projects. This will no doubt evolve a lot.

- **Another reminder to ignore sunk costs.** I had two projects this past week that just felt off. Successive attempts to fix them made them worse. So I documented everything, hit a hard reset, and rebuilt them. In both cases, I moved faster by selectively feeding the good parts of the old project into the new one, rather than trying to salvage the old one.

### New Experiments

- **Programmatic video with Remotion.** The biggest experiment of the week. [Remotion](https://www.remotion.dev/) is a React-based framework for composing video programmatically — components, props, and a dev server with frame-by-frame scrubbing. The learning curve is real (my longest session of the week, by far), but once you internalize the mental model, iteration can be fast. Their licensing model is a breath of fresh air.

- **Agent-friendly sprint planning.** It's obvious that planning and review will be the bottlenecks of the development process going forward. I did a pseudo-quantitative analysis on my team's issue tracking over the past 12 weeks to assess how "agent-friendly" we've been. I enjoyed Claude's labeling of each person's style: some people use Linear as a personal to-do list, some use it to delegate and throw over the fence, and some over-specify the process and under-specify the outcome (me).

### Good Reads

- **[Chrome's native agent support](https://x.com/addyosmani/status/2032875051830358197)** — Chrome DevTools now exposes your real, signed-in browser to coding agents via MCP. No extensions, no headless browser, no separate logins. One toggle. Curious to try this out.

- **[Claude's interactive charts](https://x.com/claudeai/status/2032124273587077133)** — The rumor: Claude ships a new feature and kills a thousand startups. The reality: possibly cool, but I think we are still a long way from one-shotting the killer chart.

- **[Self-hosting as existential requirement](https://x.com/spengrah/status/2031943507389059128)** — As companies move institutional knowledge into agentic context graphs, controlling that data becomes existential. All performance on top of models comes from context, which means feeding agents your most sensitive data, which means self-hosting at scale. Good take.

### This Week in Numbers

#### By the Numbers

- 943 messages across 40 sessions
- Longest session had 166 messages
- Usage up ~21% from last week (778 msgs / 43 sessions)

#### What I Did

| Activity | Share |
|----------|-------|
| Demo video | 37% |
| Client work & data modeling | 28% |
| Skill & agent building | 15% |
| Debugging & code reviews | 10% |
| Research & writing | 7% |
| Other | 3% |

#### Work Schedule

- Peak hours: 10pm, 12pm, 4am
- Busiest day: Tuesday (255 msgs); quietest: Thursday (19 msgs)
- Work spread across all 7 days — no real days off this week between a long flight and the deadlines

---

## Weeknotes: March 16–22, 2026

I moved my entire Claude Code environment into a containerized setup. Now I can run in yolo mode with more peace of mind. The exercise also forced me to deal with how many of my workflows had hardcoded paths and implicit dependencies.

---

### Process Upgrades

- **Containerized everything.** The single biggest change this week. All my Claude Code workflows now run inside a devcontainer. Still working out some rough edges.

- **Data visualization as a quality standard.** I created my own version of [Tufte principles](https://x.com/randal_olson/status/2034978267397313021) as a skill that agents can reference during notebook development. Then extended it with a few other profiles from people whose work I have on my bookshelf (Bertin, Few, Wilkinson, Cairo). Skills are not a moat.

- **Data marketplace guides as agent context.** Built more structured guides for public data models so agents can reference schema, lineage, and best practices during analysis projects.

- **Programmatic slide decks.** Rolled my own HTML to PPTX converter to produce presentations directly from notebook data. Charts export as SVGs, data tables render cleanly, and the whole thing rebuilds from source. Still fiddly (font sizes, annotation placement), but the goal is to never touch PowerPoint or Google Slides again.

### New Experiments

- **TikTok meets Hacker News.** Short demo videos (2-5 min) of things people have built, presented in a social feed format. This was a shower thought inspired by overhearing a non-technical person describe a tool they built. However, unlike most shower thoughts, I gave it to Claude and created a simple wireframe that looks kinda decent.

### Good Reads

- **[The Tufte Test](https://x.com/randal_olson/status/2034978267397313021)** — Randal Olson encoded Tufte's visualization principles into an API, pointed an AI agent at it, and watched it self-correct from a generic chart to a genuinely good one in two prompts. Also learned that he is [a moderator](https://www.randalolson.com/2016/03/18/why-posts-get-removed-from-rdataisbeautiful/) of my favorite dataviz subreddit (r/dataisbeautiful).

- **[Lenny's open data play](https://x.com/lennysan/status/2033958104967352587)** — Lenny released his entire newsletter archive (350+ posts) and podcast transcripts (300+ episodes) as AI-friendly Markdown, plus an MCP server. Damn. Now I need to read everything.

- **[gstack](https://x.com/garrytan/status/2036083005941535099)** — Garry Tan's "run your entire company" stack. Pretty baller that he is doing this while also running YC full-time.

### This Week in Numbers

#### By the Numbers

- 936 messages across 51 sessions
- Longest session had 162 messages
- Usage roughly flat vs last week (943 msgs / 40 sessions the week prior)

#### What I Did

| Activity | Share |
|----------|-------|
| Client dashboards & presentations | 32% |
| Data modeling & analysis | 16% |
| Skill & agent building | 15% |
| Environment setup & devops | 14% |
| Notebook dev | 10% |
| Research & writing | 8% |
| Other | 5% |

#### Work Schedule

- Peak hours: 1pm, 9pm, 10am
- Busiest day: Friday (309 msgs); quietest: Sunday (12 msgs)
- Spread across all 7 days but weekends were light — Saturday and Sunday combined were fewer than any single weekday
