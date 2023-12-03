{
  "title": "Impact evaluations for 158 Gitcoin Grants - and the 30 I chose to fund",
  "date": "01/21/2023"
}
---

> #### *This article was originally posted on [Mirror](https://mirror.xyz/cerv1.eth/yBtw568KrA9SVvITGq2E6eQb14UdZYeb1lhimFW8qV4) .*
>
# Intro

This is my first attempt at creating a series of modular, oracular impact assessments for [Gitcoin Grants](https://grants.gitcoin.co/).

Each assessment is modular because it is derived independently, is self-contained (within a round), and is easy to combine with other assessments. Each assessment is oracular in the sense that it is automated and built on top of public datasets that capture real-world events.

Communities of projects and funders can benefit from better feedback mechanisms and finer-grained tools for allocating resources.

In the long run, I’d love to see a large, decentralized ecosystem of impact assessments. No single impact assessment can capture the full impact of a project. Nor should any one assessment be relied upon for 100% of resource allocation decisions.

We need many credibly neutral, open, and [forkable impact assessment methodologies](https://gov.gitcoin.co/t/proof-of-impact-proposals-wanted/10179) working together.

Think of how Rotten Tomatoes combines expert and amateur movie reviews. Maybe there could be something similar for retrospective grantmaking?

My own impact evaluation should be viewed as nothing more than a single data point. I  happily concede that the metrics I picked are pretty easy to game. Per [Goodhart’s Law](https://en.wikipedia.org/wiki/Goodhart%27s_law) (when a measure becomes a target, it ceases to be a good measure), I expect some if not all of these methods to be laughably insufficient at predicting future impact - especially if people start to think that they are useful predictors of impact or funding.

You can view my processed dataset [here on IPFS](https://bafkreiheswljtl7nwjzpwaw36mcebk2e6xpw6qybruhazvijymddfkkayi.ipfs.nftstorage.link/). You can also see a [Google Sheet](https://docs.google.com/spreadsheets/d/1tTjx-JMPZq9cUKLOK5xd_8wq4dvDHrsuKpmG7rsHpNY/edit?usp=sharing) with the output assessment scores.

I hope this inspires you to create your own, better assessments!

# Methodology

The 158 projects currently on Gitcoin Grants have been deployed across three rounds:

- Climate Solutions (50 projects)

- Ethereum Infrastructure (22 projects)

- Open Source Software (86 projects)

To get the data on the projects, I queried [the subgraph](https://thegraph.com/explorer/subgraphs/BQXTJRLZi7NWGq5AXzQQxvYNa5i1HmqALEJwy3gGJHCr?view=Playground&chain=mainnet) for each round and extracted the metadata blobs from IPFS. The metadata contains information about each project including its wallet address, main Github repo, and Twitter handle.

Next, I ran some scripts to gather additional public data about each project:

On-chain: I checked if the project’s wallet address has an ENS domain or Lens profile registered. I like seeing projects commit to building an on-chain reputation. These are two of the most popular web3-native identity protocols currently.

Github: using the basic Github API, I gathered metrics on when the repo was created, when the last commits were made, and how many forks/stars it has. These are reasonable proxies for the longevity and activity of a project. My impact assessments for projects in the Ethereum Infrastructure and OSS rounds were heavily weighted by Github metrics.

Twitter: using the Twitter API, I pulled metadata about each account, including follower/friends lists. Then, for the projects within each round, I constructed a network graph and determined which project nodes had the most [centrality](https://en.wikipedia.org/wiki/Centrality). (Yes, this is basically a popularity contest.) Mutual support is a common theme in web3 communities, particularly the ReFi / climate community, so this is a reasonable approximation of which projects are having the most impact at least in terms of meme propagation.

Once my datasets were ready, I normalized the indicators and created ranking formulas for each round. For example, Github activity is weighted more heavily in the ranking formula for Open Source Software projects than for Climate Solutions. You can fork or play with the data [here (IPFS)](https://bafkreiheswljtl7nwjzpwaw36mcebk2e6xpw6qybruhazvijymddfkkayi.ipfs.nftstorage.link/) and [here (Google Sheet)](https://docs.google.com/spreadsheets/d/1tTjx-JMPZq9cUKLOK5xd_8wq4dvDHrsuKpmG7rsHpNY/edit?usp=sharing).

Finally, I selected the top 20% of projects from each round (for a total of 30 projects).

# Results

## Climate (10 projects):

- Natives in Tech

- TaterDAO

- Shamba Ecological Oracle and DMRV Network

- Bloom Network

- .basin - perpetual place-based climate & nature finance

- ReFiDAO X Commons Stack: ReFi Commons Prize

- Treejer Protocol

- Kokonut Network

- Web3beach

- BETTER

## ETH Infrastructure (4 projects)

- ethers.js

- Blockscout 2.0 - Premium Open-Source Block Explorer

- rotki

- TrueBlocks and the Unchained Index

## Open Source Software (16 projects)

- Lenster

- web3swift

- Vyper Smart Contract Language

- Electronic Frontier Foundation

- Dapp-Learning

- vfat.tools

- DefiLlama

- The MoonMath Manual to zk-SNARKs

- Giveth

- Tally Ho! - Open Source and Community Owned Wallet

- Jolly Roger

- POAPin

- BrightID 🔆 Universal Proof of Uniqueness

- CirclesUBI

- Lenstube

- devpill