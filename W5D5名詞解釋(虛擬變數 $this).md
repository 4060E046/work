## 虛擬變數 $this

### $this是個特殊的參照函數(reference)
#### 在方法之中它代表的是 "物件本身"
#### $this配合 '->'' 運算子及可用以存取物件成員
#### 此方法中，必須用$this來便是目前呼叫方法是哪一個物件，
#### 並透過他取得該物件的成員，如：
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
#### 虛擬變數$this除了用於儲存成員，也可呼叫類別中的'另一個'方法，如：
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
### 另一個例子
###### https://ithelp.ithome.com.tw/articles/10114707
#### 這邊的 $this->hello 屬性對應的就是 public $hello 的屬性宣告
#### 而$this指的正是demo這個物件主體
#### 要注意的是，屬性是屬於 "物件本體全域 "
#### 他只要是在這個物件中，任何一個方法(method)都可以直接叫用他
#### 這也是為什麼物件之於函式來說，某方面而言反而較具彈性
#### 因為不需要去對方法內的變數進行 "全域宣告 "
#### 可以這樣做，但會變成整個程式都可以使用這個變數
```
class demo{
  
    public $hello = 'Hello World';

    function hello(){
        echo $this->hello;
    }
}   
$demo = new demo;
$demo->hello();
```
#### 在物件中要呼叫其他的函式，則是使用
```
$this->otherMethod();
```
