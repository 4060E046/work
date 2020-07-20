
test8.html
```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
	<form method="post" action="test8.php">
	請輸入電話:<input type="text" name="telephone">
	<br>
	請輸入身分證:<input type="text" name="id_no">
	<br>
	<input type="" name="">
	<input type="submit" value="GO">


	</form>
</body>
</html>
```
test08.php
```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
	<?php
		// 比對字串
		// preg_match(用來比對的規則運算式, 要比對字串)
		// ^$分別代表字串的開頭與結束
		// \d比對任一數字,等同於[0-9]
		// https://medium.com/verybuy-dev/php%E6%AD%A3%E8%A6%8F%E8%A1%A8%E9%81%94%E5%BC%8F%E6%AF%94%E5%B0%8D-89b03ebc10eb
		header('content-type:text/html; charset=utf-8');
		if( !preg_match('/^[0-9]{2}-[0-9]{8}$/', $_POST['telephone']))
			echo '電話號碼格式錯誤';
		else
			echo '電話號碼格式OK';
		echo '<br>';
		if( !preg_match('/^[a-zA-Z]\d{8}$/', $_POST['id_no']))
			echo '身分證輸入錯誤';
		else
			echo '身分證輸入OK';
	?>
<?php echo '<br>' ?>

</body>
</html>
```
