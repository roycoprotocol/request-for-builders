# Request for Builders

A series of exciting applications that can be built on Royco. Please note this does not provide or substitute for legal advice.
Anyone and everyone is invited to contribute to this repo. 


### 1. Custom strategy allocator

#### Background

Most onchain users are looking to earn yield. Some of them are super active, constantly rebalancing and assessing the risks of each new farm. Whereas others, are super passive and haven't opened their wallet in months. With the invention of Royco, there is now a shared standard for all different yield-earning activities. However, it requires active management, even moreso when it comes to things like valuing points.

Below, we propose a solution that enables anyone to construct their own yield strategy, or opt-in to a pre-defined one. This solution is completely decentralized, and serves both passive and active users.


#### How

##### Key components: 

StrategyAdmin: A smart contract that anyone can interact with. Anyone can create a Strategy by selecting a list of IAMs they want to be allocated to. When creating a Strategy, it is also possible to set up an "Owner" who has the ability to modify the list of IAMs. Initially, strategies will only optimize for yield but it's possible to specify more complex strategies here in the future.

MasterVault: The MasterVault contains all user assets in a single vault and is in charge of rebalancing. The MasterVault receives instructions on how to rebalance and who has earned what yield from the MerkleChallenger. Additionally, when the MasterVault is currently allocated into a IAM within a strategy, it establishes limit orders on the remaining IAMs at a higher yield. 

MerklePoster: The MerklePoster calculates the appropriate rebalances, and yield and posts it onchain as a merkle root. 

MerkleChallenger: The MerkleChallenger ensures the MerklePoster has posted accurate data. This means there will be a verification delay. This can powered by a decentralized network of nodes, or an EigenLayer AVS.

##### User flow: 
1. User to deposit assets alongside their desired strategy (opt-in to someone else or build their own) into MasterVault. 
2. User will automatically get rebalanced by the MerklePoster.

<img width="675" alt="Screenshot 2024-09-17 at 2 27 41 PM" src="https://github.com/user-attachments/assets/a4915c54-a27a-456f-b432-0c3355605b2c">

##### Benefits
1. Capital efficiency: the MasterVault is establishing limit orders across all IAMs, meaning capital can move seamlessly between IAMs to earn the highest yield. 
2. Minimized attack surface: the rebalances being verified allow actors to ensure that funds aren't being drained. 
3. Gas efficiency: since all assets are inside the MasterVault, a coincidence of wants may enable a user to save money on gas by just swapping who owns each position. 

Note: 0xngmi has also written about a similar implementation here: https://gist.github.com/0xngmi/653aa70d3162f0ef4a41d56ced602a6c 


### 2. Decentralized market making

#### Background
The current methods for attracting liquidity are crude. When onchain, the only option is MasterChef which leaves no room for optimization. Whereas offchain, there are various venues but they preclude absolute competition and only support CEXs. The ideal solution is entirely onchain and runs an extremely competitive offering. 

#### How 

Build a factory that allows for IAMs with a singular action: LP on ExchangeX. 

Allow token projects and market makers to bid in realtime for folks to provide that liquidity. 

This should result in maximum participation for participants and the cheapest price for token projects. 


### 3. Unstoppable interface

#### Background 

Royco is a protocol that should outlast any person on this planet. In pursuit of that, the more unstoppable interfaces there are, the better it is for the fragility of the protocol. 

#### How

Build an interface for Royco on IPFS that cannot be stopped.

It is possible to monetize with a fee switch, as well. 


/ TO FINISH / 
### 4. Grant matcher

#### Background 
Build a system where folks (like Gitcoin) can do match grants in the most market-efficient way. 


#### How


### 7. Chain-powered liquidity

#### Background 

#### How

### 8. Demand tester 

#### Background 

#### How


### 9. Insurance 

#### Background 

#### How


