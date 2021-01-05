# AutoApiSecret-加密版
AutoApi系列：AutoApi、AutoApiSecret、AutoApiSR、AutoApiS

# 置頂 #
* 本專案是建立在[原教程](https://blog.432100.xyz/index.php/archives/50/)可以正確調用api的**假設**上的，核心是paran/黑幕大佬的py腳本。
* 本項目只是提供一個自動、免費、無需額外設備的腳本運行方式，換句話說，**借用github的電腦/伺服器來幹活**。（因為原教程需要伺服器/超長時間運轉的設備，大部分人都不具備，本項目應運而生）
* 本專案運行依賴**github action**服務，此功能github固有而**非私人提供**的伺服器，且整個運行過程只涉及你與github。
* 請務必先閱讀理解[原教程](https://blog.432100.xyz/index.php/archives/50/)的**原理說明、設計理念**。
* **不保證一定能續期！不保證一定能續期！不保證一定能續期**！或者說，**只是增大續訂可能性**。過期前、後30天都可能續期！！！
* 若理解並接受上述說明，請接著操作；**若否，請點擊流覽器右上角 X 。**

### 專案說明 ###
* 利用github action實現**定時自動調用api**，保持E5開發活躍。
* **免費，不需要額外設備/伺服器**，部署完不用管啦。
* 加密版，隱藏應用id+機密，保護帳號安全。

### 特別說明/Thanks ###
* 原教程博主-黑幕（酷安id-Paran）：https://blog.432100.xyz/index.php/archives/50/
* 普通版地址：https://github.com/wangziyingwen/AutoApi
* 加密版地址（推薦）：https://github.com/wangziyingwen/AutoApiSecret
* 模仿人為應用開發版（包含升級步驟）：https://github.com/wangziyingwen/AutoApiSR
* 超級版地址： https://github.com/wangziyingwen/AutoApiS
* **常見錯誤及解決辦法/更新日誌**：https://github.com/wangziyingwen/Autoapi-test
* 網頁獲取refresh_token小工具（不建議使用）：https://github.com/wangziyingwen/GetAutoApiToken
* 視頻教程：（我操作很慢，自行倍速/快進）
   * 線上/下載地址：https://kino-onemanager.herokuapp.com/Video/AutoApi%E6%95%99%E7%A8%8B.mp4?preview
   * B站：https://www.bilibili.com/video/av95688306/

           

### 區別 ###
   [普通版（棄用）](https://github.com/wangziyingwen/AutoApi)：金鑰暴露，不在乎的話可以使用
   
   [加密版（推薦）](https://github.com/wangziyingwen/AutoApiSecret)：應用id機密加密隱藏，提高安全性

   [模仿人為應用開發版（半棄用）](https://github.com/wangziyingwen/AutoApiSR)：顧名思義，加密版的升級版。由於超級版相容模擬版的功能，此版本處於一種尷尬位置。（當然也可以正常使用）
   
   [超級版（不建議）](https://github.com/wangziyingwen/AutoApiS)：進一步升級版，增加自訂參數、模式。按目前情況，微軟續訂要求很低，暫時不需要使用此專案。
   
   **以上推薦/不建議等只是個人意見，請自行選擇版本，可同時使用**。

--------------------------------------------------------------

## 步驟 ##  

   >:blush: :blush: :blush: :blush: :blush: :blush: 
   
   >請注意！請注意！請注意！
   
   >*** **有錯誤/問題請看**:    [常見錯誤及解決辦法/更新日誌](https://github.com/wangziyingwen/Autoapi-test)
   
   >*** 原教程/博客好像也壞了，看[視頻教程](https://www.bilibili.com/video/av95688306/)吧，懶得補充，ORZ. （或者去網上搜一下，有一堆轉載，關鍵字：github action e5 續期）
   
   >*** 註冊應用時用到的[azure管理頁面](https://portal.azure.com/)，或者直接到[儀錶板](https://aad.portal.azure.com/)，找到註冊應用選項
   
   >***【重定向URI】填寫的內容：http://localhost:53682/

   >*** rclone下載，請自行百度穀歌，官網好像是[rclone.org](https://rclone.org)
   
   >:anguished: :anguished: :anguished: :anguished: :anguished: :anguished:  
  
* 第一步，先大致流覽[原教程](https://blog.432100.xyz/index.php/archives/50/)，瞭解如何獲取應用id、機密、refresh_token 3樣東西，以方便接下來的操作。

* 第二步，登陸/新建github帳號，回到本專案頁面，點擊右上角fork本項目的代碼到你自己的帳號，然後你帳號下會出現一個一模一樣的項目，接下來的操作均在你的這個項目下進行。（看不到圖片/圖裂請科學上網）

  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/fork.png)
  
* 根據[原教程](https://blog.432100.xyz/index.php/archives/50/)獲取應用id、機密、refresh_token（自己複製保存，注意區分id機密，別弄混了）
   
  然後線上編輯你專案裡的1.txt，將整個refresh_token覆蓋粘貼進去（裡面是我的資料，先刪掉或者覆蓋掉）。（千萬不要改1.py）
  
    > refresh_token位置如圖下。複製refresh_token緊接著的雙引號裡的內容（紅分隔號框起來的），不要把雙引號複製進去。複製進1.txt後，留意結尾不要留空格或者空行
     
    ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/token地方.png)
  
* 第三步，依次點擊上欄Setting > Secrets > Add a new secret，新建兩個secret如圖：CONFIG_ID、CONFIG_KEY。

  內容分別如下: ( 把你的應用id改成你的應用id , 你的應用機密改成你的機密，單引號不要動 )
  
  CONFIG_ID
  ```shell
  id=r'你的應用id'
  ```
  CONFIG_KEY
  ```shell
  secret=r'你的應用機密'
  ```
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/机密.png)
  
  最終格式應該是類似這樣的：
  
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/格式.png)
  
* 第四步，進入你的個人設置頁面(右上角頭像 Settings，不是倉庫裡的 Settings)，選擇 Developer settings > Personal access tokens > Generate new token,

  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/Settings.png)
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/token.png)

  設置名字為GITHUB_TOKEN , 然後勾選 repo , admin:repo_hook , workflow 等選項，最後點擊Generate token即可。
  
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/repo.png)
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/adminrepo.png)
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/workflow.png)
  
* 第五步，點擊右上角星星/star立馬調用一次，再點擊上面的Action就能看到每次的運行日誌，看看運行狀況

（必需點進去Test Api看下，api有沒有調用到位，有沒有出錯。外面的Auto Api打勾只能說明運行是正常的，我們還需要確認10個api調用成功了，就像圖裡的一樣。如果少了幾個api，要麼是註冊應用的時候賦予api許可權沒弄好；要麼是沒登錄啟動onedrive，登錄啟動一下）

  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/日志.png)

* 第六步，沒出錯的話，就搞定啦！！再看看下面的定時次數要不要修改，不打算改就忽略。

  **然後第二天回來確認下是否自動運行了（ation裡是否多出來幾個）**,是的話就不用管了，完結。
  
  我設定的每6小時自動運行一次，每次調用3輪（點擊右上角星星/star也可以立馬調用一次），你們自行斟酌修改（我也不知道保持活躍要調用多少次、多久）：

  * 定時自動啟動修改地方：（在.github/workflow/AutoApiSecret.yml檔裡，自行百度cron定時任務格式，最短每5分鐘一次）
   
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/定时.png)
   
  * 每次輪數修改地方：（在1.py最後面）
   
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/次数.png)
  
------------------------------------------------------------
### 題外話 ###
> Api調用
  你們可以自己去graph流覽器看一下，學著自己修改要調用什麼api(最重要的是調用outlook、onedrive)
  https://developer.microsoft.com/zh-CN/graph/graph-explorer/preview

### GithubAction介紹 ###
提供的虛擬環境：

· 2-core CPU
· 7 GB RAM 記憶體
· 14 GB SSD 硬碟空間

使用限制：
* 每個倉庫只能同時支援20個 workflow 並行。
* 每小時可以調用1000次 GitHub API 。
* 每個 job 最多可以執行6個小時。
* 免費版的用戶最大支持20個 job 併發執行，macOS 最大只支持5個。
* 私有倉庫每月累計使用時間為2000分鐘，超過後$ 0.008/分鐘，公共倉庫則無限制。

（我們這裡用的公共倉庫，按理，你們可以設定無限迴圈調用，然後6小時啟動一次，保證24小時全天候調用）

### 最後 ###
  教程很直白了，應該都會弄吧！
  
  代碼小白，多包涵！有問題/修改建議可以點擊上方issues發佈一下，或者PY給我:
  wz.lxh@outlook.com
  
  Q群：[657581700](https://jq.qq.com/?_wv=1027&k=5FQJbWmV)  （專案相關討論）
  
  最後的最後，再次感謝黑幕/paran大佬
  
  ————wangziyingwen/酷安id-卷腿毛菌

