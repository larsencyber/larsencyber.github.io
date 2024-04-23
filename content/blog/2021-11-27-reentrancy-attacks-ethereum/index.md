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