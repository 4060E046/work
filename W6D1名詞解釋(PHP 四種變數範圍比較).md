## PHP 四種變數範圍比較

### 區域變數
* 在 function 中宣告
* 只能在宣告的 function 中使用 (local scope)
* 不同的 function 中可宣告相同名稱的區域變數
* 在宣告變數 function 結束時，區域變數也就消滅了
* 宣告時不需使用任何關鍵字 (keyword)
#### 下例不會輸入任何內容，因為 $a 在function 中未指定值
```
$a = 5; // 全域

function myTest()
{
  echo $a; // 區域
}

myTest();
```

***

### 全域變數
* 在 function 外宣告
* 除了 function 中的 script不能存取外，整個網頁中的 script 都可以存取該變數( global scope )
* 若要在 function 中使用全域變數，需使用關鍵字 global，見下例
* 在網頁關閉時，全域變數消滅
```
$a = 5;
$b = 10;

function myTest()
{
  global $a, $b;//注意這行
  $b = $a + $b;
}

myTest();
echo $b;
```
#### 上例輸出
```diff
+ 15
```
#### global 變數一旦宣告之後，PHP 會將其放置在 $GLOBALS[index] 這個 array 中
#### 其中 index 就是變數的名稱
#### 可以從 function 內存取這個 array
#### 也可以直接指定值給 array 中的某個元素來改變其值
將上例改寫如下：
```
$a = 5;
$b = 10;

function myTest()
{
  $GLOBALS['b'] = $GLOBALS['a'] + $GLOBALS['b'];
}

myTest();
echo $b;
```

***

### 靜態變數
#### 區域變數在函式結束時就會消滅
#### 不過有時候，當希望某區域變數不因函式結束而消滅
#### 可以在第一次宣告該區域變數前
#### 加上關鍵字-- static
```
static $rememberMe;
```
#### 如此一來，每次呼叫該函式時，此變數都會包含上一次呼叫函式時所得到的值
#### 要注意的是：靜態變數仍是一種區域變數

***

### 參數
#### 參數指的是一種呼叫函式時傳入的區域變數
#### 其會在函式宣告時的參數列 (parameter list) 中被宣告
```
function myTest($para1,$para2,...)//在小括號中宣告
{
  // 函式程式碼
}
```
