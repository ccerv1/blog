{
  "title": "Reflections From My First Days Working On Hypercerts",
  "date": "10/28/2022"
}
---

> This is a note I wrote on October 28, 2022 shortly after joining Protocol Labs to work on hypercerts. I’m sharing it as a blog post, almost exactly one year later, as an artifact that may be useful to other teams at the early stages of building a new protocol. I have now moved on from working on hypercerts full-time, but have great hopes for the protocol and the community that has sprouted up around it. I am also curious to see how well this doc ages. Note: the doc has been lightly edited from the original to avoid mentioning specific names.

## What are hypercerts?

We don’t have a great response yet.

Consider the following one-liners that are out in the wild:

- [Hypercerts](https://protocol.ai/blog/hypercert-new-primitive/) are a new primitive for public goods funding.
- [Hypercerts](https://hypercerts.xyz/) are a tool to build scalable retrospective reward systems for impact.
- [Hypercerts](https://archive.devcon.org/archive/watch/6/hypercerts-for-regenerative-cryptoeconomics/) are a specific, interoperable data layer to account for actions that are expected to have a positive impact.

I worry you need to be pretty deep down the regenerative cryptoeconomics rabbithole to understand these product statements and to start imagining how such a primitive / tool / interoperable data layer would be useful.

This is hard. (FWIW, I didn’t arrive at a decent product statement until three years into my last startup, so I only know the pain of a weak pitch, not the joy of a good one.)

Coming up with an effective elevator pitch is one of the most frustrating parts of starting something. Founders are obsessed with the problem and the vision, but flexible on the solution and the immediate form it takes. This makes it hard to “just” pitch a solution.

However, when giving an elevator pitch, you don’t have time to give a lengthy exposition of the problem. You need to jump straight to (your latest working version of) the solution. The main thing the person you’re talking to cares about is “will this be useful to me?”

For most people I think, crafting a good pitch is more science than art, a numbers game. You need to keep versioning and practicing over and over again. If the question “what are you building” makes you squirm, then you’re not there yet.

Having a weak product statement won’t kill you. You can overcome it by conveying genuine passion and commitment about what you’re building. People are drawn to that energy, so you can brute force your way through hiring, sales, defining product requirements, etc. by doing a lot of 1-1 communication and explaining. That’s what we’re all doing now, which is fine if we only talk to friendlies. But it probably won’t get us to $50M by Q3 2023.

The other problem is that all the time we spend *explaining the thing* is time not spent *building the thing* (or learning about our users). This is more of an issue going forward: if we get 20 minutes with a VIP, we don’t want to spend 10 of them explaining hypercerts.

Sorry for the rant. Let’s keep working on our pitch!

## Iterating on the pitch

What are the components of a good pitch? Google says:

*An elevator pitch (often referred to as a product statement) is a short description of a product that explains what the product is, who it's for, and why it’s better.*

A product statement can often be assembled from the following components:

`[name of project] is a [product category] for [group of users] to [accomplish something] [optional: positive adverb]`

Here are some modulations that we came up with during a timebound exercise yesterday in Lisbon:

1. Hypercerts are digital twins for public goods for funders to only have to fund projects with 100% success rate.
2. Hypercerts make impact tangible and trackable.
3. Hypercerts make it easier to coordinate public goods. They’re the foundation for cheap impact moonshots.
4. Hypercerts create powerful incentives for project success and efficiency by making impact tangible and trackable.
5. Hypercerts allow funders to push their portfolio’s success rate to 100% by making public goods tangible, comparable, and trackable.
6. Hypercerts allow funders to separate predicting what projects will be impactful and what impact they value by enabling participants to track participation throughout the project lifecycle.
7. Hypercerts are a protocol for funders to reward positive impact.
8. Hypercerts are a protocol for funders to incentivize more work in the areas they care about.
9. Hypercerts are a protocol for funders to coordinate impact projects in a way that incentivizes the best talent to work on the most impactful projects.
10. Hypercerts are a protocol for funders to incentivize and coordinate work on the highest impact problems.
11. Hypercerts are a tool for funders to incentivize the best talent to work on the most impactful projects.
12. Hypercerts are a tool for funders to allocate their resources to incentivize the best talent to work on the most impactful projects.
13. Hypercerts are a protocol to create highly efficient, scalable transactions for public goods projects

We probably have identified most of the keywords for an effective statement. But bear in mind there are 427,518,000 permutations formed by choosing 6 words from a set of 30, so we can’t brute force a good statement either.

We should keep iterating, sharing feedback, and practice pitching regularly.

## The future vision … and the present reality

The hypercerts vision is extremely compelling from first principles thinking, eg:

- Public goods are good.
- More public goods will accelerate humanity’s progress.
- People will make more public goods if given the right incentives.
- But existing incentives are pretty broken [point to your favorite underfunded public good].
- One of the strongest incentives is money.
- A liquid market for impact would enable all sorts of new money to enter the mix.
- Markets are built on reliable data, which enables efficient transactions.
- Hypercerts solves the data problem for public goods and impact claims.
- Hypercerts improves the efficiency of public goods transactions
- This breakthrough will lead to a renaissance in public goods!

However, the present reality includes a spicy set of stakeholders who need to be convinced of this vision.

**“Impact Creators”**

They have been conditioned to operate with a scarcity mindset – always looking and competing for more funding / recognition. They also tend to have a larger than average amount of ego invested in the belief that what they’re working on deserves more funding / recognition. They see themselves as snowflakes. Exhibit A: there is virtually zero M&A in the nonprofit sector. Exhibit B: the failure rate for nonprofits is only [30](https://nanoe.org/nonprofits-fail/#:~:text=The%20real%20data%20from%20National,of%20a%20strategic%20plan%2C%20among)%, versus [at least 50%](https://www.forbes.com/sites/forbesfinancecouncil/2018/10/25/what-percentage-of-small-businesses-fail-and-how-can-you-avoid-being-one-of-them/?sh=68cbb14b43b5) for small businesses and ~90% for startups. These suggest that (a) “bad” operators don’t exit the market quickly, and (b) a large proportion of existing operators may feel threatened by a more efficient market.

**“Impact Funders”**

There exists a relatively small set of institutions and individuals who control large amounts of money. But most of the people with decision making power either inherited or were promoted into a position where they control these resources. Thus, they also inherited a playbook for how to deploy these resources. What incentive do they have to buck with tradition? A small proportion built wealth more recently *and* care enough to have a system for thinking about how to deploy it wisely. Yet these people got to where they are today by being good at things other than picking the right basket of public goods to fund (like running a tech startup). So they are smart people who may not realize they are making suboptimal funding decisions. How motivated are they to get better?

**“Impact Evaluators”**

This group is perhaps the least studied. Impact evaluators tend to be highly specialized – the experts who evaluate clinical control trials don’t really swap notes with the experts who verify carbon credits. Even well-defined international standards, like ISO, don’t have legions of people equipped to evaluate compliance. It’s not sexy work. Expertise is highly fragmented. Impact evaluators, who usually operate as consultants charging a day rate, don’t have strong incentives to collaborate with other impact evaluators. They do have incentives to collude with whoever is paying them to produce a more favorable result. And, regardless of who is paying them, there is little business model in offering negative results only. For hypercerts to realize its vision, it will need a deep liquidity of credibly neutral impact evaluators. (FWIW, my previous startup served as an impact evaluator for coffee companies – it was extremely difficult maintaining neutrality.)

Suffice it to say, the present reality includes a large number of stakeholders who may not be intrinsically motivated to change their behaviors – and may feel threatened to do so.

**A brief word on effective altruism (EA)**

The EA community has thought deeply on the problems with the present reality and developed a set of highly opinionated expressions of what constitutes “effective” funding. They seek to narrow the field of “impact creators” to a much smaller pool, all subjected to rigorous impact evaluation. Then, the role of “impact funders” is primarily to determine an allocation of funding across those projects.

I agree with [Nadia Asparouhova](https://nadia.xyz/idea-machines) that, while EA is an important voice, the present reality may be hindered by EA being the only outspoken voice. Thus, what we really need is more idea machines like EA, not necessarily more EA.

## A hyperdimensional cold start problem

Every product faces the cold start problem at its inception, when there are no users. Networks face a harder cold start problem because they need users in order to create any value. There is no value in a social network of one. Andrew Chen of a16z has a whole [book](http://andrewchen.com/wp-content/uploads/2022/01/ColdStartProb_9780062969743_AS0928_cc20_Final.pdf) on this topic.

More traditional businesses have a one-dimensional cold start problem: finding customers.

Many web2 marketplaces or gig economy businesses have a two-dimensional cold start problem: Uber needs riders and drivers; OpenTable needs diners and restaurants.

It’s harder to think of three-dimensional cold start problems in web2. Uber Eats only added a food dimension once it had strong network effects elsewhere in its business.

Gitcoin had a unique web3 cold start problem: they needed to attract big-check match funders, a diversity of credible public goods projects, and a large number of retail public goods supporters from the Ethereum community. If my understanding is correct, they built a project network first [because they were close with many open source developers], then the big-check funder network [through Vitalik and a few other crypto HNWIs], and finally a community of retail supporters [by turning quadratic funding into a fun, gamified experience].

Hypercerts feels like a hyperdimensional cold start problem. We need impact creators, impact funders, impact evaluators, and application builders. You could further split the impact funders into two categories: those who want to exchange hypercerts and those who want to accumulate hypercerts

I think it’s impossible to push hard on all dimensions from day one. Product guru Lenny Ratchitsky has an incredible [series](https://www.lennysnewsletter.com/p/how-to-kickstart-and-scale-a-marketplace) on kickstarting two-sided marketplaces. His advice: **decide which side of the marketplace to concentrate on**.

![https://images.mirror-media.xyz/publication-images/5bRVUv2ZRuV13LnjlvMsA.png?height=1043&width=2000](https://images.mirror-media.xyz/publication-images/5bRVUv2ZRuV13LnjlvMsA.png?height=1043&width=2000)

The general pattern appears to be to focus on the more tightly constrained part of the marketplace first. With Airbnb, there were fewer people who conceivably had a nice room to rent to a stranger than there were potential guests. With TaskRabbit, they had thousands of people on their waitlist to provide services, but no one was looking for services.

Lenny doesn’t have any advice for an n-dimensional web3 marketplace, but my current instinct would be to:

- Focus on one side to concentrate on
- Ignore as many other sides as possible
- Dogfood whatever is left over (dogfooding means using your own products… I feel like it has a bad connotation in some circles, but I think it’s a good thing in many situations)

With hypercerts, this could take the form of:

- Focusing on funders (specifically funders who want to own hypercerts because they care about impact)
- Ignoring impact evaluators and speculative funders (for now)
- Dogfooding the application building [build it ourselves for the uses cases we know best]
- Assuming that with sufficient funding and a decent application stack, impact creators will be motivated and able to participate

## Solve funders’ problems first

On Tuesday’s roadmapping session, we arrived at a decision to focus on funders, ie, the demand side of the market. This means we need to talk to funders and learn about their needs before we build too much.

We then developed a set of assumptions about what we think funders care about – and applied a quick ranking method to it. Here’s what we came up with (in order from strongest to weakest preference):

- I have an impact area that I care about deeply and want to incentivize more good work in that area
- I want to have impact on a very large scale
- I want to compare projects based on their impact track record
- I have very specific public goods needs that I want people to build
- I want to see more money go towards moonshot ideas
- Too few projects succeed post-funding
- Not enough promising/high-potential projects
- I like leveraging my funding to bring in other funders
- I don't know how successful the funded projects have been
- I want to see public goods funding much more streamlined and standardized
- There's not enough retrospective funding
- I want to push for more efficient ROI (impact per dollar spent)
- I want to be seen as a thought leader and innovator
- I spend too much time / money reviewing grant proposals
- I want impact creators to spend less time worrying about grant writing
- I find it hard to keep track of project progress
- I want to let the people decide what I should fund
- I am disillusioned by the current ways of funding public goods
- I only want to fund things that have a high success rate
- I like funding things that are high risk and relatively unproven
- I want to find projects that are off my radar
- I find it difficult to find promising projects
- There are more promising projects than funding available
- I find it hard to compare my portfolio to other funders
- I want to fund impact in areas that I am not very knowledgeable about
- I want to support under-represented projects

It’s not a MECE list and, again, these assumptions need to be validated through user interviews. But if we see strong signals from users who say “I have very specific public goods needs that I want people to build” then a product statement like “hypercerts are a protocol for funders to incentivize more work in the areas they care about” could be very compelling. However, the same statement would miss the mark if what we hear from funders is “I want to find projects that are off my radar”.

## Which types of funders do we want to start with

We also started narrowing down the types of funders we want to focus on, at least for the purposes of user research. These include governments (think: Taiwan’s g0v), legacy foundations (think: Gates), crypto foundations (think: FTX* Future Fund), EA funds (think: Scott Alexander’s ACX grants), crypto high net worth individuals, and DAOs (think: Vita DAO).

- *this was written two weeks before FTX imploded 🙈*

We made a simple 2x2 with potential check size on the y axis (log scale) and a very handwavy measure of adoption on the x axis.

![https://images.mirror-media.xyz/publication-images/MRFgWdjDZz1Ar5fm0Azc8.png?height=1008&width=2000](https://images.mirror-media.xyz/publication-images/MRFgWdjDZz1Ar5fm0Azc8.png?height=1008&width=2000)

Finally, we took our users on one axis and the customer problem statements on another and attached a very non-scientific preference strength to it. [0 = not important, 2 = most important]

![https://images.mirror-media.xyz/publication-images/N10DI_qdCj7Rj6dswFb9j.png?height=666&width=1900](https://images.mirror-media.xyz/publication-images/N10DI_qdCj7Rj6dswFb9j.png?height=666&width=1900)

This exercise suggests there may be some important differences among users, some of which may be incompatible with the version of hypercerts. For example, funders are likely to have different reactions to the prospect of “leveraging my funding to bring in other funders”. A government may be categorically opposed to the idea of having outside funders join them, whereas a DAO may view it as one of the biggest value adds.

## Kickstarting the first markets: DeSci, OSS, and DeSci ∩ OSS

The answer to the “what markets do we focus on first” question is coalescing on DeSci and OSS. These seem very on-brand for Protocol Labs and would tap into existing communities where the team already has strong networks.

These markets also present numerous opportunities for dogfooding. We had an idea of running a prize competition on hypercerts for retrieval market research, which would be valuable both from a DeSci and OSS public goods perspective. (Maybe we should use hypercerts to incentivize user research on donors…)

## What’s next

We made some updates to the hypercerts roadmap. Juan Benet’s CTA is our headline goal: create a $50M impact market with hypercerts as the leading standard.

Achieving the goal requires two sets of objectives: finding community-market fit and growing protocol adoption. The community-market fit piece feels clear – and even clearer after the work done over the past week. The protocol adoption piece feels a bit more open-ended. Now that we have decided to focus on the funder side of the market first, we need to be careful to not build too much of the technology stack without first learning more about what funders want to use.