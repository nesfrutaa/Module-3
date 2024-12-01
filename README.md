Here’s a simplified version of the README:

---

# MyToken Smart Contract

This is a simple ERC-20 token contract called **MyToken** with minting, burning, and transferring features.

## Token Details

- **Name**: Clarisse
- **Symbol**: 202111295
- **Standard**: ERC-20

## Features

1. **Minting**: Only the contract owner can create new tokens.
2. **Burning**: Any user can burn their own tokens to reduce the supply.
3. **Transfer**: Users can transfer tokens to others, with a balance check.

## Installation

### Prerequisites

- **Solidity**: ^0.8.17
- **Node.js**
- **OpenZeppelin Contracts**: Install via npm

### Steps to Install

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/MyToken.git
   cd MyToken
   ```

2. Install dependencies:
   ```bash
   npm install @openzeppelin/contracts
   ```

## Deployment

Use **Truffle** or **Hardhat** for deployment. Here’s an example using Hardhat:

1. Create a deployment script (`scripts/deploy.js`):

```js
async function main() {
  const [deployer] = await ethers.getSigners();
  console.log("Deploying with:", deployer.address);

  const MyToken = await ethers.getContractFactory("MyToken");
  const myToken = await MyToken.deploy();

  console.log("MyToken deployed to:", myToken.address);
}

main().catch((error) => {
  console.error(error);
  process.exitCode = 1;
});
```

2. Deploy:
   ```bash
   npx hardhat run scripts/deploy.js --network yourNetwork
   ```

## Usage

- **Mint tokens** (only for the owner):
  ```js
  await myToken.mint("0xRecipientAddress", 1000);
  ```

- **Burn tokens** (any user can burn their tokens):
  ```js
  await myToken.burn(500);
  ```

- **Transfer tokens**:
  ```js
  await myToken.transfer("0xRecipientAddress", 100);
  ```

## License

MIT License

---

This version is more concise and provides only the essential information. Let me know if you need any adjustments!
