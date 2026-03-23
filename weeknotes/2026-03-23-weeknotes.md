# Weeknotes: March 16–22, 2026

I moved my entire Claude Code environment into a containerized setup. Now I can run in yolo mode with more peace of mind. The exercise also forced me to deal with how many of my workflows had hardcoded paths and implicit dependencies.

---

## Process Upgrades

- **Containerized everything.** The single biggest change this week. All my Claude Code workflows now run inside a devcontainer. Still working out some rough edges.

- **Data visualization as a quality standard.** I created my own version of [Tufte principles](https://x.com/randal_olson/status/2034978267397313021) as a skill that agents can reference during notebook development. Then extended it with a few other profiles from people whose work I have on my bookshelf (Bertin, Few, Wilkinson, Cairo). Skills are not a moat.

- **Data marketplace guides as agent context.** Built more structured guides for public data models so agents can reference schema, lineage, and best practices during analysis projects.

- **Programmatic slide decks.** Rolled my own HTML to PPTX converter to produce presentations directly from notebook data. Charts export as SVGs, data tables render cleanly, and the whole thing rebuilds from source. Still fiddly (font sizes, annotation placement), but the goal is to never touch PowerPoint or Google Slides again.

## New Experiments

- **TikTok meets Hacker News.** Short demo videos (2-5 min) of things people have built, presented in a social feed format. This was a shower thought inspired by overhearing a non-technical person describe a tool they built. However, unlike most shower thoughts, I gave it to Claude and created a simple wireframe that looks kinda decent.

## Good Reads

- **[The Tufte Test](https://x.com/randal_olson/status/2034978267397313021)** — Randal Olson encoded Tufte's visualization principles into an API, pointed an AI agent at it, and watched it self-correct from a generic chart to a genuinely good one in two prompts. Also learned that he is [a moderator](https://www.randalolson.com/2016/03/18/why-posts-get-removed-from-rdataisbeautiful/) of my favorite dataviz subreddit (r/dataisbeautiful).

- **[Lenny's open data play](https://x.com/lennysan/status/2033958104967352587)** — Lenny released his entire newsletter archive (350+ posts) and podcast transcripts (300+ episodes) as AI-friendly Markdown, plus an MCP server. Damn. Now I need to read everything.

- **[gstack](https://x.com/garrytan/status/2036083005941535099)** — Garry Tan's "run your entire company" stack. Pretty baller that he is doing this while also running YC full-time.

## This Week in Numbers

### By the Numbers

- 936 messages across 51 sessions
- Longest session had 162 messages
- Usage roughly flat vs last week (943 msgs / 40 sessions the week prior)

### What I Did

| Activity | Share |
|----------|-------|
| Client dashboards & presentations | 32% |
| Data modeling & analysis | 16% |
| Skill & agent building | 15% |
| Environment setup & devops | 14% |
| Notebook dev | 10% |
| Research & writing | 8% |
| Other | 5% |

### Work Schedule

- Peak hours: 1pm, 9pm, 10am
- Busiest day: Friday (309 msgs); quietest: Sunday (12 msgs)
- Spread across all 7 days but weekends were light — Saturday and Sunday combined were fewer than any single weekday