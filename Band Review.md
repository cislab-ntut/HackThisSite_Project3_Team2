Uncle Arnold’s Local Band Review & United Banks Of America
===
## 1051434 蔡適謙


## Uncle Arnold’s Local Band Review

From: HeavyMetalRyan

Message: Hey man, I need a big favour from you. Remember that website I showed you once before? Uncle Arnold's Band Review Page? Well, a long time ago I made a $500 bet with a friend that my band would be at the top of the list by the end of the year. Well, as you already know, two of my band members have died in a horrendous car accident... but this ass hole still insists that the bet is on!
I know you're good with computers and stuff, so I was wondering, is there any way for you to hack this website and make my band on the top of the list? My band is Raging Inferno. Thanks a lot, man!

## 解題流程

### step1

- 觀察html 找到可疑處
![](https://imgur.com/XZVuzB6.png)

### step2

- 透過PHPSESSION攻擊 去對發出的request做更改
![](https://imgur.com/HyjpcmP.png)
把id和數值改成想要的之後

### 結果
![](https://imgur.com/3fSDkqW.png)

## United Banks Of America

From: DarkOneWithANeed

Message: Hey man, you gotta help me out, Gary Hunter, one of the richest men in America, has just deposited $10,000,000 into his bank account at the United Banks Of America and plans to donate that money to a campaign to hunt down and lock up all hackers. Now I've tried hacking their site but I'm just not good enough. That's why I need your help, Here's a list of your objectives:
1. Find the account of Gary Hunter (I don't know his account name).
2. Move the $10,000,000 into the account dropCash.
3. Clear The Logs, They're held in the folder 'logFiles'.
I really hope you can do this, because if you can't we're all screwed

### step1
- 註冊帳號並使用SQLinjection來獲取所有帳號和敘述資料
![](https://imgur.com/7fOI5uE.png)

### step2
- 登入先前註冊的帳號後可以看到有轉錢的按鈕,其中可以看到並不是什麼安全的方法，所需的資料全在query裡
![](https://imgur.com/bCEn7yJ)
![](https://imgur.com/wcpXvdp)

### step2
