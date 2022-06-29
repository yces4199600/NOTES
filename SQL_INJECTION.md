# SQL INJECTION
## <font color="#f00">1.In-band SQL Injection:
在輸入欄位內帶入SQL語法</font>
### A.Error-based:
藉由錯誤訊息取得想要的資訊，可以獲取資料庫版本、Table_name、Column_name、數值型態。
操作指令：<font color="#f00">'</font>
![](https://i.imgur.com/wyPDzMf.png)

### B. Union-based:
藉由Union語法進行聯合查詢，將多筆資料並到單次查詢中，回傳時須注意資料格式，若格式不正確會造成失敗。
操作指令：<font color="#f00">' union all select system_user(),user() #</font>
![](https://i.imgur.com/HvXy2gw.png)
## <font color="#f00">2.Blind SQL Injection:
對於並非直接回傳資料庫的資料或是沒有回傳值時的攻擊手段</font>
### A.Content-based:
透過前端內容的變化觀察攻擊是否成功，例如可利用現成的表格回傳想取得的資料。
操作指令：<font color="#f00">' ; DROP table USERS ;——</font>
![](https://i.imgur.com/to1TvNk.png)

### B. Time-based:
藉由sleep()的語法觀察伺服器回應的時間，以此判斷攻擊是否成功。
操作指令：<font color="#f00">1' and sleep(5)#</font>
![](https://i.imgur.com/DXFSGdQ.png)

## <font color="#f00">3.Out-of-band SQL Injection:
當上面兩種方式不能使用時的最後手段，利用其他渠道帶出資料</font>
### A.DNS:
最常見為利用DNS協議獲取資料，但DNS接收的數值有限制，需搭配HEX函數將回傳值轉為16進制。
DNS範例: https://www.itread01.com/articles/1499157493.html


## 參考資料:
飛飛SQL INJECTION教學(portswigger.net線上 LAB):
https://ithelp.ithome.com.tw/articles/10240102
SQL Injection種類(範例圖片):
https://tech-blog.cymetrics.io/posts/nick/sqli/
SQL Injection概述:
https://www.acunetix.com/websitesecurity/sql-injection2/
