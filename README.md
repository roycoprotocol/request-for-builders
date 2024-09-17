# Request for Builders

A series of exciting applications that can be built on Royco. 


### 1. Custom strategy allocator

##### Background

Most onchain users are looking to earn yield. Some of them are super active, constantly rebalancing and assessing the risks of each new farm. Whereas others, are super passive and haven't opened their wallet in months. With the invention of Royco, there is now a shared standard for all different yield-earning activities. However, it requires active management, even moreso when it comes to things like valuing points.

Below, we propose a solution that enables anyone to construct their own yield strategy, or opt-in to a pre-defined one. This solution is completely decentralized, and serves both passive and active users.


##### How

###### Key components: 

StrategyAdmin: A smart contract that anyone can interact with. Anyone can create a Strategy by selecting a list of Markets they want to be allocated to. When creating a Strategy, it is also possible to set up an "Owner" who has the ability to modify the list of Markets. Initially, strategies will only optimize for yield but it's possible to specify more complex strategies here in the future.

MasterVault: The MasterVault contains all user assets in a single vault and is in charge of rebalancing. The MasterVault receives instructions on how to rebalance and who has earned what yield from the MerkleChallenger. Additionally, when the MasterVault is currently allocated into a market within a strategy, it establishes limit orders on the remaining markets at a higher yield. 

MerklePoster: The MerklePoster calculates the appropriate rebalances, and yield and posts it onchain as a merkle root. 

MerkleChallenger: The MerkleChallenger ensures the MerklePoster has posted accurate data. This means there will be a verification delay. This can powered by a decentralized network of nodes, or an EigenLayer AVS.


###### User flow: 
1. User to deposit assets alongside their desired strategy (opt-in to someone else or build their own) into MasterVault. 
2. User will automatically get rebalanced by the MerklePoster. 

###### Benefits
1. Capital efficiency: the MasterVault is establishing limit orders across all markets, meaning capital can move seamlessly between markets to earn the highest yield. 
2. Minimized attack surface: the rebalances being verified allow actors to ensure that funds aren't being drained. 
3. Gas efficiency: since all assets are inside the MasterVault, a coincidence of wants may enable a user to save money on gas by just swapping who owns each position. 

Note: 0xngmi has also written about a similar implementation here: https://gist.github.com/0xngmi/653aa70d3162f0ef4a41d56ced602a6c 

### 2. Decentralized market making

#### Background
Build a hyper-specialized interface for incentivizing AMM pools. Run an auction similar to the current market-making platforms to identify the best participant. But allow anyone to participate and compete in real time. 

#### How 


### 3. Unstoppable interface

#### Background 

#### How

Build an interface for Royco on IPFS that cannot be stopped.

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

Disclaimer: This does not provide or substitute for legal advice.
