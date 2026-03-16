# Weeknotes: March 9–15, 2026

I had a few hard deadlines this past week, so most of my time went to polishing. Claude is miraculously good at helping you build something out of the gate. It is tedious at refining.

Relatedly: while many AI businesses are using input-based pricing (ie, metering usage or seats), the real value will be in some form of verifiable outcome-based pricing. The opportunity is tracking outcomes that are not just cost savings / productivity gains.

---

## Process Upgrades

- **I'm starting to treat skill changes like code changes.** After hastily trying to compress a few of my largest skills docs, I noticed my workflows weren't performing as well as they used to. I wrote something halfway between an eval and a regression test, confirmed the degradation, and reverted.

- **Breaking ground on the data catalog.** I built a v1 system for documenting public data models — schema, lineage, business logic, best practices — so agents can reference them during analysis projects. This will no doubt evolve a lot.

- **Another reminder to ignore sunk costs.** I had two projects this past week that just felt off. Successive attempts to fix them made them worse. So I documented everything, hit a hard reset, and rebuilt them. In both cases, I moved faster by selectively feeding the good parts of the old project into the new one, rather than trying to salvage the old one.

## New Experiments

- **Programmatic video with Remotion.** The biggest experiment of the week. [Remotion](https://www.remotion.dev/) is a React-based framework for composing video programmatically — components, props, and a dev server with frame-by-frame scrubbing. The learning curve is real (my longest session of the week, by far), but once you internalize the mental model, iteration can be fast. Their licensing model is a breath of fresh air.

- **Agent-friendly sprint planning.** It's obvious that planning and review will be the bottlenecks of the development process going forward. I did a pseudo-quantitative analysis on my team's issue tracking over the past 12 weeks to assess how "agent-friendly" we've been. I enjoyed Claude's labeling of each person's style: some people use Linear as a personal to-do list, some use it to delegate and throw over the fence, and some over-specify the process and under-specify the outcome (me).

## Good Reads

- **[Chrome's native agent support](https://x.com/addyosmani/status/2032875051830358197)** — Chrome DevTools now exposes your real, signed-in browser to coding agents via MCP. No extensions, no headless browser, no separate logins. One toggle. Curious to try this out.

- **[Claude's interactive charts](https://x.com/claudeai/status/2032124273587077133)** — The rumor: Claude ships a new feature and kills a thousand startups. The reality: possibly cool, but I think we are still a long way from one-shotting the killer chart.

- **[Self-hosting as existential requirement](https://x.com/spengrah/status/2031943507389059128)** — As companies move institutional knowledge into agentic context graphs, controlling that data becomes existential. All performance on top of models comes from context, which means feeding agents your most sensitive data, which means self-hosting at scale. Good take.

## This Week in Numbers

### By the Numbers

- 943 messages across 40 sessions
- Longest session had 166 messages
- Usage up ~21% from last week (778 msgs / 43 sessions)

### What I Did

| Activity | Share |
|----------|-------|
| Demo video | 37% |
| Client work & data modeling | 28% |
| Skill & agent building | 15% |
| Debugging & code reviews | 10% |
| Research & writing | 7% |
| Other | 3% |

### Work Schedule

- Peak hours: 10pm, 12pm, 4am
- Busiest day: Tuesday (255 msgs); quietest: Thursday (19 msgs)
- Work spread across all 7 days — no real days off this week between a long flight and the deadlines