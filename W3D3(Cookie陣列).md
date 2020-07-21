```html
<?php
	//setcookie("name[index]", value, expire)
	//name: Cookie陣列的名稱
	//index: Cookie 陣列內個元素的索引

	//setcookie("color[red]內的索引不能加上引號
	//若打成setcookie("color['red']"則無法建立或修改陣列元素
	setcookie("color[red]", 'Tony', time()+1*3600*24);
	setcookie("color[green]", 'mary', time()+5*24*3600);
	echo $_COOKIE['color']['red'];
	echo $_COOKIE['color']['green'];
?>
```
