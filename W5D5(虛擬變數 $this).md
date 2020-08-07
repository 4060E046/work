## 虛擬變數 $this

### $this是個特殊的參照函數(reference)
### 在方法之中它代表的是 "物件本身"
### $this配合 '->'' 運算子及可用以存取物件成員
### 此方法中，必須用$this來便是目前呼叫方法是哪一個物件，
### 並透過他取得該物件的成員，如：
```
class WebPage
{
	...
	//定義setTitle()方法
	function setTitle($str)
	{
		//將參數$str的直射給title成員
		$this->title=$str;
	}
}
```
### 虛擬變數$this除了用於儲存成員，也可呼叫類別中的'另一個'方法，如：
```
class Test
{
	function func1()
	{
		...
	}

	function func2()
	{
		...
		//呼叫func1()方法
		$this->func1();
	}
}
```
