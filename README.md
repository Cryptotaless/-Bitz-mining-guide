# -Bitz-mining-guide
"Complete BITZ token mining guide by CryptoTales"  
# 🧠 BITZ Token Mining Setup Guide – By Cryptotales
## 📌 What is BITZ?
Bitz (BITZ) is a cryptocurrency token that runs on the **Eclipse Network**. It's a Proof of Work (PoW) based token that can be mined with your PC or VPS. By mining Bitz, you can earn this cryptocurrency which can be used for trading or staking.

## 📦 System Requirements
- **OS**: Ubuntu 22.04 (Laptop or VPS)
- **Hardware**: Minimum 2GB RAM, Multi-core CPU, Stable internet connection
- **Storage**: 100GB+ SSD recommended for smooth mining

## 🔧 Installation Steps
## Install Dependecies
**1. Install Packages**
```bash
sudo apt-get update && sudo apt-get upgrade -y

sudo apt install screen curl nano  -y
```
**2. Install Rust**
```bash
 curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
* When Prompted, Enter `1` and wait unti installation compelete.
```bash
source $HOME/.cargo/env
```
**3. Install Solana CLI:**
```bash
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
```
* Close and reopen your Terminal.
```
solana version
```
* If you get `solana: command not found` RUN :
```bash
echo 'export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
```
solana --version
```

**4. Switch RPC**
```bash
solana config set --url https://eclipse.helius-rpc.com/
```

---

## Wallet CLI
### . Create a CLI wallet
```bash
solana-keygen new
```
---

## Install Bitz
```bash
cargo install bitz
```

---

## Run Bitz Miner
### 1. Open a screen

```bash
screen -S bitz
```

### 2. Start Miner
```bash
bitz collect
```

![image](https://github.com/user-attachments/assets/7c526a4b-07da-4ad5-889f-17674761b5e7)


### Usefull Commands

Check account info:
```bash
bitz account
```

To integrate Node & Backpack address

```bash
cat ~/.config/solana/id.json
```

Claim Bitz to your Node Wallet:
```bash
bitz claim
```
Edit  CPU Utilization, Use Ctrl+C, then replace your 8 with your system cores.
```bash
bitz collect --cores 8
```

minimize screen:
  ```bash
  Ctrl+A+D
  ```
ON/OFF: 
```bash
screen -r bitz
 ```
