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

### 執行查詢資料的SQL敘述
```
mysqli_query(連線物件, SQL敘述)
---------------------------------------
例如執行 "SELECT * FROM books" 這個SQL敘述：

$result = mysqli_query("SELECT * FROM books")

若成功查詢到資料，將回傳查詢結果物件並將其儲存在$result變數
便可透過$result變數來讀取查詢結果
```

### 使用mysqli_fetch_array()讀取查詢結果
```
mysqli_fetch_array(result)

result：查詢結果物件
-------------------
第一次執行讀取第一筆
第二次執行讀取第二筆
以此類推
讀完最後一筆後,再執行mysqli_fetch_array()便會回傳FALSE
mysqli_fetch_array()會以陣列形式傳回讀取到紀錄
-------------------
```
