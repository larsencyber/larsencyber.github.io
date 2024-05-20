---
title: "Crabby's Credential Stuffing: Australian Account Takeovers in 2024"
summary: In January 2024, breaking headlines were made, with commentary from Prime Minister Anthony Albanese, that 50+ major Australian brands had customer accounts compromised through credential stuffing attacks. This article provides threat attribution, and detailed research on the adversaries involved. 
date: 2024-05-20
authors:
  - admin
tags:
  - threat research
  - cyber threat intelligence
  - offensive security
  - credential stuffing
image:
  caption: 
spacing:
  padding: ['10px', '0', '10px', '0']
---
# Abstract
In January 2024, breaking headlines were made by national Australian news agencies that 50+ major Australian brands such as Officeworks, The Iconic, and Dan Murphy's had customer accounts compromised through credential stuffing attacks. Victim customers reported stolen funds and credit card fraud.

This research concluded that compromised Australian accounts were first advertised for sale in July 2023 using public Telegram channels by a threat actor called "Based". Account sales were transacted on Discord, and two websites, before the cyber-crime business was acquired in November 2023 by an infamous international account vendor called "Juicy". This vendor rapidly rose to popularity in past year by acquiring many other well-known account shops. The Australian account shop was rebranded as "Crabby" and has utilised three websites and multiple Telegram channels to sell compromised AU accounts, which has continued to this day.

Low-level fraudsters purchasing the stolen accounts were observed to demonstrate poor operational security, often oversharing information related to their identities and the crimes they were committing. This included order reference numbers, recorded videos, and plans to collect fraudulently purchased goods including the time and store location. Whilst they are motivated by financial gain, it is clear they are also driven by the excitement and challenge of engaging in illicit activities, and would take risks in pursuit of their goals. 

This scenario prevents a challenge for law enforcement who wish to disrupt this activity, due to compromised account vendors operating out of foreign jurisdictions. The key to disrupting the rise of this crime lies in targeting the demand side of the equation. By focusing on catching and prosecuting the low-level fraudsters in Australia who are buying the compromised accounts, law enforcement can set a precedent and deter others from engaging in similar activities. 

# Detailed Research
## 1. Australian account takeovers in 2024
In the beginning of 2024, news headlines highlighted that thousands of Australian customers experienced their online accounts were being compromised and used for fraudulent transactions. It affected customers of many well known brands, such as Dan Murphy's, The Iconic, and Officeworks, to name a few. This caught the attention of the Prime Minister, who shared the following statement in January 2024:
![**Australian Prime Minister Anthony Albanese**](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/2-prime-minister.png)
>  "This is a scourge and there are so many vulnerable people being ripped off who've acted in absolutely good faith and we need to make sure they are protected." - Anthony Albanese, Prime Minister of Australia

Further reading:
* [Dan Murphy's: Credential Stuffing FAQ](https://www.danmurphys.com.au/help/help-centre/articles/8820120539535-CREDENTIAL-STUFFING-FAQs)
* [The Iconic: Suspected Unauthorised Access](https://www.theiconic.com.au/unauthorised-access-faq/)
* [7 News: Thousands of Aussie shoppers victim to new major hack impacting brands including Dan Murphy's, Binge and TVSN customers](https://7news.com.au/sunrise/thousands-of-aussie-shoppers-victim-to-new-major-hack-impacting-brands-including-dan-murphys-binge-and-tvsn-customers-c-13248625)
* [The Sydney Morning Herald: Thousands of Australians hacked in credential stuffing credit card scam](https://www.smh.com.au/politics/federal/thousands-of-australians-hacked-in-credential-stuffing-credit-card-scam-20240116-p5exls.html)
* [Yahoo News Australia: Major brands hit by credit card hack](https://au.news.yahoo.com/major-brands-hit-credit-card-234700109.html)
* [ABC News: The Iconic isn't the only one saving your payment details.](https://www.abc.net.au/news/2024-01-13/the-iconic-fraudulent-account-access-online-shopping-safety/103310902)

The hijacked accounts are used for fraudulent transactions, with the primary intention of revenue generation. Retail products with a high resale value such as phones, laptops, gift cards, headphones, watches and more were being fraudulently purchased. Here are some examples of the orders fraudulently submitted and collected by low-level fraudsters, based on images they have shared in Telegram chat rooms:
### Officeworks
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/3-officeworks1.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/4-officeworks2.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/5-officeworks3.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/6-officeworks4.png)

### The Iconic
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/7-theiconic1.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/8-theiconic2.webp)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/9-theiconic3.png)

### Dan Murphy's
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/10-danmurphys1.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/11-danmurphys2.jpg)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/12-danmurphys3.jpg)

### Guzman Y Gomez
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/13-gyg1.jpg)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/14-gyg2.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/15-gyg3.png)

## 2. What is credential stuffing?
Customer accounts are compromised through a "credential stuffing" attack. This attack is where a threat actors tries to authenticate to target websites using email and password combinations, or credentials, from unrelated third party data breaches. 

The success of achieving unauthorised access to a victim's account in a credential stuffing attack, primarily relies on customers using the same password for multiple services, or a similar permutation of a password that has been historically compromised. This means, that once one of their online accounts has been compromised, with a email and password combination being leaked, all of their other accounts are now susceptible to unauthorised access via a credential stuffing attack.
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/16-cred-stuffing.png)
[Image Credit](https://www.cloudflare.com/resources/images/slt3lc6tev37/7063QaY9i4PTXesgUmpoYk/cd8e741be8731bca5494bc14d03a134c/credential-stuffing.png)

Credential stuffing attacks are also referred to as "cracking" in underground markets. To perform cracking, multiple components are required including a cracking tool/script for automating the login process and scraping account information, residential proxies to rotate and bypass IP-based restrictions, and finally "combo lists" which are a combined list of usernames/emails and passwords for the tool to automatically to attempt to authenticate to target websites, created based on historical data breaches. 

## 3. Types of threat actors involved
Before proceeding, it's important to distinguish the two different types of threat actors involved in credential stuffing attacks:
1. **Vendors** are the ones performing the credential stuffing attacks to identify valid username and password combinations to gain access to victim accounts. They sell the accounts to customers for financial gain. 
2. **Customers** are the ones buying the compromised accounts from the vendors and are typically low-level fraudsters who need "boots on the ground" to reap any financial gain. They use the accounts to commit fraud, laundering stolen funds, or purchasing high value goods from retailers to collect and re-sell for profit. 

## 4. Who is selling the compromised accounts?
### Started with "Based"
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/17-based1.png)

Compromised Australian accounts appeared as early as 31 July 2023 by a user known as "Based" (`@ImRizzler`). The accounts were sold via a Discord channel, and also two websites (`base[.]sellpass[.]io` and `base[.]rip`). The primary Telegram channel for advertising was `/basedmarket` and vouches were kept on `/basedvouches`. [Archived Telegram Channel Reference](https://telemetr.io/en/channels/1921948977-basedmarket/posts)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/18-based2.jpg)

### Becanme "Crabby"
On 25 November 2023, "Based" sold his Australian account shop to "Juicy", and the new shop was rebranded as "Crabby". The telegram channel `/crabby_store` was used for advertising, and the website launched to sell the accounts was `crabby[.]atshop[.]io`. 
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/19-crabby1.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/20-crabby2.png)

At the same time, a website redirect was setup for `base[.]rip` to forward traffic to `crabby[.]atshop[.]io`, and the `base[.]sellpass[.]io` shop had included a link to the `/crabby_store` telegram channel. 
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/21-crabby3.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/22-crabby4.jpg)

On 9 January 2024, the new owners changed the domain from `crabby[.]atshop[.]io` to `crabby[.]fo`, matching the same TLD as their main site `juicy[.]fo`. However, the domain was terminated by the registrar on 31 January 2024, and thus the website was updated again on 1 February 2024 to `crabby[.]cash`.  

The `crabby[.]cash` website is still alive today selling compromised Australian accounts. As of 8 May 2024, a total of 19,185 accounts are for sale affecting the following brands.
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/23-crabby5.png)
![](content/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/24-crabby6.png)

### Owned by "Juicy"
"Juicy" is an compromised account seller website for primarily USA, CA and UK based brands. Historically the website sold AUS compromised accounts, but that is no longer the case since the launch of "Crabby".
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/25-juicy1.png)

The `juicy[.]fo` website and telegram channels are maintained by by one owner called "Juicy" `@juicyyyyyu` and three administrators called "Venchu" `@Gvenchi`, "TOXIC" `@Toxlc001` and "Bobby" `@bobby2x`. "Juicy" and "Venchu" are also operator of the website's live chat for customer support. 
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/26-juicy2.jpg)

In May 2024, "Juicy" demonstrated a change in behaviour as historic messages in the in the `/basedmarket` and `/crabby_store` telegram channels linking the "Crabby" and "Juicy" identities together started being deleted. It is assessed this is likely due to increased pressure from Australian law enforcement. The following is clear evidence, that "Juicy" directly owns and manages the "Crabby" account store:

#### High fidelity evidence for attribution
***Sale of "Email Bomber"***
The `crabby[.]cash` and `juicy[.]fo` websites both sell the same "Email Bomber", which links to the telegram user `@JuicyShopBomb_bot`. The product listing on both websites includes identical text and pricing.
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/27-juicy3.jpg)

***Indexed telegram messages***
The `juicy[.]fo` website has been indexed as the original chat title of the `/crabby_store` telegram channel, which is shown in a forwarded message in `/basedmarket` below. The indexed copy can be reviewed on [Telemetr](https://telemetr.io/en/channels/1921948977-basedmarket/posts). 
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/28-juicy4.png)
Additionally, the `juicy[.]fo` website was advertised on the `/crabby_store` telegram channel on multiple occasions, as shown in the images below. 
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/29-juicy5.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/30-juicy6.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/31-juicy7.png)

***Indexed terms of service***
An indexed Google search of the `crabbystore[.]atshop[.]io` website reveals that the original terms of service included a direct reference to `juicy[.]fo` as the owners and operators of the Crabby store.
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/32-juicy8.png)

#### Low fidelity evidence for attribution
***Use of atshop.io***
Crabby and Juicy have both utilised subdomains on the `atshop[.]io` digital e-commerce website to sell their compromised accounts. 
* Crabby stopped using `crabbystore[.]atshop[.]io` on 9 January 2024, and switched to `crabby[.]fo`.
* Juicy stopped using `juicy[.]atshop[.]io` on 20 February 2024 and switched to `juicy[.]fo`. 
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/33-juicy9.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/34-juicy10.png)

***Domain TLD and registrars***
Juicy and Crabby both have registered domains with the same TLD (`.fo`), and have used the same domain registrars. This detail is not a key indicator of attribution, but the TTPs are overlapping and should be mentioned.
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/35-juicy11.jpg)

***Use of privatebin.net***
Crabby and Juicy both used `privatebin[.]net` as an online pastebin tool to freely shared compromised accounts in giveaways to Telegram users. This detail is also not a key indicator of attribution, but as there are a variety variety of online pastebin tools available, the TTPs are overlapping and should be mentioned. 
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/36-juicy12.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/37-juicy13.png)

***Website FAQ information***
The FAQ page of Crabby and Juicy's websites include identical questions and answers, as shown in the image below.
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/38-juicy14.jpg)

***Website product images***
Both Crabby and Juicy host their website product listing images on `imgur.com`, and include the following formatting similarities:
* 600 pixels wide by 350 pixels height
* Palm trees as background
* Affected brand logo centred
* Website name centred below affected brand name
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/39-juicy15.jpg)

### Who is "Juicy"?
Whilst the `juicy[.]fo` domain was only registered on 7 August 2023, a high level of maturity and sophistication was shown indicating that the website owner has had previous experience with credential stuffing and compromised account sales. 

Multiple account selling and fraud related Telegram channels were acquired and merged in the early months of the Juicy shop launch to attract new customers. These channels were likely purchased for cryptocurrency with the original owners selling their hijacked accounts in bulk for the new Juicy shop. This included:
* "Hoodupdates" was acquired on 6 August 2023, including the `/hoodupdates` Telegram channel, which now advertises `juicy[.]fo`.
* "YSL" was acquired on 7 August 2023, including the `/juicystockupdates` Telegram channel (original channel name was changed), with 22,000 subscribers, to advertise `juicy[.]fo`. 
* "Buzz" was acquired on 7 August 2023, including `buzz[.]tf`, `bin[.]camp` and the `/NewJuicyShop` Telegram channel (original channel name was changed), which all now redirect and advertise `juicy[.]fo`.
* "Legalized" was acquired on 24 August 2023, including the `/legalizedshop` Telegram channel, which now advertises `juicy[.]fo`.
* "Kinder" was acquired on 20 September 2023, including `kinder[.]top` and the `/kinder` Telegram channel with 3,600 subscribers, which both now redirect and advertise `juicy[.]fo`. 
* "TrapTop" was acquired on 13 November 2023, including the `/trapchatv6` Telegram channel, which now advertises `juicy[.]fo`.
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/40-juicy16.jpg)

## 5. Who is buying the compromised accounts?
Low-level fraudsters with "boots on the ground" in Australia have been purchasing the compromised accounts from Crabby with the primary goal of monetary gain. However, these fraudsters often demonstrated poor operational security, oversharing information about the crimes they were committing.  

In one instance, a user called "Oly" (`@jimmyweb19`) shared how they used a compromised Officeworks account to place an order for an iPhone 15 Pro Max for $2,337.00 AUD, sharing the following screenshot.
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/42-jimmy1.jpg)

"Oly" subsequently boasted to the chat about how he had called the victim, and impersonated an Officeworks employee to ask them to provide a one-time-pass code that was sent to their mobile to authorise the transaction. He shared a video using the OTP to confirm the Officeworks order, as shown below.
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/43-jimmy2.png)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/44-jimmy3.mp4)
![](/blog/2024-05-20-crabby-credential-stuffing-australia-account-takeovers/content/45-jimmy4.png)

It is clear that customer of Crabby, like "Oly" are also driven by the excitement and challenge of engaging in illicit activities, and would take risks in pursuit of their goals for financial gain. The following was able to be derived about "Oly" from the information shared:
* A fraudulent Officeworks order for $2,337.00 was placed on 8th May 2024.
* Allegedly the order was for an iPhone 15 Pro Max, and he placed 2 other orders, for a total value of $7,200.
* Allegedly the items were to be collected at Castle Hill Officeworks in Sydney on 9th May 2024.
* Allegedly the orders will be picked up by "runners", which are mules doing the dirty work.
* Victim's card is Westpac Altitude Black World Mastercard ending in 7325.
* Victim's mobile phone ends in 155.
* "Oly" posted a video of committing the fraudulent purchase, local time on mobile device was 9:51pm, and the video was shared on the telegram chat at 10:05pm AWST, so he could be based in Perth, Western Australia. 

## 6. Recommendations
### For users:
1. Change your passwords for all of your accounts so that they are unique, and do not include permutations of existing passwords. 
2. Sign up to a password manager, such as [Dashlane](https://www.dashlane.com/), to make managing your passwords easier and ensure they are unique with high complexity. 
3. Enable multi-factor authentication, such as [Google Authenticator](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2&pli=1), for access to accounts with sensitive information, or the ability to execute financial transactions, based on your personal risk tolerance. 
4. Use a one-time email forwarding solution, such as [DuckDuckGo Email Protection](https://duckduckgo.com/email/), to keep your primary email hidden.

### For companies:
1. Implement a bot mitigation solution to block traffic from automated scripts performing credential stuffing.
2. Enforce minimum 14 character passwords with high complexity.
3. Ensure error messages for registration, login and password recovery do not include varying responses which could enable an adversary to enumerate valid accounts. 
4. Enforce multi-factor authentication for accounts that transact above a specified monetary quantity, based on risk tolerance. 
5. Restrict access to administrative web endpoints to the organisation's internal network IP range. 

### For law enforcement:
1. Catch and prosecute the low-level fraudsters in Australia who are buying the compromised accounts, to set a precedent and deter others from engaging in similar activities. 

## 7. Indicators of compromise
### Websites:
```Text
crabby[.]cash
crabby[.]fo
crabbystore.atshop[.].io
base[.]rip
base[.]sellpass[.]io
juicy[.]fo
juicy[.]atshop[.]io
buzz[.]tf
bin[.]camp
kinder[.]top
```
### Telegram Users:
```Text
@ReloadThaSix
@Reload_6
@Reload_7
@juicyyyyyu 
@Gvenchi
@pooron
@Wealth
@thunderstorm
@Toxlc001 
@bobby2x
```
### Telegram Channels:
```Text
crabby_store
crabbychat
JuicyOfficialLounge
JuicyVouchCenter
JuicyShopBomb_bot
juicdydrop_bot
NewJuicyShop
juicystockupdates 
basedmarket 
basedvouches
basevouches
trapchatv6
kinder 
hoodupdates
legalizedshop
```
### Discord Invites:
```Text
/WwEVuWVekT
/AN2XBYYdyq
/ZGK4vrtQ
/TQxYAbxUSE
```
