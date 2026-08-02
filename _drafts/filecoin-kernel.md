<!--
DRAFT NOTES (delete before publishing):
- Co-authored with Sejal Rekhan (PLFIF). Needs her review, especially Sections 3 and 5.
- [ ] Confirm the EF Kernel research figure (~$18M/yr) and link to the published source
- [ ] Confirm we're comfortable publishing the funding funnel numbers (~$4.7M applied → ~$1.6M kernel budget)
- [ ] Confirm the Forest consensus-bug anecdote is OK to share publicly (check with ChainSafe)
- [ ] Add tiering diagram (Section 2) and dashboard screenshot (Section 4)
- [ ] Add links: kernel repo/dashboard when public, ProPGF round announcement, feedback channel
-->

# Introducing Kernel: A Minimum Viable Protocol Approach to Public Goods

*August 2026*

*Co-authored with [Sejal Rekhan](https://twitter.com/sejalrekhan) (Protocol Labs Filecoin Infrastructure Fund). Thanks to the Ethereum Foundation, whose Kernel research inspired this work, and to the Linux kernel community for decades of proof that a well-tended core can carry an entire ecosystem. Thanks also to the Open Source Observer team for building the data foundation underneath it.*

Ask anyone running an ecosystem fund what they're excited about and you'll get a great answer. New apps, new users, new narratives. Growth stuff.

Now ask them a different question: *what is the minimum set of things your ecosystem needs to survive?*

Most can't answer it. Not because they're bad at their jobs, but because nobody has ever forced the question. Critical infrastructure gets funded ad hoc, milestone by milestone, one grant cycle at a time. It's invisible until it breaks. The open source world has a rich history of near-misses here — OpenSSL was maintained by a handful of underfunded volunteers when Heartbleed hit, and the whole internet turned out to be [a tower of blocks balanced on one maintainer in Nebraska](https://xkcd.com/2347/). Crypto ecosystems like to think they've solved this with grants programs. Mostly, they've just made the Nebraska problem better funded and worse documented.

Over the past year, we've been working on an answer for Filecoin. We call it the **kernel**: the minimum set of functions a network needs to exist, plus the projects currently serving them. This post explains the framework, how we applied it, and why we think every protocol ecosystem should run this exercise.

One thing up front: Kernel is not a Filecoin program. It's a method. Filecoin happens to be the first ecosystem to run it end-to-end, but everything below — the tests, the tiering, the data pipeline, the funding model — is designed to be forked. Consider this post an invitation.

## Every ecosystem has a kernel

The name is borrowed deliberately. The Linux kernel is a small, fiercely maintained core that an enormous ecosystem builds on top of. Nobody confuses the kernel with the distribution. Nobody argues that a desktop theme and the process scheduler deserve the same funding treatment. The boundary is understood, defended, and — crucially — *maintained by people whose job it is to maintain it*.

The Ethereum Foundation's [Kernel research](https://www.youtube.com/watch?v=CM1FGBgJerw) is the intellectual predecessor to this work. Their team asked what it would cost to neutrally fund Ethereum's essential functions and arrived at a surprisingly tractable number. That research reframed the problem for us: a kernel isn't a philosophical concept, it's a budget line. You can enumerate it, cost it, and monitor it.

The failure mode this solves is one every ecosystem funder will recognize. The teams maintaining consensus clients, VMs, and proof systems end up applying to the same grant rounds as hackathon projects, writing milestones for work that is fundamentally *continuous*, and getting evaluated by reviewers who have no framework for distinguishing "this would be nice" from "if this stops, the network stops."

## What is a kernel?

Our working definition: **the minimum set of functions a network needs to exist, plus the projects currently serving those functions.**

Note the two-part structure. Functions are abstract (block production, state execution, randomness, data availability). Projects are concrete (Lotus, ref-fvm, DRAND). The kernel is defined at the function level; projects are the *current stewards* of a function, not permanent entitlements. This distinction turns out to be the single most important idea in the whole framework, and I'll come back to why.

To decide whether something belongs in the kernel, we run three tests:

1. **The walkaway test.** If the team serving this function walked away tomorrow, what happens to the network? Immediate failure, slow degradation, or nothing?
2. **Zero-base estimation.** Forget historical funding. If you had to provide this function from scratch, what would it actually cost? (Historical grant sizes are anchored on negotiation history, not on what the function requires.)
3. **The one-way-door question.** Borrowed from the Bezos decision framework: if this fails, is it recoverable? Some failures you can fund your way out of later. Others start a death spiral.

The answers sort every function into four tiers:

- **Irreplaceable** — the network cannot exist without it, and there is no substitute. Consensus, proofs, the randomness beacon.
- **Essential** — the network degrades badly without it, though a substitute or workaround exists at high cost.
- **Important** — meaningfully improves the network's resilience or usability, but its loss is survivable and recoverable.
- **Nice-to-have** — everything else, including plenty of genuinely good work.

Only the first two tiers are the kernel. That sounds obvious written down. In practice, drawing the line is where all the work is.

**What the kernel is not.** It is not a popularity ranking — some of the most essential functions have the smallest communities. It is not permanent status — functions get reclassified as the protocol evolves, and stewards can change. And it is not a complete funding strategy — the kernel is the floor, not the ceiling. Growth programs, retro funding, and ecosystem grants all still matter. They just shouldn't be the mechanism keeping the lights on.

## How we did it for Filecoin

The Filecoin kernel mapping took roughly six months, anchored by an expert inquiry process: deep technical interviews with the leads of each candidate component — the client implementations (Lotus, Forest, Venus), the execution layer (ref-fvm, builtin-actors, FEVM), proofs, the DRAND randomness beacon, libp2p, and the endpoint and explorer infrastructure that everything downstream quietly assumes will exist.

For each function we built up an evidence base: argument trackers capturing the case for and against each classification, landscape tables comparing alternatives, and decision briefs for the calls that needed human judgment. That last category was bigger than we expected, and it's where the process earned its credibility. A few of the hard ones:

**How do you value redundancy?** Filecoin has multiple client implementations. Client diversity is an article of faith in protocol design — but is a second client that mostly serves RPC traffic a genuine resilience play, or a nice-to-have wearing a resilience costume? We went back and forth on this for weeks. The debate sharpened into a scoping question: a second client is kernel *to the extent that it exercises the consensus path*, and the funding conversation became about making that true rather than an up-or-down vote. (Mid-process, the Forest team caught a consensus-level bug that affected other implementations — about as clean a validation of the redundancy thesis as you could ask for.)

**Where does the kernel end and the ecosystem begin?** Storage onramps, indexers, SDKs — all contested boundary cases. Our resolution was usually to unbundle: a project's proposal often contains a kernel-critical slice and a discretionary slice, and the honest move is to fund them differently rather than average them together.

**Functions don't transfer their tier to projects.** This is the failure mode we had to design against most actively. "Networking" as a function is irreplaceable. That does *not* make every project proposing networking work irreplaceable. Reviewers naturally conflate the two — the function's tier bleeds onto whatever project is standing near it. The fix is the two-part definition: classify the function, then separately evaluate how much of a given proposal actually serves it. For our first review round we mapped every proposal to specific kernel functions and asked reviewers to score the overlap. Some big asks mapped to six functions; others mapped to two.

**Deprecation is part of stewardship.** An honest kernel process sometimes concludes that a component should be wound down, not funded harder. Sequencing that responsibly — coordinating with dependent teams, avoiding a cliff — is itself kernel work.

The meta-lesson: classification is a judgment process supported by evidence, not an algorithm. We built rubrics and then spent half our time telling reviewers not to over-rely on them. The tests and tiers give the judgment structure and make it auditable. They don't replace it.

## The data layer

You can't retain a kernel you can't observe. This is where Open Source Observer comes in, and it's the part I've personally spent the most time on.

The principle we started from: **measure health, not activity.** The kernel is a support platform — its success shows up in the projects that depend on it, not in its own commit volume. Nobody should care how many lines of code the randomness beacon team shipped this month. They should care whether the beacon lagged.

Concretely, every kernel function gets an SLA-style entry in a public registry: the function, its tier, its current steward, a measurable health statement, and where the data comes from. Something like:

```yaml
- function: randomness-beacon
  tier: irreplaceable
  steward: drand
  sla:
    statement: "beacon relay not lagging: expected - current <= 1 round"
    metric: beacon_round_lag
    threshold: { op: "<=", value: 1 }
    cadence: daily
```

The metrics themselves were largely proposed by the teams in their applications and baked into the funding agreements — which matters, because a metric a team chose for itself is a metric they'll defend. OSO's pipeline ingests the rest: repository activity, on-chain data, dependency graphs, endpoint uptime. Everything gets normalized and surfaces in a **Kernel Health dashboard** with two faces: *health* (are the functions being served?) and *funding fragility* (how concentrated are the funding sources behind each function?).

Two design decisions worth highlighting. First, **incident responsiveness beats raw uptime**. What we actually track is how quickly a team acknowledges and communicates when something breaks — a public "kernel health" channel with a bot tagging responsible teams does more for confidence than a wall of green checkmarks. Second, **dependency mapping runs top-down**: rather than deriving the whole graph, we ask every funded project for its top 3–5 dependencies at intake. Cheap, self-updating, and it catches the hidden edges (the analytics portal that quietly depends on an indexer nobody was tracking).

There's a happy side effect: the dashboard replaces most of the reporting burden. Monthly reports are generated from the pipeline instead of written by maintainers. Teams that used to spend days on grant reports now spend zero. And because the data is open, anyone — not just the funder — can audit whether the kernel is healthy. That's the standard: if you have to take the foundation's word for it, it isn't really a kernel program.

## Funding the kernel differently

Here is where the framework stops being an analysis exercise and starts changing how money moves.

Kernel work breaks the milestone-grant model, structurally. Maintaining a consensus client is not a project with a beginning, middle, and demo day. It's a near-fixed cost, closer to payroll than to a grant. Forcing it into milestone format produces theater: teams invent deliverables that describe what they were going to do anyway, and reviewers pretend to evaluate them. Everyone knows, nobody says.

So for kernel functions, we dropped the pretense:

- **Annual soft-committed budgets** per function, sized by the zero-base estimates rather than negotiation history.
- **Retainer rhythm, no milestones.** Teams are paid on a recurring schedule. No invoicing — they hear from us only if a payment is delayed.
- **Monthly performance reporting by the program**, not the teams — generated from the Kernel Health pipeline.
- **Six-month check-ins with budget resets**, run by a small dedicated review group that carries context between cycles instead of re-litigating from scratch.
- **One dedicated Kernel round, one shared term.** Every kernel project on the same clock. Predictability for maintainers, coherence for the funder, and an honest annual moment to ask whether the map still matches the territory.

The kernel also imposes discipline on the funder's side. In our first cycle, teams applied for roughly three times more "core infrastructure" funding than the kernel classification supported. The framework gave us a principled way to fund the essential slice properly, route the important-but-not-essential work to other mechanisms, and say no to the rest — with reasons we could publish rather than vibes we had to defend.

## How we'll know it's working

Success looks boring: kernel functions continuously served, no surprise failures, maintainers who stay. The specific things we watch:

- **Continuity** — every irreplaceable and essential function has a funded, responsive steward at all times.
- **Early warning** — degradation shows up on the dashboard before it shows up as an outage. The system should produce yellow lights, not just post-mortems.
- **Maintainer retention and bus factor** — the point of retainer-style funding is that senior people can commit to this work as a career, not a gig between grants.
- **Classification integrity** — a regular audit of a subset of kernel functions, re-running the tests to check whether yesterday's essential is still essential.

Any of these can trigger reclassification or a budget change at the six-month check-ins. And we're committed to publishing what we learn, including the misses — that's the difference between running a program and starting a movement.

## The agentic kernel

Everything described so far produced a pile of artifacts: classification rubrics, argument trackers, landscape tables, decision briefs, an SLA registry, a data pipeline. Traditionally, that pile becomes a PDF that three people read.

We're taking a different bet: the kernel shouldn't just be documented, it should be **operable** — encoded as skills that AI agents (and humans) can actually run. The methodology is, after all, mostly structured judgment over structured data, which is exactly what agents are getting good at. The skills we're building:

- **Kernel classification** — run the walkaway / zero-base / one-way-door tests against any project and produce a draft tier with evidence.
- **Kernel health monitoring** — query the OSO pipeline, check SLAs, flag anomalies, draft the monthly report.
- **Funding-decision support** — generate the decision briefs and landscape tables that took us weeks to assemble by hand.
- **Dependency mapping** — maintain the graph from intake data and repository signals.
- **Onboarding** — "explain the Filecoin kernel to a new contributor," grounded in the registry rather than tribal knowledge.

Health monitoring already runs on an agentic loop, with humans reviewing rather than assembling. But the bigger idea is portability. The Filecoin inquiry took months of interviews and synthesis. With the methodology encoded as skills, the next ecosystem should be able to run a credible first-pass kernel inquiry in weeks — agents drafting the map, experts correcting it — instead of starting from a blank page.

## The foundation for what comes next

The kernel is the base layer of a funding stack, not the whole stack. Once you know what must not fail — and can see that it isn't failing — every other mechanism gets easier to run with confidence. Retro funding, convergence/divergence experiments, prediction-market-informed allocation: all of these operate *above* the kernel, taking bigger swings precisely because the floor is guaranteed. You can't take intelligent risks at the edges if you're not sure the center will hold.

For Filecoin specifically, what's next: the first dedicated Kernel round, the shared 2027 term, and continued iteration on the Kernel Health dashboard. And the governance layer, which we consider open research: How does a function get added to the kernel? How does one get removed — and who sequences the deprecation? How should the important and nice-to-have tiers get funded, and by whom? We have opinions, but we'd rather publish the questions and iterate in public than pretend to certainty we don't have.

## An invitation

If you help steward a protocol ecosystem, try the exercise. You don't need our tooling to start — you need a whiteboard and the honesty to ask what would actually happen if each piece of your infrastructure disappeared tomorrow. If you get further than that, everything we're building — the framework, the registry format, the skills — is developing in the open, and we want the method to outgrow us.

Engage with the work on GitHub, tell us where the framework breaks, and if you run a kernel inquiry for your own ecosystem, we want to hear about it — especially the parts where you conclude we got it wrong.

Every ecosystem has a kernel. Most just haven't mapped it yet.
