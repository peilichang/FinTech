# Amazon API Gateway and AWS Lambda


## 課堂資源
> * [專案PPT](http://isee.scu.edu.tw/mod/url/view.php?id=708556)
> * [課堂PPT](https://drive.google.com/file/d/1-AsnJmAldi_-gPnxdQcyBifScMmR_IBk/view)
> * [課堂錄影](http://isee.scu.edu.tw/mod/url/view.php?id=709691)

        
## 課堂筆記
> * [作業Notion](https://www.notion.so/HW4-Build-a-Telegram-Chatbot-using-Amazon-API-Gateway-and-AWS-Lambda-a245dcde8d14473a86d63c7dc00549d1)
### Chatbot

---

用戶對聊天機器人的接受度高，可用引導的方式達到目的

1. 種類分為
    - **一般**（沒有導入自然語言系統）

    - **進階**（有自然語言系統在設計框架下）

2. 功能
    - 問答系統（資訊取得）
    - 任務導向型對話系統（表單、問卷）
    - 閒聊系統
    - 主動推薦系統（每天的固定推播）

### API（Application Programming Interface）

---

API是指各種軟體組件之間一套明確定義的溝通方法

個人或企業為了達到某種需求而去設計一段功能或程式，最後的output是一串連結

![image](https://github.com/peilichang/FinTech/blob/master/Week6/API.png)

### HTTP（HyperText Transfer Protocol）

---

HTTP 客戶端（用戶）通過網址向 HTTP 服務端（Web 伺服器）傳送所有請求，根據接收到的請求後，向客戶端傳送響應資訊。

- **HTTP的溝通方法**

![image](https://github.com/peilichang/FinTech/blob/master/Week6/HTTP.png)

### API Gateway

---

是一種API服務，但不包括後面的運作邏輯

- 全受託管的服務（服務背後的底層系統和自動擴展的功能皆由AWS處理）
- 可建立、發佈、維護、監控和保護任何規模的 API
- API類型有Restful API（HTTP API、REST
API）及 WebSocket API

### AWS Lambda

---

處理邏輯的執行者，是一個Serverless運算的核心服務

- 無伺服器的運算服務
- 用於資料處理、即時串流處理、機器學
習、後端
- 為事件驅動的程式，需要有Event Source來觸發AWS Lambda中的Function
1. **Event Source 資料來源**
        如何達到Trigger?

        - 數據的改變
        Ex. 定義的欄位有變動觸發Function進行計算

        - 資源狀態的改變
        Ex. 上傳的mp4檔要轉成mp3

        - 終端請求
        Ex. API呼叫
        
2. **Function**

        - 寫的內容就是將Event Source的內容達到轉換目的的程式碼
        - 可支援的程式碼：Node.js / Python / Java / C# / Go / Ruby / Custom Runtime（自己部署環境）
        
3. **Destination 目的地**

       最後的Action為Optional，可送回User端或是在雲端上進行

    ![image](https://github.com/peilichang/FinTech/blob/master/Week6/Lambda.png)

---

### Less is more

### What’s server-less？

1. 無需管理基礎設施任務
2. 自動擴展性（當流量達到限制時會自動擴展）
3. 按價值付費的計算模型
4. 安全且高可用性

**演進過程**

Machine → Virtual Servers → Cloud & Containers → Serverless 

### Function as a Service(FaaS)

一般來說 A用戶呼叫function a時會得到一個結果，在FaaS上，A用戶呼叫時會建立一個instance專門服務A用戶，B用戶呼叫時也會新建一個，所以提供給兩個用戶的使用環境是不一樣的，使用的參數也不一樣，使用完則關機。
