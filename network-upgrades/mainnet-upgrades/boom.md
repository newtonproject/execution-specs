# Boom Network Upgrade Specification

# Included EIPs
Specifies changes included in the Network Upgrade.

  - [x] [EIP-145](https://eips.ethereum.org/EIPS/eip-145): Bitwise shifting instructions in EVM
  - [x] [EIP-1014](https://eips.ethereum.org/EIPS/eip-1014): Skinny CREATE2
  - [x] [EIP-1052](https://eips.ethereum.org/EIPS/eip-1052): EXTCODEHASH opcode
  - [x] [EIP-1283](https://eips.ethereum.org/EIPS/eip-1283): Net gas metering for SSTORE without dirty maps
  - [x] [EIP-152](https://eips.ethereum.org/EIPS/eip-152): Add Blake2 compression function `F` precompile
  - [x] [EIP-1108](https://eips.ethereum.org/EIPS/eip-1108): Reduce alt_bn128 precompile gas costs
  - [x] [EIP-1344](https://eips.ethereum.org/EIPS/eip-1344): Add ChainID opcode
  - [x] [EIP-1884](https://eips.ethereum.org/EIPS/eip-1884): Repricing for trie-size-dependent opcodes
  - [x] [EIP-2028](https://eips.ethereum.org/EIPS/eip-2028): Calldata gas cost reduction
  - [x] [EIP-2200](https://eips.ethereum.org/EIPS/eip-2200): Rebalance net-metered SSTORE gas cost with consideration of SLOAD gas cost change

# Readiness Checklist

**List of outstanding items before deployment.**
 
Code merged into Participating Clients

| **Client** | EIP-X |
| ---------- | :---: |
| Geth       |   ✔   |
 
 Tasks 
- [x] Client Integration Testing
  - [x] [Integration tests](https://github.com/ethereum/tests/)
 - [x] Select Fork Blocks
   - [x] Testnet `17181218` (2020-08-08) []()
   - [x] Mainnet `18500000` (2020–09–20) []()
 - [x] Deploy Clients
   - [x]  Geth
