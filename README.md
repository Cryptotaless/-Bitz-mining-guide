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

### Step 1: Install Dependencies
First, update your system and install some necessary tools:
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install screen curl nano git -y
Step 2: Install Rust
Rust is the programming language used to build Bitz miner. We need to install it:

bash
Copy
Edit
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
Step 3: Install Solana CLI
Solana is used to interact with the Eclipse network.

bash
Copy
Edit
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
After installation, if you get an error like solana: command not found, you can fix it by adding Solana to the path:

bash
Copy
Edit
echo 'export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
solana --version
Step 4: Set up RPC Configuration
Next, set the Solana RPC URL to Eclipse Network's public endpoint:

bash
Copy
Edit
solana config set --url https://eclipse.helius-rpc.com/
Step 5: Generate Solana Wallet
Generate a Solana wallet which will be used for receiving Bitz rewards:

bash
Copy
Edit
solana-keygen new
Securely save the Seed Phrase and Public Key for future use.

Step 6: Fund Your Wallet
Send a small amount of ETH to your Solana wallet using the Eclipse Network bridge to fund the mining process. This is needed to pay for transaction fees.

Step 7: Install Bitz Miner
Once the dependencies and setup are complete, install the Bitz miner:

bash
Copy
Edit
cargo install bitz
Step 8: Start Mining
Now, start mining by running the miner:

bash
Copy
Edit
screen -S bitz
bitz collect
If you want to use more CPU cores:

bash
Copy
Edit
bitz collect --cores 4
Step 9: Monitor and Detach
You can monitor the mining process, and if you want to detach and leave it running in the background:

Detach: Press Ctrl + A, then press D

Re-attach: screen -r bitz

Step 10: Useful Commands
Check your wallet balance: bitz account

Claim rewards: bitz claim

Help: bitz -h

📣 Troubleshooting
Solana Error: Command Not Found

Run the following command to add Solana to your path:

bash
Copy
Edit
echo 'export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
Low Hash Rate

Ensure your system is not overloaded with other processes.

Use more CPU cores with bitz collect --cores 4.

RPC Connection Issues

Check the Eclipse Network status at Eclipse Network Status.

Try changing RPC to a different endpoint.

🔑 Additional Resources
Eclipse Network Official Docs

Solana Docs

Bitz Token Overview
