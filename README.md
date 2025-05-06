# Nexus Protocol Subgraphs

The Nexus Protocol subgraphs index data from the protocol smart contracts, and expose a GraphQL endpoint hosted by [The Graph](https://thegraph.com).

# Active deployments

## Protocol Subgraphs

### Test networks

- [Ethereum Sepolia](https://api.studio.thegraph.com/query/8290/zeebu-money-market-sepolia/version/latest)
- [Base Sepolia](https://api.studio.thegraph.com/query/8290/zeebu-money-market-base-sepolia/version/latest)
- [Chapel](https://api.studio.thegraph.com/query/8290/zeebu-money-market-bsc-chapel/version/latest)

## Development

```bash
cp .env.test .env

# install project dependencies
yarn install

# deploy subgraph
yarn subgraph:deploy:sepolia
```
