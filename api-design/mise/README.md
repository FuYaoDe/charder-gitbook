# 補充

### 不要把 API 設計成 DB 一對一的 CRUD

REST API 所呈現的資源，是從應用面 client 角度來思考，不需要和後端的資源儲存形式（例如資料庫schema）維持一對一的關係。

### 原子 (Atomic)

* 一個完整的動作不應由二個或二個以上API組成，每一個動作都必需是 Atomic，一個完整執行後的 API 呼叫，不能讓伺服器端資料停留在不一致的狀態。

<!-- 例如 User A 轉帳 100 給 User B 付錢買火車票。 -->
<!-- 但不代表，要把兩個 request api get 結合在一起，我們有 cache 機制。 -->
<!-- 重點在於若兩個 request，其中一個失敗了，會不會導致資料狀態不全。 -->
<!-- 如何測試 atomic api -> 應該是由商業邏輯來定義，所以在談 user requirement 中，會需要不斷的問客戶問題！ex: 轉帳轉到一半斷線的話怎麼辦？ -->

* [Amigo 陳兆祥 - RESTful API Design](https://www.slideshare.net/AmigoChan/restful-api-design): p30-53

### 無狀態 (stateless)

* Client 端應該要是無狀態的
* Server 端是允許有狀態的

<!-- RESTful 禁止使用 Session -->

### 處理重複的 request

server 要懂如何處理重複的 post request，在用 POST 建立新物件時，client 端要把 timestamp 也放進 API request 中，這樣 server 端就可以辨別是不是收到重複的 post request。

<!--
post timestamp 也是要存進 redis 或資料庫中囉？ Redis 就行了，設個 5 分鐘即可。也不用開保護，通常真的遺失也沒關係。
-->

### 為什麼 API 設計的基本知識對你很重要?

**PM**

<!--
* 了解整個 API 的設計運作過程，降低與 RD 的觀念上的差距。
* 為什麼 API 不能草率設計？
* 為什麼要版本控制？
* 為什麼 RD 堅持要我申請 HTTPS？
* 瞭解安全性的重要性
 -->

**前端工程師**

<!--
* API 是 application process interface，代表是前端跟後端的溝通。
* 需求是由前端開出，當瞭解了後端實作需要的東西時，雙方討論才有基礎共識。
 -->

**後端工程師**

<!--
* 現在主流的設計方法
* 如何突破系統的瓶頸
* 注意實作要避免的細節
* 學習怎麼跟 PM 解釋，PM 覺得不重要的東西其實很重要。
* 安全性
 -->
