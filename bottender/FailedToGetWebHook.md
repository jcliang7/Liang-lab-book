# 取得WebHook失敗

# 跟者[官網教學](https://bottender.js.org/docs/zh-TW/channel-telegram-setup)從頭做 Bottender and Telegram
https://bottender.js.org/docs/zh-TW/channel-telegram-setup

## 用我之前參考鐵人賽建立的機器人來改
在 bottender.config.js 裡面加入以下設定：
```javascript=
module.exports = {
  channels: {
    telegram: {
      enabled: true,
      path: '/webhooks/telegram',
      accessToken: process.env.TELEGRAM_ACCESS_TOKEN,
    },
  },
};
```
## 安裝dotenv
https://www.npmjs.com/package/dotenv
官網說「Bottender 利用 dotenv 套件來在你開發應用程式的時候載入你的環境變數。」
我以為要自己安裝，但是看了我的node_module資料夾，發現dotenv已經有了，應該是建立bottender專案的時候，自動安裝的。

## 準備 Telegram Access Token
先去Telegram 找 [@BotFather](https://t.me/BotFather)建立一個新的Telegram 機器人。

輸入/newbot，然後根據指示填入機器人的基本資料。
我的設定：
name: Liang01
username: Liang01Bot
Use this token to access the HTTP API:
1796429284:AAEeQ7YfbpCliR3YBjUY2lr1glqP_UmWDW0
![](https://i.imgur.com/xaWS7Jg.png)



我其實不懂name 跟 username的差別。
username 本來是設定 TestBot，BotFather說已經被使用了。

然後官網說要把token貼到.env裡面，我的資料夾裡面沒有.env這個檔案，所以我自己建立一個，內容如下

```
# .env

TELEGRAM_ACCESS_TOKEN=<Your Telegram Bot Token>
```

## Webhook
官網說執行 npm run dev，我跟著做就出現error:
![](https://i.imgur.com/GoyArH6.png)

之前[鐵人賽](https://ithelp.ithome.com.tw/articles/10216040)的指令有成功run：
```
npx bottender start
```
可是沒有得到webhook，機器人也不理我。
原因出在創建專案的方式不對。我決定重新建立一個新的bottender bot了。
