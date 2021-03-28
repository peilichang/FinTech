
# AWS IAM & S3

## 課堂筆記
### Identity and Access Management(IAM)
用於服務跟服務溝通時，可建立和管理AWS使用者、群組，將各種服務串起來時，透過IAM設定使用者能取用的data。

IAM 分為兩種Policy，底下皆有**Statement**能針對以下幾個指定做設定：

      1. Effect - 對動作允許或不允許
      2. Action - 允許後對資源的操作行為（新增、修改、刪除...等）
      3. Resource - AWS資源
      
- **Identity-based Policy** 以**使用者**為角度出發，分為

        1. User - root account底下的多個users
        2. Group - 類似公司部門的群體，一個Group有多個Users
        3. Role - 非人，為服務跟服務之間的橋樑，賦予權限的動作

        以使用者為基準，設定他們使用資源的權限

- **Resource-based Policy** 以**資源**為角度出發

        1. Statement中多了Principle - 授權給誰
        2. Ex . S3中的資源只能做刪除、修改

        以資源為基準，設定這份資源只能被所有使用者做什麼操作

---

### S3

為Object-based的儲存方式，將object儲存於bucket（類似folder概念）

    1. 單一帳號上限100 Buckets
    2. 1 Bucket 中容量無上限，但單一檔案大小限制為 0 bytes ~ 5 TB
    3. 每個Bucket會有全球Unique的DNS名稱

- **Object特性**有以下幾種：

        1. Key - Object Name（檔案按字母排序）
        2. Value - 資料本身（一堆 Byte 的組合）
        3. Version ID - 版本控制使用，上傳兩個相同名稱檔案後，輸入ID則能選擇提取版本
        4. Metadata -  額外用來記錄Object相關資訊的資料、在找尋資料時能更快找到資料的基準

- **S3 的訪問控制的狀態**（遵循最低權限原則）

        1. Default deny - 所有Object的默認狀態為私有
        2. Explicit deny -  Statement 中的 Effect 顯示為 "Deny"
        3. Explicit Allow - Statement 中的 Effect 顯示為 "Allow"

- **確認是否有訪問權限的三大關卡** 

        1. S3 Access Control List(ACL)
        2. S3 Bucket Policy - 外部訪問
        3. AWS IAM - 內部訪問

        通過 Bucket 權限後再去確認 Object 訪問權限



## 課堂資源
> * [課堂PPT](http://isee.scu.edu.tw/mod/url/view.php?id=706975)
> * [課堂錄影](http://isee.scu.edu.tw/mod/url/view.php?id=708126)
