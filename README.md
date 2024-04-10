# solana-nft

Here's i provide a guide for creating a full UI for a Candy Machine and setting up an SPL token:

---

# Creating a Full UI for a Candy Machine and Setting Up an SPL Token

In this guide, we'll walk through the process of creating a full user interface (UI) for a Candy Machine and setting up an SPL token on the Solana blockchain.

## Project Overview


1. **Create an SPL Token**: We'll create a new SPL token on the Solana blockchain.
2. **Configure Candy Machine**: We'll configure the Candy Machine for minting NFTs (Non-Fungible Tokens).
3. **Build UI for Candy Machine**: We'll develop a user-friendly interface for users to interact with the Candy Machine.

## Getting Started

### 1. Set Up Your Environment

- Ensure that you have Node.js and npm (Node Package Manager) installed on your computer.

### 2. Create a React Application

- Initialize a new React application using Create React App or your preferred React setup.

### 3. Set Up a New Wallet

- Create a new wallet specifically for Devnet testing.

```bash
cd your_project_directory
npm init -y
npm install solana-web3.js
```

### 4. Establish a Connection to Your QuickNode RPC

- Connect your Solana CLI to a node for faster response times.

```bash
solana config set --url YOUR_QUICKNODE_URL
```

## Prepare NFT Assets

### 1. Configure Candy Machine

- Create a new file named `config.json` in your project root folder and add the configuration for the Candy Machine.

```json
{
    "price": 0.01,
    "number": 10,
    "symbol": "NB",
    "sellerFeeBasisPoints": 500,
    "solTreasuryAccount": "YOUR_WALLET_ADDRESS",
    "creators": [
        {
            "address": "YOUR_WALLET_ADDRESS",
            "share": 100
        }
    ]
}
```

### 2. Validate Candy Machine Configuration

- Run the following command to validate the configuration:

```bash
sugar validate
```

### 3. Create Candy Machine

- Upload your assets, deploy the Candy Machine, and verify it.

```bash
sugar upload
sugar deploy
sugar verify
```

### 4. Test Your Candy Machine

- Mint test NFTs using the Candy Machine.

```bash
sugar mint
```

## Set Up a Minting Site

- Use Candy Machine UI for the easiest setup.
- Clone the Candy Machine UI repository and configure it with your Candy Machine ID and Solana network endpoint.

```bash
git clone https://github.com/metaplex-foundation/candy-machine-ui ./candy-machine-ui/
cd candy-machine-ui
```

- Rename `.env.example` to `.env` and update the configuration.

```bash
REACT_APP_CANDY_MACHINE_ID=<YOUR_CANDY_MACHINE_PUBKEY>
REACT_APP_SOLANA_NETWORK=devnet
REACT_APP_SOLANA_RPC_HOST=<YOUR_QUICKNODE_DEVNET_ENDPOINT>
```

- Install dependencies and start the UI.

```bash
npm install
npm start
```

## Usage

1. Start the development server: `npm start`
2. Open your browser and navigate to `http://localhost:3000` to use the UI.

## License

This project is licensed under the [MIT License](LICENSE).

---
