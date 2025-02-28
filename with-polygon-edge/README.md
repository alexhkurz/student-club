# README.md

A prototype implementation of a blockchain-based DApp for the decentralized governance of a student club.

Currently abandoned due to deprecation issues.

## Setup

To set up the local blockchain network:

1. Install Polygon Edge

2. Generate validator keys for each validator node:
   ```bash
   polygon-edge secrets init --data-dir validator1
   polygon-edge secrets init --data-dir validator2  
   polygon-edge secrets init --data-dir validator3
   ```

At the time of writing, these commands generated the following keys:

**Validator 1**

- Public key: 0x02f7bADA2B75BFEF6fBF9AD9E09c4CB49f2233dB
- Node ID: 16Uiu2HAmQK4QfU4qnGJ71xVpRMHCB32xnMFHshZq8du6m5oUGXrf
- BLS Public key: 0xae929489194202d62b5235ebec82e147a99c1a5b3def2e5002f4b8a35531d7db4824b844383648b41bbf11bc1d01ca3b

**Validator 2**
- Public key: 0x05ABf4Ad806f4bA10d1164936c3A758CD7A704e0
- BLS Public key: 0xa477260232aaaf4f98ac36897c2540aa0242731bef80290a033d617d04a4234f3a8b073bce66821fc8486862ec5ed518
- Node ID: 16Uiu2HAm9F3daYVqyYZqRgPK67XBTBjgtHxzT6BGZbuMwQBpccgS

**Validator 3**
- Public key: 0xEbBE53118e322C6A9CF695A79427EE3a3FF677e2
- BLS Public key: 0x80a1156068471d66f051124d327fdeac8d074c04be3da111385833bfd0c5ab8db83cbd43b384f09b35c4b5c187bfc7d7
- Node ID: 16Uiu2HAmTiT9QrW2kuQq1nLbSU51J2mxUjNnzxZDAvt4wo8zFtwc

3. Create [genesis.json](polygon-edge/genesis.json) file with validator addresses and chain configuration.

**Network Configuration**
- Chain ID: 100
- RPC Port: 8545
- P2P Port: 30301

## Starting the network

Start each validator node with the appropriate configuration:
   ```bash
   ./polygon-edge server --data-dir ./validator1 --chain genesis.json --grpc-address :10000 --libp2p :30301 --jsonrpc :8545 --seal
   ./polygon-edge server --data-dir ./validator2 --chain genesis.json --grpc-address :20000 --libp2p :30302 --jsonrpc :8546 --seal
   ./polygon-edge server --data-dir ./validator3 --chain genesis.json --grpc-address :30000 --libp2p :30303 --jsonrpc :8547 --seal
   ```

The network should now be running with 3 validator nodes in a Proof of Authority consensus configuration.


