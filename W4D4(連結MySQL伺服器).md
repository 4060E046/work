## 連結MySQL伺服器

### 連線伺服器--mysqli_connect()
```
mysqli_connect(server , username, password, dbname) 

server		伺服器位址
username	帳號名稱
password	密碼
dbname		要用的資料庫(可省略)
```

### 設定連線所使用的字原集與排序規則
```
$conn = @mysqli_connect(server , username, password, dbname)
...
mysqli_set_charset($conn, "utf8")
```

### 選擇資料庫
```
$conn = @mysqli_connect(server , username, password, dbname)
...
mysqli_set_db($conn,"dbname")
```
