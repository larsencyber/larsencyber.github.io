---
title: "Twitter Hack: Lessons learned and why it could have been worse"
summary: This article describes the events that led to the 2020 Twitter account compromise.
date: 2020-07-23
authors:
  - admin
tags:
  - twitter hack
  - sim swapping
  - cyber security
---
This article describes the events that led to the recent Twitter account compromise, the techniques the cyber threat used, why the impact could have been much more catastrophic, and lessons learned that your organisation could incorporate to uplift cyber security maturity.

## Table of Contents
1. Summary of Events
2. Method of Compromise
3. Threat Actor Evaluation
4. Lessons Learned
5. References

## 1. Summary of Events
On Wednesday 15th July 2020, 45 of 130 targeted Twitter accounts belonging to the world's most recognisable figures were compromised. Accounts included investment mogul Warren Buffet, business magnate Bill Gates, Tesla CEO Elon Musk, Amazon CEO Jeff Bezos, presidential candidate Joe Biden, presidential candidate Mike Bloomberg and ex-president Barrack Obama[1].

![**JoeBidenHacked**](/blog/2020-07-23-twitter-hack-lessons-learned/img1.jpg)

The accounts had been identified as compromised after they began posting statements about a bitcoin scam giveaway called "CryptoForHealth", which enticed victims into sending their own bitcoin to the perpetrator's wallet, under the impression they would receive double of what they had sent in return[2]. At present time, the bitcoin wallet has received over 400 transactions accumulating almost 13 stolen bitcoin, worth approximately USD $118,000[3]. However, the true count of victims and scammed bitcoin could have been much higher as various cryptocurrency exchanges and wallets indicated that they had blocked thousands of withdrawals to the perpetrator's wallet[4].

![**FakeEthereumScam**](/blog/2020-07-23-twitter-hack-lessons-learned/img2.png)
![**DiscordMessages**](/blog/2020-07-23-twitter-hack-lessons-learned/img3.png)

Prior to the public account take-over of world leaders and business magnates, the threat actor had also compromised and sold access to inactive twitter accounts that had rare or uncommon usernames. Accounts with short and single character usernames such as @vampire, @insane, @spy, @emo and @6 are considered valuable and generally are resold to brands and social media influencers[5]. The threat actor appeared to be brokering sales of compromised twitter accounts on the underground community "OG Users".

An interview with one of the merchants on OG Users identified that threat actor went by the alias of "Kirk", as seen in the screenshot above which shows an exert of their private messages. The bitcoin address that Kirk used to collect payments from the merchants on OG Users has received almost 15 bitcoin worth approximately $143,000 USD[6]. This bitcoin address has been linked in public transactions to the same bitcoin address that was posted on the CryptoForHealth website.

## 2. Method of Compromise
The multi-account compromised was determined to have been orchestrated jointly by the same threat actor, "Kirk". They were able to take control of any twitter account they wanted after gaining unauthorised access to an internal Twitter employee's account that was highly privileged. The privilege allowed them to change the registered email on any account through an administrative dashboard. The screenshot below shows Twitter's back end for the @R9 account, with the options to "Detach" and "Add Email"[7].

![*TwitterEmployeePanel**](/blog/2020-07-23-twitter-hack-lessons-learned/img4.jpg)

The threat actor was able to obtain initial compromise by socially engineering multiple twitter employees, presumably with phishing campaigns to capture and use their Slack credentials[8]. It is assumed that the threat actor then discovered the account details in a Slack chat room or coerced another Twitter employee to disclose or reset their credentials to a highly privileged account.

With the ability to change any account's registered email, the threat actor had essentially obtained god mode. They were able to take control of any twitter account by assigning their own new email as the account's registered email. Once this had been completed, they would reset the account's password and disable multi-factor authentication.

With unrestricted access and domination of the accounts, the threat actor could not only post public messages that would immediately circulate to the account's large followers, but also download a copy of user data which included personally identifiable information about the users, and potentially sensitive commercial information from direct messages[9].

## 3. Threat Actor Evaluation
Whilst various media outlets are speculating that the attack is likely to be the working of an advanced persistent threat or state sponsored cyber warfare[10], there are various indicators that this attack was more likely the work of a singular opportunistic threat actor with only moderate technical capabilities.

Twitter is considered one of the primary tools for worldwide communication in the United States and is used regularly by world leaders and CEOs to disseminate important information and news. If the recent Twitter attack were conducted by a sophisticated criminal entity or state sponsored actors, there would have been far more devastating global impacts, similar to what was seen in April 2013 when Syrian hackers compromised The Associated Press' Twitter account[11].

![**TheAssociatedPressPost**](/blog/2020-07-23-twitter-hack-lessons-learned/img5.png)

In this case, within minutes that The Associated Press' twitter account tweeted out a false statement about the White House being under attack to its 2 million followers, the financial markets erased $136 billion USD in equity market value[12], as fear grew about the United States being under a terrorist attack. Comparing the response the financial markets made to 1 account being compromised and publishing a fake tweet, the potential damage the threat actor in the July 2020 hacks could have caused is overwhelming.

Further evidence that nominates the July 2020 hacker as unsophisticated is that they originally began their crusade by selling access to inactive twitter accounts that had rare or unusual usernames. They conducted these trades on the online market OG Users, which is notorious for being filled with script kiddies. Script kiddie is a term used to described unskilled individuals, typically juveniles that conduct cyber attacks which leverage other people's code to achieve marginal financial gains or gain credibility on forums.

![**TheOGUsers**](/blog/2020-07-23-twitter-hack-lessons-learned/img6.png)

It is clear that the threat actor had financially driven motives. However, it seems counter intuitive that they used a SegWit bitcoin address to receive funds, which is not supported yet by all major cryptocurrency exchanges and wallets[13]. By using this type of address, they limited the number of victims that would be able to transfer bitcoin to them. Additionally, the "CryptoForHealth" website that was designed by the threat actor can be considered very basic and used code that has been previously sold on other underground markets for bitcoin scam giveaways. This evidence further supports that the threat actor was not advanced or sophisticated.

## 4. Lessons Learned
Whilst Twitter could have made better decisions and implemented controls to prevent this type of attack from materialising, it is unfair to think that they should have been completely secure. Cyber threat actors can only be disrupted with layers of controls and optimised processes, not completely defeated. Defence in depth is an approach to cyber security in which a series of defensive mechanisms are layered. This multi-layered approach increases the security of the system as a whole and will address many different attack vectors[14].

If the following items were implemented, the recent Twitter account compromise might have been prevented. By implementing a combination of the controls or processes below, your organisation will uplift it's cyber security maturity and increase it's overall cyber resilience.

* Implementation of access controls such as multi-factor authentication, conditional access based on IP, segregation of duties for provisioning additional privileges or resetting accounts and single sign on.
* Implementation of a SIEM or similar solution that performs behavioural analysis and correlates log events to detect and prevent intrusions.
* Regular cyber security awareness, education and training with all employees and specialised training for employees who use highly privileged accounts.
* Routine phishing campaigns with all employees to achieve greater visibility over the human attack surface in the organisation, to identify which users are most vulnerable and require additional training.
* Supply chain cyber risk assessments to identify and assess risks that the organisation will inherent by procuring or collaborating with a third party.

The context of your organisation and it's risk appetite will determine which of the above controls are suitable to be implemented. A cyber risk assessment is the most important activity any organisation can conduct to identify and assess confidentiality, integrity and availability risks that could lead to a material business impact.

## 5. References
1. [https://www.marketwatch.com/story/prominent-twitter-accounts-hijacked-in-crypto-scam-elon-musk-and-warren-buffet-among-victims-2020-07-15](https://www.marketwatch.com/story/prominent-twitter-accounts-hijacked-in-crypto-scam-elon-musk-and-warren-buffet-among-victims-2020-07-15)
2. [https://web.archive.org/web/20200715195113/https://cryptoforhealth.com/](https://web.archive.org/web/20200715195113/https://cryptoforhealth.com/)
3. [https://www.blockchain.com/btc/address/bc1qxy2kgdygjrsqtzq2n0yrf2493p83kkfjhx0wlh](https://www.blockchain.com/btc/address/bc1qxy2kgdygjrsqtzq2n0yrf2493p83kkfjhx0wlh)
4. [https://www.theblockcrypto.com/post/72200/coinbase-says-it-prevented-over-1000-customers-from-sending-280000-worth-of-bitcoin-to-twitter-hackers](https://www.theblockcrypto.com/post/72200/coinbase-says-it-prevented-over-1000-customers-from-sending-280000-worth-of-bitcoin-to-twitter-hackers)
5. [https://www.nytimes.com/2020/07/17/technology/twitter-hackers-interview.html](https://www.nytimes.com/2020/07/17/technology/twitter-hackers-interview.html)
6. [https://www.blockchain.com/btc/address/1Ai52Uw6usjhpcDrwSmkUvjuqLpcznUuyF](https://www.blockchain.com/btc/address/1Ai52Uw6usjhpcDrwSmkUvjuqLpcznUuyF) 
7. [https://www.vice.com/en_us/article/jgxd3d/twitter-insider-access-panel-account-hacks-biden-uber-bezos](https://www.vice.com/en_us/article/jgxd3d/twitter-insider-access-panel-account-hacks-biden-uber-bezos)
8. [https://ia.acs.org.au/article/2020/here-s-how-twitter-got-hacked.html](https://ia.acs.org.au/article/2020/here-s-how-twitter-got-hacked.html)
9. [https://blog.twitter.com/en_us/topics/company/2020/an-update-on-our-security-incident.html](https://blog.twitter.com/en_us/topics/company/2020/an-update-on-our-security-incident.html)
10. [https://www.theguardian.com/technology/2020/jul/16/twitter-hack-security-concerns-privacy](https://www.theguardian.com/technology/2020/jul/16/twitter-hack-security-concerns-privacy)
11. [https://www.washingtonpost.com/news/worldviews/wp/2013/04/23/syrian-hackers-claim-ap-hack-that-tipped-stock-market-by-136-billion-is-it-terrorism/](https://www.washingtonpost.com/news/worldviews/wp/2013/04/23/syrian-hackers-claim-ap-hack-that-tipped-stock-market-by-136-billion-is-it-terrorism/)
12. [https://twitter.com/OptionsBeat/status/326778407461474304](https://twitter.com/OptionsBeat/status/326778407461474304)
13. [https://www.coindesk.com/blockchain-bites-twitter-hack-fallout-a-new-way-to-yield-farm-and-a-hurricane-proof-cbdc](https://www.coindesk.com/blockchain-bites-twitter-hack-fallout-a-new-way-to-yield-farm-and-a-hurricane-proof-cbdc)
