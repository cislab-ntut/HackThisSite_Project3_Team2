Damn Telemarketers!
===
### Realistic missions 第5題
#### 第2組 1051524 莊子毅

## 問題

Message: Yo! This is Spiffomatic64 from Hackthissite.org! I'm a bit of a hacker myself as you can see, but I recently came upon a problem I couldn't resolve.....Lately I've been getting calls day and night from the telemarketing place. I've gone to their [website](https://www.hackthissite.org/missions/realistic/5/) and hacked it once deleting all of their phone numbers so they wouldn't call me anymore. That was a temporary fix but they put their database back up, this time with an encrypted password. When I hacked them I noticed everything they used was 10 years out of date and the new password seems to be a 'message digest'. I have done some research and I think it could be something like a so-called hash value. I think you could somehow reverse engineer it or brute force it. I also think it would be a good idea to look around the server for anything that may help you.

## 問題-中文簡述

一位本身就是駭客的男子，受到了電話市場調查的騷擾，於是他自己駭進去市場調查公司的官網把所有電話號碼都刪除讓他們無法打電話。但市場調查公司把備份的電話資料重新上傳，而且這次還需要**密碼**才能瀏覽。已知這個**密碼**為10年以前的加密方法所產出來的hash值。

## 解題流程
### Step 1
- 先點進題目中所提到的[website](https://www.hackthissite.org/missions/realistic/5/)，可以看到首頁。

![](https://i.imgur.com/jz0oB9l.png)

### Step 2
- 因為題目說對方將電話號碼放在加密的資料庫，於是點左邊的<b>Database</b>，可以看到會要求輸入密碼。

![](https://i.imgur.com/TiM1MZY.png)

- 先隨便測試密碼，當然結果是錯的。

![](https://i.imgur.com/rCsq3g8.png)


### Step 3
- 回到輸入密碼的頁面，並查看他的原始碼。

![](https://i.imgur.com/NM0SsYL.png)

- 原始碼如下：
```Html
<html>

<head>

<title>Log in</title>
</head>

<body bgcolor="#000000" text="#FFFFFF">
<center><br /><br />
Enter Password:
<form action="secret/admin.php">
<p><input type="password" name="password" size="20"><input type="submit" value="submit" name="submit"></p>
</form>
</center>
</body>

</html>
```

- 在輸入密碼的地方，可以看到它導向了<b>"secret/admin.php"</b>

- 去查看<b>secret</b>這個[路徑](https://www.hackthissite.org/missions/realistic/5/secret/)，裡面有兩個php。

![](https://i.imgur.com/1w7D43B.png)

### Step 4
- <b>admin.php</b>為密碼輸入錯誤的頁面。

![](https://i.imgur.com/rCsq3g8.png)

- <b>admin.bak.php</b>則是跳出這行資訊。

![](https://i.imgur.com/zeUVkEk.png)

- `20edb691f20c0e501b71dc924e67b822`，應該就是hash過後的密碼。

### Step 5
- 有了hash值，我們必須知道是用哪一個hach function所產生的。
- 回頭看題目，題目說是一種<b>message digest</b>。
- google有關<b>message digest</b>的資料，得知：
        
    - MD5訊息摘要演算法(MD5 Message-Digest Algorithm)
        - 美國密碼學家Ronald Linn Rivest設計，於1992年公開
        - 一種被廣泛使用的密碼雜湊函式
        - 輸入不定長度資訊，輸出固定長度128-bits的演算法
        - 一般128位元的MD5雜湊被表示為32位元十六進位數字
    - MD還有前幾代，如MD4。
    - 無法從密文逆推回明文，只能靠蒐集到的<b>曾被加密過的明文與其密文</b>來比對。

### Step 6
- 網路上有許多MD5的解密網站，但是用`20edb691f20c0e501b71dc924e67b822`去解密仍然找不到對應的明文。
    - 有可能是使用了其他代的<b>message digest</b>(例如MD4)。
- 於是試著改用MD4解密。[解密網站](http://www.ttmd5.com/hash.php?type=6)。
![](https://i.imgur.com/RNqFd6A.png)

### Step 7
- 把結果<b>53767</b>輸入資料庫的密碼。

![](https://i.imgur.com/y6DhFIG.png)

### 成功

![](https://i.imgur.com/RdFeImt.png)

        


