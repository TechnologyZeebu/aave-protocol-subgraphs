# 🚀 Nexus Protocol Subgraphs

Subgraphs for indexing Nexus Protocol smart contracts using [The Graph](https://thegraph.com). Useful for querying on-chain data with GraphQL.

---

## 🧠 TL;DR

- Subgraphs index blockchain data so you can query it via GraphQL.
- Edit the config file with contract addresses + start blocks.
- Authenticate with your deploy key from The Graph Studio.
- Deploy using the scripts in `package.json`.

---

## 🌍 Active Deployments

### Test Networks

#### V2

- [Ethereum Sepolia](https://api.studio.thegraph.com/query/8290/zeebu-money-market-sepolia/version/latest)  
- [Base Sepolia](https://api.studio.thegraph.com/query/8290/zeebu-money-market-base-sepolia/version/latest)  
- [BSC Chapel](https://api.studio.thegraph.com/query/8290/zeebu-money-market-bsc-chapel/version/latest)  

#### V3

- [Ethereum Sepolia](https://api.studio.theneegraph.com/query/103968/nexus-money-market-sepolia-v-3/version/latest)  
- [Base Sepolia](https://api.studio.thegraph.com/query/103968/nexus-money-market-base-sepolia-v-3/version/latest)  
- [BSC Chapel](https://api.studio.thegraph.com/query/103968/nexus-money-market-chapel-v-3/version/latest)

### Mainnet

- [Ethereum Mainnet](https://api.studio.thegraph.com/query/114661/nexus-mm-mainnet/version/latest)

---

## ⚙️ Getting Started

### 1. Install dependencies

```bash
yarn install
```

## 🔧 Configuring a Deployment

### 2. Set up your config file

Find the file for your target network under /config.
Example: [/config/sepolia-v3.json](./config/sepolia-v3.json)

Fill it out with the correct data:

```json
{
  "network": "sepolia",
  "AaveOracleAddress": "0xB7c437D99bD1EEd8E8D0eC4fE865b70EfBFAc1f3",
  "AaveOracleStartBlock": 8320405,
  "PoolAddressesProviderRegistryAddress": "0xdBDa92ca3C9B618dE766c3E68Ff8e12a54347bcD",
  "PoolAddressesProviderRegistryStartBlock": 8320373,
  "RewardsControllerAddress": "",
  "RewardsControllerStartBlock": 8320373
}
```

<div style="background-color: #d4edda; padding: 10px; border-radius: 5px; margin-bottom: 10px;">
<strong>💡 Tip:</strong> You can find block numbers using Etherscan or your preferred block explorer
</div>

### 3. Authenticate with The Graph Studio

Get your deploy key from The Graph Studio and run:

```bash
npx graph auth <your-deploy-key>
```

## 🚀 Deploying a Subgraph

You can now deploy using the available scripts:

Examples:

```bash
# Deploy V2 on Sepolia
yarn subgraph:deploy:sepolia

# Deploy V3 on Sepolia
yarn deploy:sepolia:v3
```

<div style="background-color: #f8d7da; padding: 10px; border-radius: 5px; margin-bottom: 10px;">
<strong>⚠️ Important:</strong> Make sure the slug you use matches exactly the "Display Name" in The Graph Studio.
</div>

Manual deployment example:

```bash
VERSION=v3 BLOCKCHAIN=v3 NETWORK=mainnet env-cmd npm run prepare:subgraph && SLUG=nexus-mm-mainnet env-cmd npm run subgraph:deploy
```

During deployment, you'll be asked to enter a version name.
If you're unsure what to enter, just check existing versions in Studio and follow the naming pattern.
