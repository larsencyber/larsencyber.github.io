---
title: Performing Re-Entrancy Attacks on the Ethereum Blockchain
summary: Despite mainstream media, boot camps and universities claiming there is a cyber security skills shortage, and that you can become a professional "in just 24 weeks", it hasn't been made clear that the shortage is of experienced professionals, and not entry level candidates. This creates a "chicken and the egg" scenario, as individuals struggle to secure their first role. 
date: 2022-02-22
authors:
  - admin
tags:
  - bsides perth
  - conference presentation
  - ethereum
  - reentrancy attacks
image:
  caption: 'Image credit: BSides Perth 2021'
---
This article is for those that missed my BSides Perth 2021 talk on Performing Re-Entrancy Attacks on the Ethereum Blockchain. Unfortunately there was some technical issues on the day and not all of my slides were not visible on the stream, however if you'd like to listen to this presentation, you can do so on YouTube at the 4:31:16 time mark.

{{< youtube id="opnc_3fCkkQ?t=16276" >}}


# Performing Re-Entrancy Attacks on the Ethereum Blockchain
## Introduction
Today I will be walking you through the most well known Ethereum smart contract flaw, known as the re-entrancy attack. This attack, is also known as a race-to-empty attack, which intends to recursively loop a withdrawal until a smart contract balance is emptied.

This is like withdrawing $50 from an ATM over and over again, until the ATM runs out of money. This flaw was first unveiled in early 2016, when a hacker drained 3.5 million Ethereum from the smart contract balance of a Decentralised Autonomous Organisation, known as The DAO. This 3.5 million Ethereum was worth $70 million AUD at the time, but would be worth over $12.5 billion AUD today.

## Warning
Before I go into more detail about what we will be covering today, I'd like to give a small warning. Whilst bitcoin and cryptocurrency are hot topics, I want to make it clear that this talk is not about worldwide adoption, or how every business should go out and implement a blockchain solution. I do not agree with this, and I am not a preacher for "all things crypto". However, we can't deny that blockchain has become much more mainstream in recent years. As it evolves and grows at an exponential rate, it is important we as cyber security professionals understands how it works, so that it can be protected and defended, to better serve our communities. Before we dive into the detail of re-entrancy attacks, it is important we cover some fundamentals of blockchain, Ethereum and smart contracts.

## Fundamentals of Blockchain
Blockchain technology is a new way of maintaining agreements and tracking ownership through a decentralised ledger. In modern society, it is not humanely possible to track ownership of all assets and manage agreements in one place. Currently this issue is solved by maintaining central registries. For example:
* Department of Transport keeps track of vehicle ownership using a registry of registration plates.
* ICANN and domain registrars track who own what websites.
* Commonwealth Bank keeps an up-to-date ledger of the balance of account holders.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img1.png)

Blockchain challenges the use of these centralised ledgers, by allowing society to track ownership through a decentralised and distributed ledger. A decentralised ledger does not rely on a central authority, and rather relies on group consensus of who owns what. Before a transaction is added to the decentralised ledger, there is a series of steps that it must go through.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img2.png)

1. Each transaction is digitally signed by its creator using their private key to prove that it is legitimate.
2. At regular intervals, these transactions are combined into blocks, and the block creator digitally signs the entire block with their own private key, before sending it to the rest of the blockchain network.
3. Once consensus is achieved by the network, the block is added to chain of other blocks, each linked by a hash of the previous block. This ties the blocks together, since the collision resistance of the hash function makes it computationally infeasible for an attacker to generate a fake version of a block that hashes to the value stored in the block after it.
4. The blockchain is then added to the distributed ledger and communicated to other nodes using peer-to-peer networking. Each node in the network stores it's own copy of the ledger, and these copies are kept in sync via the consensus algorithm.

**Therefore, once a transaction is made and added to the distributed ledger, there is no simple method to reverse it, and in most situation becomes completely unrecoverable.**

## Fundamentals of Ethereum & Smart Contracts
Cryptocurrency relies on the use of distributed and decentralised ledgers for tracking ownership. The cryptocurrency which is relevant for today's discussion is Ethereum. Ethereum is a decentralised, open source blockchain with smart contract functionality, and is the largest cryptocurrency by market capitalisation after Bitcoin, at $500 billion AUD.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img3.png)

Smart contracts can be seen as the simplest form of decentralised automation, following rules triggered by predefined conditions. Smart contracts operate just like normal binding agreements in the physical world, however remove the requirement to trust a third party for execution.

For example, if a group of investors would like to get involved in a project, they could use a website such as Kickstarter. Kickstarter would take the investors deposit, minus a fee, and provide it to the project creators. If the project was not able to be completed or encountered issues, investors would rely on Kickstarter as a trusted third party to reimburse them.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img4.png)

However, if the investors and project creators came together and agreed on all of their rules of interactions, they could implement these rules in a smart contract which is guaranteed to be enforced by the network.

Ethereum smart contracts implement the capability to execute arbitrary code on the blockchain within the "Ethereum Virtual Machine", known as EVM. EVM is just an interpreter for the EVM assembly language, and as the interpreter runs, it maintains a stack and memory byte array. However, EVM is very limited compared to other virtual machines, as there is no way to do input/output, make API calls, or generate random numbers, which makes it a simple deterministic state machine.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img5.jpg)

Writing smart contracts in assembly is no fun, so a high-level objected oriented programming language called Solidity was created to compile into EMV assembly. We will review some smart contracted written in Solidity further into this article. 

## Smart Contract Security Considerations
Due to the unique structure and architecture of smart contracts, there are a variety of security considerations that must be accounted for in development. 
1. **Contract Lifetimes** - Smart contracts are part of the immutable blockchain and as such as permanent. Whilst a developer can build a "kill switch" or update mechanism to a smart contract, the code is there forever. Even with a dormant smart contract, an attacker may be able to find ways to bypass the kill switch mechanism to exploit it. 
2. **Untrusted Code** - The design of the blockchain means that every node in the blockchain network will be regularly running untrusted code on their computers. Smart contracts are permitted to interact with other smart contracts, and as such this means that developers are creating software which will run any program that it comes across. This includes malicious smart contracts.
3. **External Interfaces** - A major issues of smart contracts is that they allow external components to interact with the blockchain. This means that these external components are within the blockchain's security perimeter and also part of it's attack surface. Vulnerable external components can potentially compromise the smart contracts they are connected to and vice versa.
4. **Turing-Completeness** - Smart contracts are designed to be Turing-complete. This means that they have the same capabilities as a standard computing program. Code as law arbitration means that attacks arising from programming errors are unlikely to be reversed.

Now that we have considered some fundamentals of blockchain, Ethereum and smart contracts, we can move into understanding the re-entrancy attack on The DAO.

## The DAO and a 3.5 Million Ethereum Heist
The DAO is an acronym for Decentralised Autonomous Organisations. This term is used describe a complex interacting set of smart contracts which aim to resemble the fundamentals of an organisation, by interacting with individuals and transacting with some sort of asset. The DAO in question, was released by a German start-up called Slock.IT with the intention to create an investment fund for projects, similar to the earlier example compared to Kickstarter.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img6.png)

At launch investors received 100 DAO tokens for every 1 Ethereum deposited in the smart contract fund. These DAO tokens gave them governance over the DAO smart contract and represented their share of The DAO. 

Token holders could also submit proposals for investment. For example a proposal could be made to invest some of The DAO's funds into the stake of an organisation. Once the proposal passed initial verification, it could be voted on by all of the other investors. Token holders could vote yes or no to support the proposal.

However, there still needed to be a way to protect the minority of investors. 
**What if a minority group strongly disagreed with a proposal that they can't out vote?**

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img7.png)

Instead of voting no, they could call a split function. This would move their DAO token s from the main DAO to a child DAO. It was a standard procedure for anyone to call a split as the new child DAO included the functionality to reclaim their invested Ethereum to their wallet. **We will be referencing split function in the re-entrancy attack in detail further in the article.**

When The DAO went live on 30th April 2016, it raised over 11 million Ethereum in the first 2 weeks. This was almost 14% of all Ethereum available at the time. However, whilst the crowd funding project had a lot of success, it became quite an attractive financial target for threat actors.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img8.png)

In less than 2 months since being live, the DAO smart contract attacked by a threat actor. The smart contract was drained of over 3.5 million Ethereum in 48 hours. At the time, this was worth roughly $70 million AUD, but today would be over $12.5 billion AUD. 

**The DAO was drained due to a re-entrancy attack which allowed an attacker to recursively call the split function, and withdraw tokens from the main DAO to their own child DAO.**

## Performing Re-Entrancy Attacks
![](/blog/2021-11-27-reentrancy-attacks-ethereum/img9.jpg)

Before we walkthrough the technical details of this attack, let's go over a high level explanation. Imagine you have $50 in your bank account and you want to withdraw that from an ATM.
1. You insert your card, enter your pin number and request that $50.
2. Before the machine spits the cash out, it checks your balance.
3. Once it spits out the cash, it will debit $50 from its internal state, which is your balance.
4. Next, the machine asks if you'd like to process another transaction.
5. You tap yes, and try to take that $50 out again.
6. But the ATM sees that your balance is now $0 and refuses.
7. It asks you again if you want to process another transaction, so this time you say no and the session ends.

**Now imagine that the ATM didn't update your balance until you ended the session. You could keep requesting that $50 again, and again until you finally told the machine you didn't want to process any more transactions or the machine ran out of money.**

The DAO smart contract relied on 6 Solidity files to perform its operations. These files wee responsible for a variety of tasks including automating organisation governance and decision making, checking token balances, sending tokens, approval processes, managing rewards and fallbacks.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img10.png)

The **DAO.sol file contained a vulnerable function called splitDAO which was targeted.** This function was responsible for withdrawing tokens from the main DAO smart contract to a child DAO smart contract, which could eventually be exchanged for Ethereum. The attacker was analysing this function and noticed it was vulnerable to the recursive send or withdraw pattern.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img11.png)

The splitDAO function was vulnerable because it updates user balances and totals at the end. If an attacker can get any of the function calls before this happens to call splitDAO again, an infinite recursive loop is created. This can then move as many tokens as there are available in the main DAO smart contract. So when the main DAO goes to withdraw the attacker's tokens, the attacker will call the function to execute a new split before that withdrawal finishes.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img12.png)

Now looking at the withdrawRewardFor function, if the attacker could get the first if statement on line 2 to evaluate to false, the statement marked as vulnerable on line 7 would run. When that statement runs, the payOut function code would be called. 

Line 5 would then send a message from the DAO's contract to the recipient. This would contain a default function that would **call splitDAO again** with the same parameters as the initial call from the attacker, **starting the infinite recursive loop.**

I understand this might be a little hard to keep up with, so I have re-created this re-entrancy attack with simple code in a testnet environment.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img13.png)

Here are two smart contracts that will mimic the vulnerable behaviour of the DAO. 
* Contract V is the Victim and has a withdraw function, which mimics the ATM in our previous example.
* Contract A is the Attacker, and has a fallback function, which mimics the person withdrawing from the ATM in our previous example.

The intent is for Contract A to call back into Contract V, whilst Contract V is still executing. Let's say Contract V holds 1 Ethereum that belongs to Contract A, but it also holds a total of 9 Ethereum from other users, the same way a bank account would hold the balance of other account holders. Therefore the overall balance of Contract V is 10 Ethereum.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img14.png)

1. The first step of the re-entrancy attack relates to the attack function inside Contract A. The intent is to have the attack function, call the withdraw function inside Contract V. 
2. Contract V then check's Contract A's internal balance to see if it is greater than zero, the same way an ATM would.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img15.png)

3. As it has 1 Ethereum, it sends that 1 Ethereum back to Contract A, and also triggers the fallback function. This means that now Contract V's overall balance is 9 Ethereum and Contract A's overall balance is 1 Ethereum.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img16.png)

4. Now the fallback function inside Contract A calls back into the withdraw function inside Contract V. 
5. Contract V then check's Contract A's internal balance to see if it is greater than zero. You can see above that **Contract A's Balance still appears as 1 Ethereum.**

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img17.png)

6. As Contract A's balance hasn't changed, this check passes. Contract V sends another 1 Ethereum to Contract, **which triggers the fallback function again.**
7. Now Contract V's overall balance is 8 Ethereum, and Contract A's overall balance is 2 Ethereum. However, the internal balance of Contract A inside Contract V still hasn't updated.

This is because the fallback function creates a recursive loop. **It will continue to call back to the withdraw function inside Contract V until the overall balance is emptied. Contract A's balance inside Contract V will never update.** This was how the DAO was able to be drained by the attacker.

##  Mitigations & The DAO Resolution
![](/blog/2021-11-27-reentrancy-attacks-ethereum/img18.png)
To mitigate re-entrancy attacks in future smart contract development, there are a variety of techniques and tools that can be used. One of the major issues with securing smart contracts is that the technology is so new. It is expected that developers have limited understanding of how it operates under the hood. While the number of Solidity developers and experts are increasing, it is still far behind traditional programming languages. A change in mindset of developers is ultimately required for defeating this type of attack.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img19.png)

Due to the decentralised nature and code-as-law arbitration of the smart contract, the creators of The DAO could not interface with the attack was it was occurring. They couldn't update the smart contract and had to watch on as the balance was draining. From that moment on, the child DAO which contained the stolen tokens would be known as the Dark DAO.

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img20.png)

Whilst the main DAO was being drained, a team of Whitehat hackers came together to see if they could prevent the hacker from withdrawing all of the funds. They initiated the same re-entrancy attack, with a larger recursive withdrawal amount and transferred the remaining roughly 7.5 million Ethereum to a safely controlled Child DAO.

Now the remaining funds were under control, the Ethereum community needed to determine what the next step would be. **Would they honour the decentralised nature of smart contracts and accept the heist, or would they find an alternative way to retrieve all of the stolen funds?**

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img21.png)

Ultimately the Ethereum network decided that a hard fork was required. When there is a lack of consensus in the network, nodes may attempt to re-write history with a new divergent blockchain. This divergent blockchain is a duplicate of the original chain but includes upgrades to re-write the ownership of funds.
If enough nodes or miners agreed that the divergent blockchain was the new legitimate distributed ledger, the original blockchain would be abandoned. However, only 85% of nodes agreed with the hard fork, and therefore 15% of the miner nodes continued to use the legacy blockchain. **This legacy blockchain still exists today and is known as Ethereum Classic.**

![](/blog/2021-11-27-reentrancy-attacks-ethereum/img22.png)

In summary, once the hard fork occurred, it included upgrades that allowed the stolen funds to be sent to a withdrawal contract. This withdrawal contract was then accessed by the original investors and their DAO tokens were exchanged for Ethereum.

The choice to perform a hard fork of the entire network required buy-in from the community. If another smart contract today was to be exploited by a re-entrancy attack, I highly doubt that another hard fork would be completed. Therefore, it is of paramount importance that smart contract developers use any of the mitigations provided in this article to prevent this type of attack from occurring again in the future.

*"The modern, high-tech bank heist does not require a gun, a mask, or a getaway car. It requires only the internet and ingenuity."*