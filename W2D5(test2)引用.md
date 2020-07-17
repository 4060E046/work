include.php
```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
	<?php 
		function testfunction1($x)
		{
			return 2 * $x;
		}
	?>
</body>
</html>
```
run1.php
```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
	<?php
	header('content-type:text/html; charset=utf-8');
	include 'include1.php'; //相對路徑或絕對路徑

	$pi = 3.14;
	echo '圓周率為:' . $pi . '<br>';
	echo '兩倍的圓周率為:' . testfunction1($pi);

	?>
</body>
</html>
```
