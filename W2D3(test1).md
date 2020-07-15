xxx.html
```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
	<form method="post" action="test01.php">
		請輸入名稱:<input type="text" name="username" autocomplete="off" placeholder="輸入名稱">
		<input type="submit" value="送出">
		
	</form>

</body>
</html>
```

test01.php
```
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
	<?php 
		header("content-type: text/html; charset=utf-8");
		if($_POST['username'])
			echo $_POST['username'].'早安哇~';
		else
			echo '你沒輸入';
	?>
</body>
</html>
```
