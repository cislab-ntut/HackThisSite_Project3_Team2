Peace Poetry: HACKED
===
### Realistic missions 第3題
#### 第2組 1051518 李政憲

## 題目

From: PeacePoetry

Message: I run this website where people can read and submit peace-related poetry. I am doing this out of good will towards others, and I don't see why I would be making enemies out of this, but some real ass hole hacked my website posting a bunch of ignorant aggressive propaganda on the front page. And I made that website a while ago, and I no longer have access to it. Do you think you can hack in and change it back? Please? Oh, and bonus points if you message me the name of the bastard who did this!
My website can be found [here](https://www.hackthissite.org/missions/realistic/3/).

## 題目-中文簡述

我做了一個和平詩歌的網站，被駭客害掉了，請幫我修復。

## 解題流程
### Step 1
- 點進題目中[here](https://www.hackthissite.org/missions/realistic/3/)，進入此頁面。
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/1.jpg)

### Step 2
- 內文中並沒有什麼可用資訊，查看`網頁原始碼(F12)`。
- 註解中有可用資訊，駭客複製舊的index.html到oldindex.html中，並重新製作index.html。
```Html
<!--Note to the webmasterThis website has been hacked, but not totally destroyed. The old website is still up. I simply copied the old index.html file to oldindex.html and remade this one. Sorry about the inconvenience.-->
```
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/2.jpg)

### Step 3
- 更改URL進入oldindex.html。
- `https://www.hackthissite.org/missions/realistic/3/oldindex.html`
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/3.jpg)

### Step 4
- 下方有兩個超連結，先嘗試點擊左方超連結[Read The Poetry](https://www.hackthissite.org/missions/realistic/3/readpoems.php)。
- 有三首詩歌，每首詩歌的URL為`https://www.hackthissite.org/missions/realistic/3/readpoem.php?name=詩歌名`。
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/4.jpg)
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/5.jpg)
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/6.jpg)

### Step 5
- 點擊右方超連結[Submit Poetry](https://www.hackthissite.org/missions/realistic/3/submitpoems.php)。
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/18.jpg)

### Step 6
- 亂嘗試然後`add poem`，皆會導向此[網站](https://www.hackthissite.org/missions/realistic/3/submitpoems2.php)。
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/7.jpg)
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/8.jpg)
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/9.jpg)
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/10.jpg)
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/11.jpg)
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/12.jpg)
- ↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/13.jpg)

### Step 7
- Google找到管理員發的有關這題的[文章](https://www.hackthissite.org/forums/viewtopic.php?f=52&t=3107&sid=a2377cc2ec14c104db82811e299a9aee)
>Required:
>>- Logical thinking (of course)
>>- Moderate HTML knowledge
>>- Basic PHP knowledge
>>- `Directory Traversal`
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/14.jpg)

### Step 8
- 思考:駭客從`https://www.hackthissite.org/missions/realistic/3/submitpoems.php`攻擊`https://www.hackthissite.org/missions/realistic/3/oldindex.html`。
- 回到[Submit Poetry](https://www.hackthissite.org/missions/realistic/3/submitpoems.php)。
- `Name of poem`寫上`../oldindex.html`。
- `Poem`全選複製貼上`https://www.hackthissite.org/missions/realistic/3/oldindex.html``內文`。
- 點擊`add poem`，成功。
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/15.jpg)
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/16.jpg)

### 小嘗試
- 搜尋Step 1網站裡的`H4XX0R3D`、`h4x0r3d`，不過沒什麼幫助。
- Strp 8中，在`Poem`處不打任何東西，會導向此[網站](https://www.hackthissite.org/missions/realistic/3/submitpoems2.php)，提醒你`Poem`要打什麼，非常貼心。
![](https://github.com/cislab-yzu/Project2-3_Hackthissite/blob/master/1051518_Pictures/17.jpg)

### 網路解法
- 差別只在Step 8，他們是複製`網頁原始碼`到`Poem`。
