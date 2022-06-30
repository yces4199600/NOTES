# SQLMAP
## <font color="yellow">Options</font>
### 1.`-h, --help` 查看幫助
### 2. `-hh` 查看全部的幫助
### 3.`--version` 查看版本
### 4.`-v` 顯示信息的級別，一共有六級
```
0：只顯示python 錯誤和一些嚴重信息；
1：顯示基本信息（默認）；
2：顯示debug信息；
3：顯示注入過程的payload；
4：顯示http請求包；
5：顯示http響應頭；
```
## <font color="yellow">Target</font>
### 1.`-d` 直接連接目標後端數據庫，而不是使用sql注入漏洞，直接通過目標的偵聽端口連接，需要有目標數據庫的賬號名和密碼。
### 2.`-u` 指定一個url連接，url中必須有`？xx=xx` 才行
## <font color="yellow">Request</font>
### 1.  `--method=METHOD` 指定是get方法還是post方法。
例： `--method=GET` `--method=POST`
### 2.`--data=DATA` 指明參數是哪些。
例：`-u "www.abc.com/index.php?id=1" --data="name=1&pass=2"`
### 3. `--param-del=PARA.` 指明使用的變量分割符。
例： `-u "www.abc.com/index.php?id=1" --data="name=1;pass=2" --param-del=";"`
### 4.`--cookie=COOKIE` 指定測試時使用的cookie，通常在一些需要登錄的站點會使用。
例： `-u "www.abc.com/index.php?id=1" --cookie="a=1;b=2"`
## <font color="yellow">Optimization</font>
### 1.  `-o` 開啓下面三項（`--predict-output`，`--keep-alive`， `--null-connection`）
```
1.  `--predict-output` 預設的輸出，可以理解爲猜一個表存在不存在，根據服務器返回值來進行判斷，有點類似暴力破解，但和暴力破解又不同，這個是一個範圍性的暴力破解，一次一次的縮小範圍。
2.  `--keep-alive` 使用http（s）長鏈接，性能更好，避免重複建立鏈接的開銷，但佔用服務器資源，而且與`--proxy`不兼容。
3.  `--null-connection` 只看頁面返回的大小值，而不看具體內容，通常用於盲注或者布爾的判斷，只看對錯，不看內容。
```
### 2.`--threads=THREADS` 開啓多線程，默認爲1，最大10。和 `--predict-output` 不兼容。
## <font color="yellow">Injection</font>
### 1.`--os=OS` 指定目標操作系統。例： `--os="Linux/Windows"`
### 2.`--tamper=TAMPER` 使用sqlmap自帶的tamper，或者自己寫的tamper，來混淆payload，通常用來繞過waf和ips。
## <font color="yellow">Detection</font>
### 1. `--level=LEVEL` 設置測試的等級（1-5，默認爲1）
```
lv2：cookie; 
lv3：user-agent，refere; 
lv5：host` 在sqlmap/xml/payloads文件內可以看見各個level發送的payload;
```
### 2.`--risk=RISK` 風險（1-4，默認1）升高風險等級會增加數據被篡改的風險。
```
risk 2：基於事件的測試;
risk 3：or語句的測試;
risk 4：update的測試;
```
## <font color="yellow">Enumeration</font>
### 1.`-a, --all` 查找全部，很暴力。直接用`-a`
### 2.`-b, --banner` 查找**數據庫管理系統**的標識。直接用`-b`
### 3.`--dbs` 目標服務器中有什麼數據庫，常用，直接用`--dbs`
### 4.`--tables` 目標數據庫有什麼表，常用，直接用`--tables`
### 5.`--columns` 目標表中有什麼列，常用，直接用`--colums`
## <font color="yellow">參考資料</font>
https://www.twblogs.net/a/5e9b44f26052e1406acf28f5