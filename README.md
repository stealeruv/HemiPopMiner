# HemiPoPMiner
PoP Btc Tx miner

### Project Intro
Hemi is a modular blockchain built for superior scaling, security and interoperability.
One Network, Powered by  Bitcoin and  Ethereum.

Docs : [hemiDocs](https://docs.hemi.xyz/) | X : [x.com](https://x.com/hemi_xyz) | Site : [Hemi](https://hemi.xyz/)

**Bitcoin Superfinality**

Hemi's Proof-of-Proof (PoP) consensus mechanism ensures transactions surpass Bitcoin's level of security in just a few hours.
__________________________________________________________________________________________________________________________________________

### Testnet 

📣Hemi Incentived Testnet (Backed by Binance Labs)

- Join and complete testnet task
- Start earning hemi miles 

Hemi Miles are a metric designed to recognize and reward early participants in the Hemi ecosystem.

Task link: https://points.absinthe.network/hemi/start

Paste Ref code: **284f5931**

Sepolia Eth Faucet : https://www.alchemy.com/faucets/ethereum-sepolia | https://www.infura.io/faucet/sepolia

Stable coins Faucet : https://staging.aave.com/faucet/

Complete Ongoing task and climb up the leaderboard 🚀
__________________________________________________________________________________________________________________________________________
## System Requirements

| **Hardware** | **Minimum Requirement** |
|--------------|-------------------------|
| **CPU**      | 2 Cores                 |
| **RAM**      | 2 to 4GB                |
| **Disk**     | 50 to 100 GB            |
| **Bandwidth**| 10 MBit/s               |

Join : [Crypto Console Telegram](https://t.me/cryptoconsol)

Follow : [Crypto Console Twitter](https://www.x.com/cryptoconsol)

Subscribe : [Crypto Console Youtube](https://www.youtube.com/@cryptoconsole)

Crypto VPS : [https://vpsdime.com](https://vpsdime.com/a/4418/linux-vps)

### Update and Install jq
```
sudo apt-get update
sudo apt-get install -y jq
```


### Download the Binary

For x86_64 Architecture:

```
wget https://github.com/hemilabs/heminetwork/releases/download/v0.5.0/heminetwork_v0.5.0_linux_amd64.tar.gz
```
```
tar -xzvf heminetwork_v0.5.0_linux_amd64.tar.gz
```
### Wallet create
```
./keygen -secp256k1 -json -net="testnet" > ~/popm-address.json
```
### View Private Key and address
```
cat ~/popm-address.json
```

Save it safe.

### Public Key for faucet
```
cat ~/popm-address.json | jq -r '.pubkey_hash'
```

**Request faucet in discord** : [Hemi Discord](https://discord.gg/hemixyz)

### create a servive file
```
sudo tee /etc/systemd/system/hemid.service > /dev/null << EOF

[Unit]
Description=Hemi testnet pop tx Service
After=network.target

[Service]
WorkingDirectory=/root/heminetwork_v0.4.5_linux_amd64
ExecStart=/root/heminetwork_v0.4.5_linux_amd64/popmd
Environment="POPM_BTC_PRIVKEY= replace here with your privatkey "
Environment="POPM_STATIC_FEE=150"
Environment="POPM_BFG_URL=wss://testnet.rpc.hemi.network/v1/ws/public"
Restart=on-failure

[Install]
WantedBy=multi-user.target
EOF
```
### Start Miner service
```
sudo systemctl daemon-reload
sudo systemctl enable hemid.service
sudo systemctl start hemid.service
```
### check logs
```
sudo journalctl -u hemid.service -f -n 50
```


# Update Node

### Stop Hemid service
```
sudo systemctl stop hemid.service
```
### Remove old files

```
rm -rf heminetwork_v0.4.5-linux_arm64
rm -rf heminetwork_v0.4.5_linux_arm64.tar.gz
```

### Update and Install jq
```
sudo apt-get update
sudo apt-get install -y jq
```

### Download the Binary

```
wget https://github.com/hemilabs/heminetwork/releases/download/v0.5.0/heminetwork_v0.5.0_linux_amd64.tar.gz
```

```
tar -xzvf heminetwork_v0.5.0_linux_amd64.tar.gz
```

### Update service file

```
sudo tee /etc/systemd/system/hemid.service > /dev/null << EOF

[Unit]
Description=Hemi testnet pop tx Service
After=network.target

[Service]
WorkingDirectory=/root/heminetwork_v0.5.0_linux_amd64
ExecStart=/root/heminetwork_v0.5.0_linux_amd64/popmd
Environment="POPM_BTC_PRIVKEY= replace here with your privatkey "
Environment="POPM_STATIC_FEE=150"
Environment="POPM_BFG_URL=wss://testnet.rpc.hemi.network/v1/ws/public"
Restart=on-failure

[Install]
WantedBy=multi-user.target
EOF
```

or 

```
nano /etc/systemd/system/hemid.service
```

Edit 0.4.5 with 0.5.0


### Start Service
```
sudo systemctl daemon-reload
sudo systemctl enable hemid.service
sudo systemctl start hemid.service
```

Check you PoP **Keystones** Mined : https://testnet.popstats.hemi.network/
__________________________________________________________________________________________________________________________________________

Join Disussion : [Crypto Console Telegram](https://t.me/cryptoconsol)
