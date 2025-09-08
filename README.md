# Guru Testnets
This repository provides resources on Guru testnets

| Types    | Informations                                                                                            |
|----------|---------------------------------------------------------------------------------------------------------|
| Chain ID | guru_631-1                                                                                              |
| Version  | v2.0.0                                                                                                  |
| Genesis  | [genesis.json](https://guru-testnet.s3.ap-northeast-2.amazonaws.com/genesis_guru_testnet_20250903.json) |

## Requirements
### Minimum Hardware
| Conponents  | Specifications   |
|-------------|------------------|
| **CPU**     | 4 physical cores |
| **Memory**  | 32 GB            |
| **Storage** | 500 GB NVME      |
### Operating System
| Types          | Architectures |
|----------------|---------------|
| **Linux**      | amd64         |
| **Linux**      | arm64         |
| **Darwin**     | arm64         |
| **Darwin**     | x86_64        |

## Gurud Installation Stpes
**Install Binary**
```bash
git clone https://github.com/GPTx-global/guru-v2.git
cd guru-v2
git checkout v2.0.0
make install
```
**Check**
```bash
gurud version
# 2.0.0
```

<!--
details, endpoints, faucet
-->