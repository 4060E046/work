## $_ SERVER ($_ 與 SERVER之間沒空白!!!)
```
https://ithelp.ithome.com.tw/articles/10157282
```
***

### $_ SERVER['HTTP_HOST']：當前請求的Host頭中的內容(與取得Server的Port)
### $_ SERVER['SERVER_NAME']：當前運行網頁檔案所在的主機名稱
### $_ SERVER['REQUEST_URI']：訪問此頁面需要的URL
### $_ SERVER['PHP_SELF']：當前正在執行的網頁檔案名稱
### $_ SERVER['QUERY_STRING']：查詢的變數值

#### 假設今天的實作的網址是：http://jhsiao.dscloud.me:8080/server2.php?id=1798
#### server2.php
```
<?php
    echo "HTTP_HOST：".$_SERVER['HTTP_HOST']."<hr />";
    echo "SERVER_NAME：".$_SERVER['SERVER_NAME']."<hr />";
    echo "REQUEST_URI：".$_SERVER['REQUEST_URI']."<hr />";
    echo "PHP_SELF：".$_SERVER['PHP_SELF']."<hr />";
    echo "QUERY_STRING：".$_SERVER['QUERY_STRING']."<hr />";
?>
```
#### 輸出
```
HTTP_HOST： jhsiao.dscloud.me:8080
SERVER_NAME： jhsiao.dscloud.me
REQUEST_URI： /server2.php?id=1798
PHP_SELF： /server2.php
QUERY_STRING： id=1798
```
