# Bounty Write a DeFi Script

This script interacts with Uniswap and Aave to perform token swaps and supply liquidity on the Sepolia testnet. It leverages Ethereum smart contracts and the ethers.js library to automate the process of swapping USDC for LINK and subsequently supplying LINK to the Aave lending pool.

## Illustration

Here are the illustrations of the script in action:
![Illustration](https://github.com/ajayfaul/write_a_defi_script_bounty/blob/main/diagram.png)

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

```env
RPC_URL=your_rpc_url
PRIVATE_KEY=your_private_key
```

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

The script is configured to swap 1 USDC for LINK and supply the received LINK tokens to Aave. Adjust the main() function call to change the amount of USDC to swap.

## Key Functions

Key Functions of index.js

1. `approveToken(tokenAddress, tokenABI, amount, wallet)`
   **Purpose:** Approves a specified amount of a token to be spent by the Uniswap swap router.
   **Key Actions:**
   Creates a contract instance for the token.
   Populates and sends an approval transaction.
   Waits for and logs the transaction confirmation.
2. `getPoolInfo(factoryContract, tokenIn, tokenOut)`

Purpose: Retrieves information about the Uniswap pool for a given trading pair.
Key Actions:
Fetches the pool address from the factory contract.
Creates a contract instance for the pool.
Retrieves and returns details like token addresses and fee.
prepareSwapParams(poolContract, signer, amountIn)

Purpose: Prepares the parameters required for a token swap on Uniswap.
Key Actions:
Gets the pool fee.
Sets up parameters including token addresses, amount to swap, and minimum output amount.
getTokenBalance(tokenAddress, wallet)

Purpose: Retrieves the balance of a specified token for a given wallet.
Key Actions:
Creates a contract instance for the token.
Fetches and formats the token balance.
executeSwap(swapRouter, params, signer)

Purpose: Executes a token swap transaction on Uniswap.
Key Actions:
Logs the balance of the output token before the swap.
Sends a swap transaction.
Waits for and logs the transaction confirmation.
Logs the balance of the output token after the swap and calculates the swapped amount.
approveLendingPool(tokenAddress, amount, wallet)

Purpose: Approves a specified amount of LINK to be used by the Aave lending pool.
Key Actions:
Creates a contract instance for the token.
Populates and sends an approval transaction.
Waits for and logs the transaction confirmation.
supplyToAave(lendingPool, amount, tokenAddress, wallet)

Purpose: Supplies LINK tokens to the Aave lending pool.
Key Actions:
Sends a supply transaction to Aave.
Waits for and logs the transaction confirmation.
main(swapAmount)

Purpose: Coordinates the overall process of swapping USDC for LINK and supplying LINK to Aave.
Key Actions:
Approves USDC for the swap router.
Retrieves pool information and prepares swap parameters.
Executes the swap and calculates the received LINK amount.
Approves LINK for Aave and supplies it to the lending pool.

### Example Output

![Example Output](https://github.com/ajayfaul/write_a_defi_script_bounty/blob/main/output.png)
