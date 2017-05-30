# 啟動 Selenium Server

**執行 Selenium Server**

至 <http://www.seleniumhq.org/download/> 下載 selenium-server-standalone-3.4.0.jar 檔

```
cd Downloads
java -jar selenium-server-standalone-3.4.0.jar
```

<http://127.0.0.1:4444/wd/hub>

**或**

```
// 安裝 webdriver-manager 模組到全域環境
npm install webdriver-manager -g

// 更新 driver
webdriver-manager update

// 啟動 selenium server
webdriver-manager start

// 查看 driver 狀態
webdriver-manager status

// 清除 driver
webdriver-manager clean
```