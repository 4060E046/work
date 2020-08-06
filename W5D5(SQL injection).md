## SQL Injection-隱碼攻擊
***
### 發生於應用程式之資料庫層的安全漏洞
### 在輸入的字串之中夾帶SQL指令，在設計不良的程式當中忽略了檢查
### 這些夾帶進去的指令就會被資料庫伺服器誤認為是正常的SQL指令而執行 
***
### 以常見的使用者登入系統為例，假設下方程式碼檢查使用者帳號密碼
#### 依照user輸入的帳號名稱與密碼，查詢資料庫中是否有相符紀錄
```
$sql = "SELECT * FROM account WHERE username='{$_POST['user']}'
							  	AND	passward='{$_POST['pass']}'";
$result=mysqli_query($conn,$sql);
```
#### 取得查詢結果筆數
```
$total = mysqli_num_rows($result);
```
#### 若查得到紀錄，表示使用者輸入的帳號密碼正確
```
if($total > 0)
{
	echo '登入成功';
}
else
{
	echo '登入失敗';
}
```

***
***

#### 當使用者登入表單user單位輸入 tony 
#### pass欄位輸入 happy，責程式會"執行"下面SQL敘述
```diff
+ SELECT * FROM account WHERE username='tony' AND passward='happy'
```
#### 但使用者在pass欄位輸入 ' OR ''=' 程式會"執行"下面SQL敘述
* username='tony' AND passward='' 此條件為FALSE
* ''='' 此條件為True
```diff
- SELECT * FROM account WHERE username='tony' AND passward='' OR ''=''
```

***

### 另一個例子
```
https://reurl.cc/oLNeM3
```
#### 正常SQL語句
#### (TRUE) AND (TRUE) = TRUE
```diff
SELECT * FROM account 
+ TRUE
WHERE username='tony' 
+ TRUE
AND passward='happy'
```
#### 惡意填寫的SQL語句
#### passward='XXX ' = FALSE
#### ' 1 '=' 1' = TRUE
### (TRUE) AND (FALSE OR TRUE) = TRUE
```diff
SELECT * FROM account 
- FALSE
WHERE username='tony' 
+ TRUE
AND passward='XXX ' OR ' 1 '=' 1'
```
|語法	|意義|
|:-:	|:-:|
|'		|是將 name 的 input 方塊內容關閉|
|OR		|是指或是的條件|
|1=1	|恆正|

***
***

## 如何避免SQL Injection
* 最重要的就是不要相信使用者輸入的資料
* 將含有SQL指令過濾掉、或是將單引號變換成雙引號
* 將資料庫預設帳號、密碼關閉，提高資料庫存取權限

### 在PHP中，傳統處理方式是呼叫 mysqli_real_escape_string()
### 以過濾掉使用者輸入資料中的特殊字元
```
mysqli_real_escape_string(連線物件, 要過濾的字串)
```

### mysqli_real_escape_string()會過濾字串中的特殊字元
### 將其加上反斜線，再傳回來
```
原始字串		過濾後字串
   
It's cool	It\'s cool
\n		\\n
"WOW"		\"WOW\"
```
### 上例中 ' OR ''=' 過濾後會變成 
```
\' OR \'\'=\'
```
