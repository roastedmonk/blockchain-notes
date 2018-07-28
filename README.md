## Blockchain

This repo is about notes on the MOOC [Blockchain for Business - An Introduction to Hyperledger Technologies](https://www.edx.org/course/blockchain-business-introduction-linuxfoundationx-lfs171x) by The Linux Foundation.

And other Blockchain personal notes.

## Background - The Rising Interest in Distributed Ledger Technologies

Looking back to the last half century of computer technologies and architectures, one may observe a trend of fluctuation between the centralization and subsequent decentralization of computing power, storage, infrastructure, protocols, and code.

Mainframe computers are largely centralized. They typically house all computing power, memory, data storage, and code. Access to mainframes is mainly by 'dumb terminals', which only take inputs and outputs, and do not store or process data.

With the advent of personal computers and private networks, similar computational capabilities were now housed both on the clients, as well as the servers. This, in part, gave rise to the 'client-server' architecture, which supported the development of relational database systems. Massive data sets, which are housed on mainframes, could move onto a distributed architecture. This data could replicate from server to server, and subsets of the data could be accessed and processed on clients, and then, synced back to the server.

Over time, Internet and cloud computing architectures enabled global access from a variety of computing devices; whereas mainframes were largely designed to address the needs of large corporations and governments. Even though this 'cloud architecture' is decentralized in terms of hardware, it has given rise to application-level centralization (e.g. Facebook, Twitter, Google, etc).

Currently, we are witnessing the transition from centralized computing, storage, and processing to decentralized architectures and systems. According to [Muneeb Ali](https://medium.com/@muneeb/the-next-wave-of-computing-743295b4bc73), these systems aim to "give explicit control of digital assets to end-users and remove the need to trust any third-party servers and infrastructure".

Distributed ledger technology is one of the key innovations making this shift possible.


## Distributed Ledger Technology (DLT)


A **distributed ledger** is a type of data structure which resides across multiple computer devices, generally spread across locations or regions.

**Distributed Ledger Technology** includes blockchain technologies and smart contracts. While distributed ledgers existed prior to Bitcoin, the Bitcoin blockchain marks the convergence of a host of technologies, including timestamping of transactions, Peer-to-Peer (P2P) networks, cryptography, and shared computational power, along with a new consensus algorithm. 

In summary, distributed ledger technology generally consists of [three basic components](https://intelledger.github.io/introduction.html):

* A data model that captures the current state of the ledger
* A language of transactions that changes the ledger state
* A protocol used to build consensus among participants around which transactions will be accepted, and in what order, by the ledger.

## Blockchain Definition

According to [hyperledger.org](https://hyperledger.org/about),

> "A blockchain is a peer-to-peer distributed ledger forged by consensus, combined with a system for "smart contracts" and other assistive technologies."

*Smart contracts* are simply computer programs that execute predefined actions when certain conditions within the system are met.

*Consensus* refers to a system of ensuring that parties agree to a certain state of the system as the true state.

## Blockchain - Block's Anatomy Introduction

Blockchain is a specific form or subset of distributed ledger technologies, which constructs a chronological chain of blocks, hence the name 'block-chain'. A block refers to a set of transactions that are bundled together and added to the chain at the same time. In the Bitcoin blockchain, the miner nodes bundle unconfirmed and valid transactions into a block. Each block contains a given number of transactions. In the Bitcoin network, miners must solve a cryptographic challenge to propose the next block. This process is known as 'proof of work', and requires significant computing power. We shall discuss proof of work in more detail in the Consensus Algorithms section. For a brief history of blockchain technology, please click here.

Timestamping is another key feature of blockchain technology. Each block is timestamped, with each new block referring to the previous block. Combined with cryptographic hashes, this timestamped chain of blocks provides an immutable record of all transactions in the network, from the very first (or genesis) block.

A block commonly consists of four pieces of metadata:

* The reference to the previous block
* The proof of work, also known as a nonce
* The timestamp
* The Merkle tree root for the transactions included in this block.

## Merkle Tree

The Merkle tree, also known as a binary hash tree, is a data structure that is used to store hashes of the individual data in large datasets in a way to make the verification of the dataset efficient. It is an anti-tamper mechanism to ensure that the large dataset has not been changed. The word 'tree' is used to refer to a branching data structure in computer science, as seen in the image below. According to Andreas M. Antonopoulos, in the Bitcoin protocol,

> "Merkle trees are used to summarize all the transactions in a block, producing an overall digital fingerprint of the entire set of transactions, providing a very efficient process to verify whether a transaction is included in a block."

![Merkle Tree](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/5bef2699f0c33f98eb3ccb6c2526b447/asset-v1:LinuxFoundationX+LFS171x+3T2017+type@asset+block/Bitcoin_Block_Data.png)

## Transactions

The record of an event, cryptographically secured with a digital signature, that is verified, ordered, and bundled together into blocks, form the *transactions* in the blockchain. In the Bitcoin blockchain, transactions involve the transfer of bitcoins, while in other blockchains, transactions may involve the transfer of any asset or a record of some service being rendered. Furthermore, a smart contract within the blockchain may allow automatic execution of transactions upon meeting predefined criteria.

*Cryptography* has a key role to play both in the security, as well as in the immutability of the transactions recorded on blockchains. Cryptography is the study of the techniques used to allow secure communication between different parties and to ensure the authenticity and immutability of the data being communicated. For blockchain technologies, cryptography is used to prove that a transaction was created by the right person. It is also used to link transactions into a block in a tamper-proof way, as well as create the links between blocks, to form a blockchain.


## Differences between Blockchains and Databases


Blockchain technology has some key differentiators from databases. 

A blockchain is a write-only data structure, where new entries get appended onto the end of the ledger. Every new block gets appended to the block chain by linking to the previous block's 'hash' (you can check the Glossary tab for a refresher on hash functions). There are no administrator permissions within a blockchain that allow editing or deleting of data.

In a relational database, data can be easily modified or deleted. Typically, there are database administrators who may make changes to any part of the data and/or its structure. Additionally, blockchains were designed for decentralized applications, whereas relational databases, in general, were originally designed for centralized applications, where a single entity controls the data.

![Differences DB vs Blockchain](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/d387060c18e43cb6f676f10c56443ce7/asset-v1:LinuxFoundationX+LFS171x+3T2017+type@asset+block/Centralized_Databases_vs_Blockchain.png)


## Types of Blockchains

A blockchain can be both **permissionless** (like Bitcoin or Ethereum) or **permissioned** (like the different Hyperledger blockchain frameworks). A permissionless blockchain is also known as a public blockchain, because anyone can join the network. A permissioned blockchain, or private blockchain, requires pre-verification of the participating parties within the network, and these parties are usually known to each other.

The choice between permissionless versus permissioned blockchains should be driven by the particular application at hand (or use case). Most enterprise use cases involve extensive vetting before parties agree to do business with each other. An example where a number of businesses exchange information is the supply chain management. The supply chain management is an ideal use case for permissioned blockchains. You would not want non-vetted companies participating in the network. Each participant that is involved in the supply chain would require permissions to execute transactions on the blockchain. These transactions would allow other companies to understand where in the supply chain a particular item is. 

On the contrary, when a network can 'commoditize' trust, facilitating parties to transact without necessarily having to verify each other's identity, like the Bitcoin blockchain, a permissionless blockchain is more suitable. Many of these instances involve the sale or distribution to the public. Cryptocurrencies and Initial Coin Offerings (which are not backed by national governments) usually involve implementations of permissionless blockchains.

You will learn about a variety of use cases in Chapter 3, *The Promise of Business Blockchain Technologies*.

## Peer-to-Peer Network Architecture

Historically, most applications utilize a central server (or servers). For one user/client to send a message to another user/client in the network, the request has to be sent to the hub or a central server, which then directs it to the right computer.

Peer-to-peer (P2P) networks were first made popular by Napster (and later BitTorrent) and consist of computer systems which are directly connected to each other via the Internet, without a central server. Peers contribute to the computing power and storage that is required for the upkeep of the network. P2P networks are generally considered to be more secure than centralized networks, as they do not have a single point of attack, as in the case of a server-based network, where the security of the entire network can be compromised if the central server is successfully attacked. As a result, large corporations invest significant amounts of financial resources to fortify their central servers, and yet, a total cost of $445 billion to the global economy in cyberspace crimes was estimated by the World Economic Forum's [2016 Global Risk Report](https://www.weforum.org/reports/the-global-risks-report-2016).

Permissionless P2P systems do not require a set amount of peers to be online and are generally slower. Permissioned P2P networks have to guarantee uptime and require a high level of quality of service on the communication links.

![Network Architectures](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/99e70ee58cba3930923df89a997e65be/asset-v1:LinuxFoundationX+LFS171x+3T2017+type@asset+block/Network_Architectures.png)

## Immutability of Data

The immutability of the data which sits on the blockchain is perhaps the most powerful and convincing reason to deploy blockchain-based solutions for a variety of socio-economic processes which are currently recorded on centralized servers. This immutability, or 'unchanging over time' feature makes the blockchain useful for accounting, financial transactions, identity management, and asset ownership, management and transfer, just to name a few examples. Once a transaction is written onto the blockchain, no one can change it, or, at least, it would be extremely difficult to change it.

According to Antony Lewis, the Director of Research at R3,

"When people say that blockchains are immutable, they don't mean that the data can't be changed, they mean it is extremely hard to change without collusion, and if you try, it's extremely easy to detect the attempt."

Let's dig into this statement a bit further. It is extremely hard to change the transactions in a blockchain, because each block is linked to the previous block by including the previous block's hash. This hash includes the Merkle root hash of all the transactions in the previous block. If a single transaction were to change, not only would the Merkle root hash change, but so too would the hash contained in the changed block. In addition, each subsequent block would need to be updated to reflect this change. In the case of proof of work, the amount of energy required to recalculate the nonce for this block and each subsequent block would be prohibitive. On the other hand, if someone did modify a transaction in a block without going through the necessary steps to update the subsequent blocks, it would be easy to recalculate the hashes used in the blocks and determine that something is amiss.

Let's look at an example of how this works. In the following diagram, we see the original blocks and the transactions for Block 11. Specifically, we see that the Merkle root for the transactions in Block 11 is Hash #ABCD, which is the combined hash for the four transactions in this block. Now, let's say that someone comes in and attempts to change Transaction A to Transaction A'. This, in turn, modifies the hashes that are stored in the Merkle tree, and the Merkle root changes to Hash #A'BCD. In addition, the Previous Block hash stored in Block 12 also needs to be modified to reflect the overall change in the hash for Block 11.

![Immutability](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/7b24ffd61a0fcdc9c147463892a273da/asset-v1:LinuxFoundationX+LFS171x+3T2017+type@asset+block/BLOCKCHAIN_IMMUTABILITY.png)

## Blockchain Applications

Since blockchain is a new form of digital infrastructure, applications built on top of a blockchain provide a gateway to accessing information that sits on that blockchain. In other words, clients/users interact with the blockchain through applications. Starting from the simple wallets that hold bitcoins, sophisticated applications which encompass applications addressing digital identity (e.g. UPort, KYC-Chain, Netki, etc.), and complex financial transactions are being built on the blockchain.

A more exhaustive list of companies using blockchain technology for identity management and authentication can be found [here](https://letstalkpayments.com/22-companies-leveraging-blockchain-for-identity-management-and-authentication/).

For more details about blockchain applications, you can refer to Daniel Palmer's article at [coindesk.com](https://www.coindesk.com/7-cool-decentralized-apps-built-ethereum/).

## Smart Contracts

**Smart contracts** are simply computer programs that execute predefined actions when certain conditions within the system are met. Smart contracts provide the **language of transactions** that allow the ledger state to be modified. They can facilitate the exchange and transfer of anything of value (e.g. shares, money, content, property).

![Smart Contracts](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/ec30b3736f17bdbbc1a7bc6e08380094/asset-v1:LinuxFoundationX+LFS171x+3T2017+type@asset+block/Blockchain_and_Smar_Contracts_-_Flow_Diagram.png)

Understanding Hyperledger Sawtooth — Proof of Elapsed Time
Sawtooth, like Fabric, is a permissioned blockchain network technology. The network is called permissioned because prospective participants must identify themselves to the network, and the network can decide whether to let them participate. Once in the network, participants share a view of the blockchain ledger. The network uses a consensus algorithm to make sure all participants see identical ledgers.

Consensus algorithms come in different forms. For example, Bitcoin uses a proof-of-work system. Members of the Bitcoin network compete to solve a cryptographic puzzle that identifies the solver as the new leader — the authoritative party for the new block on the blockchain. It’s essentially a lottery for choosing who is responsible for adding the new block. Proof-of-stake is another lottery system, except the lottery is based on ownership of coin in the system. The more coin a participant owns, the more likely they are to be chosen as the leader for a new block.

In addition to lottery-like systems, there are also other kinds of consensus algorithms. For example, permissioned blockchain networks like Sawtooth and Fabric can also use traditional Byzantine fault tolerance (BFT) algorithms, which are often based on voting.

Sawtooth and Fabric are both designed to allow users to choose the consensus algorithm for their blockchain network. Today, we’ll look at a lottery-like algorithm used with Hyperledger Sawtooth called proof-of-elapsed-time.

Proof of Elapsed Time (PoET)
At a high level, proof-of-elapsed-time follows this strategy:

Each participant in the blockchain network waits a random amount of time.
The first participant to finish waiting gets to be leader for the new block.
In order for this to work, two requirements must be verified. First, did the lottery winner actually choose a random wait time? Otherwise, a participant could intentionally choose a short wait time in order to win. Second, did the lottery winner actually finish waiting the specified amount of time?

PoET comes from Intel, and it relies on a special CPU instruction set called Intel Software Guard Extensions (SGX). SGX allows applications to run trusted code in a protected environment. For PoET, the trusted code is what ensures that these two requirements are satisfied — keeping the lottery fair.

Intel SGX
Before going into what PoET’s trusted code does, let’s understand some key points about SGX.

A specialized hardware component can create an attestation that some particular trusted code was set up correctly in a protected environment. e.g. An external party can use the attestation to verify that the right code is running the right way.
Trusted code runs in an environment that is private to the rest of the application. e.g. The rest of the application can’t inspect or interfere with the memory space of the trusted code.
The first point allows a network participant to prove to other participants that it is running the right trusted code for the network. Without this feature, there’s no way for the network to know whether a participant is actually running the PoET trusted code.

The second point ensures that a malicious participant can’t cheat by manipulating the PoET trusted code after it’s been set up.

PoET’s trusted code
The details of the protocol are somewhat complex, but here’s a simplified outline:

Joining the network

A new participant downloads the trusted code for the blockchain.
On initialization, the trusted code creates a new keypair.
Participant sends a SGX attestation (which includes the trusted code’s public key) to the rest of the network as part of a join request.
Participating in the lottery

Participant obtains a signed timer object from the trusted code.
Participant waits for the time specified by the timer object.
Participant obtains a certificate (signed by the trusted code’s private key) that the timer has completed. Participant sends this certificate to the rest of the network along with the new block for the blockchain.
The protocol also involves other protections on top of SGX. For example, the network measures how often a given participant wins the lottery in order to detect participants with a compromised SGX system. Bad actors can then be blacklisted.

Conclusion
Hyperledger Sawtooth can use a proof-of-elapsed-time (PoET) consensus algorithm that leverages Intel’s Software Guard Extensions (SGX) to implement a leader-election lottery system. Instead of using computational effort to solve cryptographic puzzles (like Bitcoin), the system uses a trusted execution environment to generate random wait times—potentially a much more energy-efficient approach.

To learn more about Sawtooth, including additional details about the PoET protocol, check out the project’s docs!


##Pros and Cons of Different Blockchain Consensus Protocols
Blockchain consensus protocols allow a decentralized network to arrive at an agreement about the state of the blockchain. There are different ones for different types of blockchains and each has its pros and cons.

Selecting — and then implementing the right consensus protocol (or consensus algorithm) — is a key decision to make early in your blockchain project. Consensus protocols allow the blockchain to confirm transactions without relying on a third party. And, of course, getting rid of intermediaries and decentralizing is at the heart of blockchain.

Put simply, the consensus algorithm seeks to ensure that the next block to be added is, as nearly every blog and tech publication puts it, “the one and only version of the truth.” At the same time, it’s also designed to keep bad actors from tampering with or undermining the blockchain network.

Consensus allows a decentralized network to arrive at an agreement about the state of the blockchain. Unless everyone participating on the blockchain is totally honest and pure of heart, consensus is essential.

“Consensus is the backbone of the blockchain and any other decentralized and distributed technology,” writes Collin Thompson, co-founder of Intrepid Ventures.

Here’s a look at several blockchain consensus protocols. We’ll start with the best known.

Proof-of-Work (PoW)
“The correct way of thinking about the proof-of-work concept is as a means for a group of self-interested people, none of whom is subordinate to any other, to establish a consensus against a considerable incentive to resist it. Bitcoin could operate perfectly well without proof-of-work, as long as everyone was perfectly honest and altruistic. If they are not, then reaching a consensus is difficult.” — Satoshi Nakamoto Institute

The first — and still most common — distributed blockchain protocol mechanism is called “proof-of-work.” It’s most closely associated with Bitcoin, which introduced it to the world, but many cryptocurrencies have subsequently adopted it. It’s designed for a public (or permissionless) blockchain.

blockchain consensus protocolWhen a transaction is initiated, “miners” get to work on solving a cryptographic puzzle.

Miners have what lay people would call “supercomputers.” The computing power, or “hashrate,” gives them an advantage in solving the puzzle, which allows them to add the next block to the chain. The puzzle they solve is difficult and requires substantial computational power (or, work). Just how hard it is varies: In Bitcoin, for example, it’s programed so that one block is produced every 10 minutes. The difficulty of the puzzle automatically adjusts to make that happen.

The first miner to solve the puzzle receives newly minted Bitcoins, plus a small transaction fee.

PoW was first; hence it’s currently the most popular. It’s also highly scalable, which makes it attractive. But it has major drawbacks. Among them:

Energy consumption: The miners’ “supercomputers” test millions of computations per second, and this is happening around the world. Due to the amount of computational power required, PoW is costly and energy intensive. To quote the MIT Technology Review, “It's been estimated that Bitcoin guzzles about as much electricity annually as all of Nigeria.” That’s not sustainable and, as this CoinDesk piece points out, most PoW mining is done in areas of the world where electricity is cheap. One (controversial) aspect of this particular complaint is that these computations are useless. Mathematician Andrew Tar makes the case in a Cointelegraph piece. “Miners do a lot of work to generate blocks and consume a lot of power. However, their calculations are not applicable anywhere else. They guarantee the security of the network but cannot be applied to business, science or any other field.”
Vulnerability: PoW is vulnerable to a “51% attack,” meaning — in theory — nefarious miners could capture 51 percent of a network’s computing power, gain what’s termed “dominance“ and manipulate the blockchain to their advantage.
Ethereum, like Bitcoin, uses PoW; however, it’s slated to move to a proof-of-stake algorithm in its 2018 Serenity release.

Proof-of-Stake
Proof-of-Stake (PoS) algorithms are designed to overcome the disadvantages of PoW — in particular, high energy consumption. PoS, in its various permutations, is the most common alternative to PoW. Like PoW, it’s also designed for a public blockchain.

Instead of miners with fancy — and costly — computer equipment racing to mine blocks, a “validator” invests cryptocurrency. (Which type of coin depends on the system, of course.)

A white paper from Persistent Systems offers a useful explanation:

“Instead of a user spending say $2,000 buying mining equipment to engage in PoW algorithm and winning a mining reward, with PoS she can buy $2,000 worth of cryptocurrency and use it as stake to buy proportionate block creation chances in the blockchain system by becoming a ‘validator.’”

There’s no guarantee the individual validator will be selected, no matter how much he or she invests. That’s because the PoS algorithm randomly selects validators for block creation. In that sense, it’s like a lottery: The more you invest, the better your chances. Validators are paid processing fees — no new coins are minted or mined in the process.

Peercoin, blackcoin, and NXT were among the first to use PoS.

Among PoS’s benefits are

Speed: Provides faster processing of transactions
Efficiency: Consumes less energy
Less hardware: Doesn’t require a “supercomputer”
Among its drawbacks are

Vulnerability: Someone with enough money to invest exclusively into the destruction of this system can do so by investing only money, as opposed to PoW where they need to invest money, time, expertise, hardware, electricity, etc.
The rich get richer: Only the richest stakeholders are permitted to have control of consensus in the blockchain.
PoS has different variations. Perhaps the most common is delegated proof-of-stake.

Delegated Proof-of-Stake (DPoS)
With DPoS blockchain consensus protocols, coin holders use their coin balances to elect delegates, called witnesses. These witnesses have the opportunity to stake blocks of new transactions and add them to the blockchain. Voting power is determined by cyberwealth. Those who have more coins or tokens will have a greater impact on the network that those with fewer.

It’s natural to wonder if the name was changed to “witnesses” from “delegates” to avoid overt political overtones. But in fact, it’s probably the best available analogy. Consider this description from “CaptainAltcoin”:

"Delegated Proof-of-Stake and traditional Proof-of-Stake are very different, and the difference can be compared to the difference between direct democracy and representative democracy. In regular PoS, every wallet that contains coins is able to ‘stake.’ This means it can participate in the process of validating transactions and forming the distributed consensus and to earn coins in return. In a DPoS system every wallet that contains coins is able to vote for delegates."

In addition to the benefits of PoS, DPoS offers:

Better distribution of rewards: People will elect only those delegates who give them the most rewards, so casual users — not just the “rich” — earn rewards. (This democratization makes DPoS more decentralized than either PoS or PoW.)
Real-time voting security: Any malicious action by a witness can be immediately detected by the voters, who can oust the offending delegate.
So, what’s the downside?

Cartels: Witnesses could organize into cartels.
Easier to organize an attack: Because fewer people are in charge of keeping the network alive, it’s easier to organize a “51%” attack
Potentially more centralized: Power is again concentrated in the hands of a few.
Does all this sound vaguely familiar? Again, the political analogies are obvious. This time, the challenge —  be it blockchain or a nation —  is voter apathy. “It’s also subject to voter apathy; without a large number of engaged users, the system will not function as intended,” observes an Invest in Blockchain piece.

Leased Proof of Stake (LPoS)
This is another, less common variation on PoS. It was developed by WAVES, a decentralized blockchain platform that allows for the creation of custom tokens. It attempts to address the “rich get richer” issues. It also aims to improve security, given that network security is better when there are more participants. To those ends, it seeks to incentivize those with fewer coins to lease out their balances to nodes.

The coins make the node stronger — or gives it more “weight,” — increasing its chances of being allowed to add a block to the blockchain. The rewards received are shared with those who leased their coin balance to the “winning” node. (This is a contrast to DPoS, where participants aren’t necessarily rewarded directly.)

Proof of elapsed time PoET
Hyperledger Sawtooth, originally developed by Intel, is a modular blockchain platform. What may be generating the most buzz is its blockchain consensus algorithm: proof of elapsed time (PoET). What’s so notable? For one thing, it’s applicable to permissioned and public platforms. More importantly, it lets users on a permissioned blockchain reach consensus, even when the parties don’t know each other. (Other permissioned blockchains require that users know and trust each other.)

PoET is similar to proof of work but without the high resource consumption. Simply put, it leverages trusted computing to enforce random waiting times for block construction. According to Intel, it’s the first lottery-based consensus for Blockchain. It’s designed to work in what are called “trusted execution environments,” such as Intel’s Software Guard Extension (SGX). In PoET’s random leader-election model based, the protocol selects the next leader in the block. Like most others we discussed, it requires far less energy than does PoW.

The downsides:

Reliance on Intel: As a piece in CoinDesk puts it, “The one problem with this protocol is it requires you to put your trust in Intel – and isn’t putting trust in third parties what we were trying to get away from with public blockchains?”
Hardware requirement: It relies on specialized hardware.
Practical Byzantine Fault Tolerance (PBFT)
PBFT is the most popular permissioned blockchain platform protocol and is currently used by Hyperledger Fabric.

To understand the Practical Byzantine Fault Tolerance algorithm, you need to understand the Byzantine generals’ problem. You probably do, but it’s worth a review, especially if you pass this post along to one of your less-tech-savvy colleagues.

Credit goes to Leslie Lamport, Robert Shostak, and Marshall Pease, who posed the problem in a 1982 academic paper. Different versions have circulated, but let’s keep it simple. Imagine a group of Byzantine generals and their armies have surrounded a castle and preparing to attack. To win, they must attack simultaneously. But they know that there is at least one traitor among them. So, how do they launch a successful attack with at least one, unknown, bad actor in their midst?

The analogy is clear: In any distributed computing environment — blockchain — there is a risk that rogue actors could wreak havoc. So, its reliance on community consensus makes Byzantine faults an especially thorny problem for blockchain.

PoW generally provides a solution: “Byzantine fault tolerance.” But the drawbacks may not be worth it. Distributed provides one such example.

“In industries like healthcare, it may make more sense to rely on node votes. Because participants in a blockchain in healthcare are more likely to be altruistic and operate under real identities than are users of a highly anonymous, unregulated system like Bitcoin, the benefits of avoiding PoW may outweigh the risks associated with node voting as the solution to Byzantine faults.”

That’s where the Practical Byzantine Fault Tolerance algorithm comes into play. It’s considered the first practical solution to achieving consensus that overcomes Byzantine failure, according to Persistent's whitepaper. The very short version: A consensus decision is determined based on the total decisions submitted by all the generals. It addresses the challenges without the expenditure of energy required by proof-of-work. But it works only on a permissioned blockchain, because there’s no anonymity.

Some of the others
We’ve discussed the major ones. Here are a few others that are gaining a foothold.

Proof of Importance: Developed by NEM, this advances the idea that productive network activity, not just the number of coins accumulated, should be rewarded. Participants who frequently send and receive transactions are more likely to find blocks.
Proof of Activity: Proof of Activity is a hybrid approach that combines proof of work and proof of stake. As in PoW, miners race to solve a cryptographic puzzle. Then the system switches to PoS. Criticisms are the same as for both proof of work and proof of stake.
Proof of Capacity: Most of the alternatives to PoW are, in some respect, pay-to-play. In proof of capacity, you pay with your hard drive space. The more you have, the better your chance of mining the next block and earning the reward.
Proof of Burn: This requires proof of having “burned” cryptocurrency, which is accomplished by sending the coins to a wallet from which they cannot be recovered. “By committing your coins to never-never land, you earn a lifetime privilege to mine on the system based on a random selection process,” Amy Castor writes in an article for Coindesk. Critics point out that, although it doesn’t consume energy the way PoW does, it still wastes resources needlessly. And as with POS, it’s focused on those already “rich” —  those who are willing to burn more money.
The bottom line — sort of
So, what does this mean for your business? The most obvious thing is that there are many, many consensus algorithms out there. Despite that, there may not be a perfect fit. But there are some general considerations, driven by the applications you plan to deploy.

If you are envisioning a public blockchain, which requires robust consensus among a lot of unknown and untrusted participants, you may prefer a more complex model at the expense of speed. (Examples: Bitcoin’s PoW model.)

To begin, ask yourself some very basic questions:

What’s the scale of your project?
Is your blockchain public or permissioned? (Permissioned — or consortium —  blockchain projects may require faster transactions.)
What are your performance requirements?
Token or no token?
This last point may become the biggest. IBM — the brains behind Fabric — observed last year a divide is emerging between cryptocurrency-based and non-cryptocurrency- based consensus systems, arguing that the model based on cryptocurrency is unsustainable for enterprise use and permissioned blockchains. PoW and PoS, for example, use coins; PBFT and PoET do not.

It sounds overwhelming, but it doesn’t have to be. We’re here to help. Drop us a note to let us know what we can do. 

Link : https://www.verypossible.com/blog/pros-and-cons-of-different-blockchain-consensus-protocols
