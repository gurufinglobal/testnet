# Guru Testnets
This repository provides resources on Guru testnets

## Requirements
**Minimum Hardware Specifications**
| Conponents  | Specifications   |
|-------------|------------------|
| **CPU**     | 4 physical cores |
| **Memory**  | 32 GB            |
| **Storage** | 500 GB NVME      |

**Supported Operating Systems**
| Types          | Architectures |
|----------------|---------------|
| **Linux**      | amd64         |
| **Linux**      | arm64         |
| **Darwin**     | arm64         |
| **Darwin**     | x86_64        |

## Gurud Installation Stpes
**1. Clone Guru codes**
```bash
git clone https://github.com/GPTx-global/guru-v2.git
```

**2. Checkout to testnet version**
```bash
cd guru-v2 && git checkout v2.0.0
```

**3. Install binary**
```bash
make install
```

**4. Verify binary**
```bash
gurud version
```

## Download Binary
If you only want to download the binary, you can download it [here](https://github.com/GPTx-global/guru-v2/releases/tag/v2.0.0).

## Full-Sync Steps
**1. Set variables**
```bash
MONIKER="YOUR_NODE_NAME"
CHAIN_ID="guru_631-1"
PEERS="d36c5074078b71ea0a3cb53096fd8f1cd0c9da0e@trpc-state1.gurufin.io:26656,fcb10968c4877f1747e55d1d8bd71a9cd7754122@trpc-state2.gurufin.io:26656"
```

**2. Init node**
```bash
gurud init $MONIKER --chain-id $CHAIN_ID
```

**3. Setup config**
```bash
gurud config set client chain-id $CHAIN_ID
gurud config set config moniker $MONIKER --skip-validate
gurud config set config p2p.persistent_peers $PEERS --skip-validate
gurud config set config p2p.max_packet_msg_payload_size 10240 --skip-validate
wget -O $HOME/.gurud/config/genesis.json https://guru-testnet.s3.ap-northeast-2.amazonaws.com/genesis_guru_testnet_20250903.json
```

**4. Run node**
```bash
gurud start
```

## Resources
- **docs**: <https://docs.gurufin.com>
- **faucet**: <https://faucet.gurufin.io>
- **explorer**: <https://tscan.gurufin.io>
