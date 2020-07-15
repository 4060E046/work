test2.html
```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
	<form method="get" action="test02.php">
		<p>我想吃:</p>
		<select name="study[]" size="5" multiple>
			<option>牛排</option>
			<option>荷包蛋</option>
			<option>薯餅</option>
			<option>義大利麵</option>
			<option>雪花冰</option>
			<option>銅鑼燒</option>
		</select>
		<br>
		<input type="submit" value="送出">
		<input type="reset" value="清除 ">
	</form>

</body>
</html>
```
test02.php
```
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
	<?php 
		header('content-type: text/html; charset=utf-8');
		echo '大哥您要學習的是:<br>';

		foreach($_GET['study'] as $study)
			echo $study. '<br>';
	?>

</body>
</html>
```
