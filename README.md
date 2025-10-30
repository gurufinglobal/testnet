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

**Software Dependencies**
```bash
sudo apt update -y
sudo apt upgrade -y
sudo apt-get install -y wget
```

## Gurud Installation

Check binary download url: [here](https://github.com/gurufinglobal/guru/releases/tag/v2.0.1).

```bash
# example for amd64 Linux
wget https://github.com/gurufinglobal/guru/releases/download/v2.0.1/guru-v2_2.0.1_Linux_amd64.tar.gz
mkdir -p guru
tar -zxvf ./guru-v2_2.0.1_Linux_amd64.tar.gz -C ./guru/
sudo mv ./guru/bin/gurud /usr/local/bin/
```

>After installation, if enter the `gurud version` command, the version should be displayed.

## Full-Sync Steps
**Step 1. Set variables**
```bash
MONIKER="YOUR_NODE_NAME"
CHAIN_ID="guru_631-1"
PEERS="d36c5074078b71ea0a3cb53096fd8f1cd0c9da0e@trpc-state1.gurufin.io:26656,fcb10968c4877f1747e55d1d8bd71a9cd7754122@trpc-state2.gurufin.io:26656"
```

**Step 2. Init node**
```bash
gurud init $MONIKER --chain-id $CHAIN_ID
```

**Step 3. Setup config**
```bash
gurud config set client chain-id $CHAIN_ID
gurud config set config moniker $MONIKER --skip-validate
gurud config set config p2p.persistent_peers $PEERS --skip-validate
gurud config set config p2p.max_packet_msg_payload_size 10240 --skip-validate
wget -O $HOME/.gurud/config/genesis.json https://raw.githubusercontent.com/gurufinglobal/testnet/refs/heads/main/genesis.json
```

**Step 4. Run node**
```bash
gurud start
```

## Resources
- **Docs**: <https://docs.gurufin.com>
- **Faucet**: <https://faucet.gurufin.io>
- **Explorer**: <https://tscan.gurufin.io>
