test3.html
```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body style="text-align: center;">
		<form method="post" autocomplete="off" action="as.php">
			會員帳號<input type="text" name="uname"><br>
			密碼<input type="password" name="pwd">
			<input type="submit" value="登入">
		</form>
</body>
</html>
```
test03.php
```html
<!DOCTYPE html>
<html>
<head>
	<title>test03.php</title>
	<meta charset="utf-8">
	<style>
		body{text-align: center;}
		div.welcome{color: green}
		div.error{color: red}
	</style>
</head>
<body>
	<?php
	$userpass = array('admin' => '12345', //使用者帳號密碼
						'aaa' => 'zzz');
	if(! $_POST['uname'] || ! $_POST['pwd'])
	{
		echo "<div class='error'>請輸入帳號密碼</div>";
	}
	else
	{
		$username = $_POST['uname'];//將POST的帳密設定給$username與$password
		$password = $_POST['pwd'];	//將POST的帳密設定給$username與$password
		if ( $userpass[$username] == $password )
		{
			echo "<div class='welcome'>$username 大哥您好,早ㄤㄤ</div>";
		}
		else
		{
			echo "<div class='error'>錯誤</div>";
		}
	}
	?>
</body>
</html>
```
