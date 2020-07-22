test5.php
```html
<?php
	session_start();
	date_default_timezone_set('Asia/Taipei');
	//若Session的enterTime參數不存在,表示是第一次進入本站
	//紀錄Session起始時間
	if(!isset($_SESSION['enterTime']))
		$_SESSION['enterTime'] = time();
?>
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
	<p>
		本次進站時間是:
		<?php
			echo date("H時i分s秒", $_SESSION['enterTime']);
		?>
	</p>
	<a href="test05.php">瀏覽test05.php</a>
</body>
</html>
```
test05.php
```html
<?php 
	session_start();
	//儲存使用者逗留本站時間的變數
	$delaytime = 0;
	if(isset($_SESSION['enterTime']))
		//計算逗留本站時間
		$delaytime = time() - $_SESSION['enterTime'];
?>
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
	已經逗留本站:
	<?php 
		echo date("H時i分s秒",$delaytime);
	?>
</body>
</html>
```
