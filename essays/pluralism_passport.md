{
  "title": "Towards a Pluralism Passport Built from DeSoc Legos",
  "date": "07/28/2022"
}
---

Since reading the [DeSoc paper](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4105763) back in May, I've been fascinated with the concept of on-chain identity. 

It started with exploring DAO voting records to identify wallets that were active in multiple DAOs and that were willing to make non-consensus votes more frequently than other token-holders.

I then went deep into POAP data, trying to isolate POAP farmers and events that tended to attract large numbers of farmers.

In July, I started contributing afterhours to Gitcoin's Fraud Detection & Defense workstream. I expanded my research to a broader set of on-chain identity protocols. And I applied the research to a large dataset of Gitcoin Grants Round 14 contributors to see if on-chain, "DeSoc legos" could aide the DAO with [Sybil detection](https://gov.gitcoin.co/t/characterizing-the-sybil-resistance-problem/11235) and [Gitcoin Passport](https://passport.gitcoin.co/) trust scores.

[Here is a write-up](public/images/Towards_a_Pluralism_Passport_Built_from_DeSoc_Legos.pdf) of the findings so far. It's a lot of slides, though it's full of colorful dataviz, so you can flick through them pretty fast.

I've also pushed a public version of the analysis to Gitcoin's FDD repo, availabe [here](https://github.com/Fraud-Detection-and-Defense/gr14-onchain-trustscore-analysis).

---

If you're interested in conducting your own analysis, here are the APIs and some starter queries.

### Sites

- POAPs (xDAI only) via [The Graph API](https://api.thegraph.com/subgraphs/name/poap-xyz/poap-xdai)
- Snapshot votes (all EVM chains) via [Snapshot API](https://hub.snapshot.org/graphql/)
- NFT ownership (ETH Mainnet only) via [Zora API](https://api.zora.co/graphql)
- Lens profiles via [Lens API](https://api.lens.dev/)
- Proof of Humanity via [PoH API](https://api.poh.dev)

### Some sample queries to get you started

In each of the cases below, substitute the `$WALLETS` field with a list of wallet addresses (0x...)

#### Lens Protocol

```
query Profiles {
  profiles(
    request: { 
        ownedBy: [$WALLETS], 
        limit: 50 
    }
  ) {
    items {
      id
      name
      ownedBy
      stats {
        totalFollowers
        totalFollowing
      }
    }
  }
}
```

####  POAP

```
query POAPs {
  accounts(
    where: {
      id_in: [$WALLETS]
    }
  ) {
    id
    tokensOwned
    tokens (first: 1000) {
      event {
        id
      }
    }
  }
}
```

#### Snapshot

```
query Votes {
  votes (
    first: 10000
    skip: 0
    where: {
      voter_in: [$WALLETS]
    }
  ) {
    id
    voter
    created
    proposal {
      id
    }
    choice
    space {
      id
    }
  }
}
```

### Automating queries

Once you've configured your queries, here are some simple Python scripts for automating requests. 
Note: these scripts are fine for ad hoc analysis, not for building applications.

You'll need to provide values for `my_api_url`, `my_graphql_docstring` and `my_list_of_wallets`.

#### Method 1: Using requests

```
str_list = ", ".join(f'"{w}"' for w in my_list_of_wallets)
query = my_graphql_docstring.replace("$WALLETS", str_list)
r = requests.post(my_api_url, json={"query": query})
json_data = json.loads(r.text)
```

#### Method 2: Using gql

This approach is better for more complex tasking and uses a Python GraphQL client (gql3).

Get the gql package [here](https://gql.readthedocs.io/en/stable/).


```
from gql import gql, Client
from gql.transport.requests import RequestsHTTPTransport
sample_transport=RequestsHTTPTransport(
    url=my_api_url,
    verify=True,
    retries=3,
)
client = Client(
    transport=sample_transport
)
str_list = ", ".join(f'"{w}"' for w in my_list_of_wallets)
query = my_graphql_docstring.replace("$WALLETS", str_list)
q = gql(my_graphql_docstring)
r = client.execute(q)
json_data = json.loads(r.text)
```