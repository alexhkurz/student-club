## README

## Setup

```bash
# Install and use Node.js v20 (LTS version)
nvm install 20
nvm use 20
node --version  # Should show v20.x.x

# Install Hardhat
npm install --save-dev hardhat

# Initialize Hardhat project
npx hardhat
```

This installs the "Sample Hardhat Project".

### Sample Hardhat Project

This project demonstrates a basic Hardhat use case. It comes with a sample contract, a test for that contract, and a Hardhat Ignition module that deploys that contract.

Run the following tasks and ask your LLM for explanations:

```bash
npx hardhat help
npx hardhat test
REPORT_GAS=true npx hardhat test
# Start the local Hardhat network
npx hardhat node
# Deploy the sample contract
npx hardhat ignition deploy ./ignition/modules/Lock.ts --network localhost
# Start Hardhat's interactive console
npx hardhat console --network localhost
# Get the deployed contract
const Lock = await ethers.getContractAt("Lock", "0x5FbDB2315678afecb367f032d93F642f64180aa3")
# Call contract functions
await Lock.unlockTime()  // View when the lock expires
await Lock.owner()       // View the contract owner
```



## Initial Planning

Here is some initial planning as suggested by an LLM. This needs more work.

For a beginner-friendly Ethereum project, the goal is to provide your students with a straightforward and well-supported environment to learn the basics of blockchain development. Here's a recommended setup:

---

### **1. Development Environment**
#### **a. Code Editor**
- **Visual Studio Code (VS Code)**: It's free, lightweight, and has excellent extensions for Ethereum development.
  - Install the **"Solidity"** extension for syntax highlighting and linting.
  - Add the **"Prettier"** extension for code formatting.

#### **b. Node.js**
- Install **Node.js** (LTS version). This is required for running JavaScript-based tools and frameworks like Truffle, Hardhat, and front-end libraries.

### **2. Ethereum Development Tools**
#### **a. Hardhat**
- Hardhat is a popular Ethereum development framework. It allows students to compile, deploy, test, and debug smart contracts.
  - Install Hardhat globally:  
    ```bash
    npm install --save-dev hardhat
    ```
  - Use the Hardhat starter project by running:  
    ```bash
    npx hardhat
    ```
  - Features perfect for beginners:
    - Built-in local Ethereum network for testing.
    - Easy integration with testing libraries like Mocha and Chai.

#### **b. Truffle Suite (Alternative)**
- Truffle is another beginner-friendly framework for Ethereum development. It provides similar functionality to Hardhat.
  - Install Truffle globally:  
    ```bash
    npm install -g truffle
    ```
  - Create a new Truffle project:  
    ```bash
    truffle init
    ```
  - Truffle comes with Ganache, a local blockchain emulator for testing.

### **3. Local Blockchain**
#### **a. Ganache**
- Ganache is a personal Ethereum blockchain for testing smart contracts. It comes with a user interface to visualize transactions.
  - Install Ganache:  
    ```bash
    npm install -g ganache
    ```
  - Start Ganache:  
    ```bash
    ganache
    ```

#### **b. Hardhat Network (Alternative)**
- If you’re using Hardhat, it includes its own local blockchain, so you don't need Ganache.

### **4. Wallet**
- **MetaMask**: A browser-based Ethereum wallet that allows students to interact with their smart contracts.
  - Install the browser extension for Chrome/Firefox.
  - Connect MetaMask to the local blockchain (e.g., Ganache or Hardhat Network).

### **5. Smart Contract Language**
- **Solidity**: The most widely-used language for Ethereum smart contracts.
  - Start with simple contracts like:
    - A "Hello World" contract.
    - A basic token (e.g., an ERC-20 token).
    - A voting system.

### **6. Front-End Integration**
- Use **React.js** for the front-end, as it integrates well with Ethereum libraries.
  - Install React via Create React App:  
    ```bash
    npx create-react-app my-dapp
    ```
  - Use **ethers.js** or **web3.js** to connect the front end to Ethereum smart contracts.

### **7. Testing and Debugging**
- Write unit tests for smart contracts using **Mocha** and **Chai** (built into Hardhat and Truffle).
- Use the **Hardhat Console** or **Truffle Console** to interact with your contracts during development.

### **8. Project Ideas for Beginners**
Here are some beginner-friendly project ideas:
1. **"Hello World" Smart Contract**: A simple contract that stores and retrieves a string.
2. **Voting System**: A contract that allows users to vote on proposals.
3. **Simple Token (ERC-20)**: Teach students the basics of tokens and ERC standards.
4. **Crowdfunding DApp**: A decentralized application where users can contribute Ether to fund a project.
5. **Todo List DApp**: A simple app to add and manage tasks on the blockchain.

### **9. Resources**
- [Solidity Documentation](https://docs.soliditylang.org/)
- [Hardhat Documentation](https://hardhat.org/)
- [Truffle Documentation](https://trufflesuite.com/)
- [MetaMask Documentation](https://metamask.io/)

