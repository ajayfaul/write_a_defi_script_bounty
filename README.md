# Bounty Write a Defi Script

This script interacts with Uniswap and Aave to perform token swaps and supply liquidity on the Sepolia testnet. It leverages Ethereum smart contracts and the ethers.js library to automate the process of swapping USDC for LINK and subsequently supplying LINK to the Aave lending pool.

## Environment Prerequisites

- Git: Ensure Git is installed on your system for cloning the repository.
- Node.js: Make sure Node.js is installed (preferably version 18 or higher).
- NPM: Node.js package manager is required to install dependencies.

## Project Setup and Installation ⚙️

1. Clone the repository

```bash
git clone https://github.com/ajayfaul/write_a_defi_script_bounty
```

2. Navigate to the project directory:

```bash
cd write_a_defi_script_bounty
```

3. Install the necessary dependencies & libraries

```bash
npm install --save
```

4. Make sure to set up your environment variables (`RPC_URL` and `PRIVATE_KEY`) in a .env file in the root directory of the project.

## Running the Script

```bash
node index.js
```

## Script Execution

Run the script to execute the following tasks:

1. Approve USDC Token:
   Approves the specified amount of USDC to be spent by the Uniswap swap router.
2. Get Pool Information:Retrieves the Uniswap pool address for the USDC-LINK trading pair.Fetches details like token addresses and fee from the pool contract.
3. Prepare Swap Parameters:Prepares the parameters needed to perform a token swap from USDC to LINK.
4. Execute Swap:Executes the swap transaction using Uniswap's swap router.
   Logs the LINK amount received from the swap.
5. Approve LINK Token for Aave: Approves the LINK token to be used by the Aave lending pool.
6. Supply LINK to Aave: Supplies the swapped LINK tokens to the Aave lending pool to start earning interest.

Now that you're set up, you're ready to start the quest! 🏁 Follow the steps as outlined in the campaign. Each step contains detailed instructions to guide you through the process. 📜

Happy questing~ 🎉
