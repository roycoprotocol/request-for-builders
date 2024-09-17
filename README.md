# Request for Builders

A series of exciting applications that can be built on Royco. Please note this does not provide or substitute for legal advice.
Anyone and everyone is invited to contribute to this repo. 


## 1. Custom strategy allocator

### Background

Most on-chain users are looking to earn yield on their assets. Some are highly active, constantly rebalancing and assessing the risks of each new yield opportunity. Others are passive, rarely interacting with their wallets. With the advent of Royco, there is now a shared standard for various yield-earning activities. However, maximizing returns still requires active management, especially when it comes to valuing points and navigating different incentive structures.

We propose a solution that enables anyone to construct their own yield strategy or opt into a predefined one. This solution is entirely decentralized and serves both passive and active users.


### How

#### Key components: 

StrategyAdmin: A smart contract that allows users to create and manage custom strategies. Users can select a list of Incentive Action Markets (IAMs) they want to allocate to. When creating a strategy, users can specify an "Owner" who has the ability to modify the list of IAMs. Initially, strategies will focus on optimizing for yield but can be extended to include more complex strategies in the future.

MasterVault: The MasterVault holds all user assets in a single vault and is responsible for rebalancing according to the chosen strategies. It interacts directly with Royco's ERC4626i vaults and uses the Royco Protocol's standard interfaces for deposits, withdrawals, and rewards management.

MerklePoster: The MerklePoster calculates the appropriate rebalances and yield distributions and posts this information on-chain as a Merkle root. This component uses off-chain computation to optimize strategies and leverages Royco's orderbooks for efficient execution.

MerkleChallenger: The MerkleChallenger ensures that the data posted by the MerklePoster is accurate. It provides a verification layer that allows actors to challenge incorrect data. This process can be powered by a decentralized network of nodes or an EigenLayer Active Validator Set (AVS). It interacts with Royco's smart contracts to enforce challenges and corrections.


<<<<<<< Updated upstream
#### User flow: 
1. User to deposit assets alongside their desired strategy (opt-in to someone else or build their own) into MasterVault. 
2. User will automatically get rebalanced by the MerklePoster.

<img width="675" alt="Screenshot 2024-09-17 at 2 27 41 PM" src="https://github.com/user-attachments/assets/a4915c54-a27a-456f-b432-0c3355605b2c">

#### Benefits
1. Capital efficiency: the MasterVault is establishing limit orders across all IAMs, meaning capital can move seamlessly between IAMs to earn the highest yield. 
2. Minimized attack surface: the rebalances being verified allow actors to ensure that funds aren't being drained. 
3. Gas efficiency: since all assets are inside the MasterVault, a coincidence of wants may enable a user to save money on gas by just swapping who owns each position. 
=======
##### User flow: 
1. Deposit Assets: Users deposit assets into the MasterVault, specifying their desired strategy (either opting into an existing one or creating their own). The MasterVault uses Royco's ERC4626i vault interface for asset management.
2. Automated Rebalancing: The MerklePoster calculates optimal rebalancing actions based on data from Royco's orderbooks (VaultOrderbook and RecipeOrderbook). It posts a Merkle root on-chain containing the rebalancing instructions.
3. Verification and Execution: The MerkleChallenger verifies the Merkle root. Upon successful verification, the MasterVault executes the rebalances by interacting with the relevant IAMs through Royco's standard interfaces.
4. Yield Distribution: Users receive yield based on their allocations and the performance of their chosen strategies. The rewards are managed using Royco's reward distribution mechanisms within the ERC4626i vaults.

<img width="675" alt="Screenshot 2024-09-17 at 2 27 41 PM" src="https://github.com/user-attachments/assets/a4915c54-a27a-456f-b432-0c3355605b2c">

##### Benefits
1. Capital Efficiency: The MasterVault establishes limit orders across all IAMs using Royco's orderbooks, allowing capital to move seamlessly between markets to earn the highest yield.
2. Minimized Attack Surface: The verification process ensures that rebalances and yield distributions are accurate, protecting user funds from malicious actions. This leverages Royco's built-in security features and the transparency of on-chain data.
3. Gas Efficiency: By aggregating assets within the MasterVault, users can benefit from reduced gas costs due to economies of scale and potential netting of transactions. Interacting directly with Royco's optimized contracts further enhances gas efficiency.
>>>>>>> Stashed changes

Note: 0xngmi has also written about a similar implementation here: https://gist.github.com/0xngmi/653aa70d3162f0ef4a41d56ced602a6c 


## 2. Decentralized market making

<<<<<<< Updated upstream
### Background
The current methods for attracting liquidity are crude. When onchain, the only option is MasterChef which leaves no room for optimization. Whereas offchain, there are various venues but they preclude absolute competition and only support CEXs. The ideal solution is entirely onchain and runs an extremely competitive offering. 
=======
#### Background
Current methods for attracting liquidity are suboptimal. On-chain options like MasterChef contracts lack flexibility and optimization. Off-chain venues often preclude absolute competition and primarily support centralized exchanges (CEXs). An ideal solution is entirely on-chain and offers a highly competitive environment for liquidity providers and token projects.
>>>>>>> Stashed changes

### How 

Build a factory that allows for the creation of IAMs with a singular action: providing liquidity on a specific decentralized exchange (DEX), such as Uniswap or SushiSwap. This factory leverages Royco's protocol to standardize incentive mechanisms and interactions. Allow token projects and market makers to bid in realtime for folks to provide that liquidity. 

This should result in maximum participation for participants and the cheapest price for token projects. 

<<<<<<< Updated upstream

## 3. Unstoppable interface
=======
### 3. Unstoppable interface
>>>>>>> Stashed changes

### Background 

Royco is a protocol that should outlast any person on this planet. In pursuit of that, the more unstoppable interfaces there are, the better it is for the fragility of the protocol. 

### How

Build an interface for Royco on IPFS that cannot be stopped.

It is possible to monetize with a fee switch, as well. 


/ TO FINISH / 
## 4. Grant matcher

### Background 
Build a system where folks (like Gitcoin) can do match grants in the most market-efficient way. 


### How


## 7. Chain-powered liquidity

### Background 

### How

## 8. Demand tester 

### Background 

### How


## 9. Insurance 

### Background 

### How


