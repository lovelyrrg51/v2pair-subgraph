# Uniswap V2 Pair Subgraph

## Description
The Uniswap V2 One-Pair Subgraph
- TSLA/WETH Pair - https://etherscan.io/address/0xBa2A50B90f055781c2C0846C4b548980831Cc3f3
- Deployed Subgraph - https://thegraph.com/hosted-service/subgraph/lovelyrrg51/uniswap-pair

## Initialize
### 1. Update Pair Address & Block Number
- On subgraph.yaml, update your target pair address & startBlock
```
  - kind: ethereum
    name: V2Pair
    network: mainnet
    source:
      address: "0xBa2A50B90f055781c2C0846C4b548980831Cc3f3"
      abi: V2Pair
      startBlock: 18730054
    mapping:
```
- Also, on src/helpers.ts, need to update `CERTAIN_PAIR_BLOCK`
```
    // Certain Specialized Pair Created Block
    export const CERTAIN_PAIR_BLOCK = '18730054';
```
### 2. Yarn Install
```
yarn install
```

## Build & Deploy
- Build
```
    yarn codegen && yarn build
```
- Deploy
```
    graph auth --product hosted-service ${YOUR_OWN_SUBGRAPH_KEY}
    graph deploy --product hosted-service ${YOUR_OWN_SUBGRAPH_URL}
```