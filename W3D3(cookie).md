## setcookie()函式執行之前,若有echo()或HTML標籤等輸出,會導致setcookie()函式執行錯誤
```html
<?php
		if(isset($_post['color']))
			$color = htmlentities($_post['color']);
		else if(isset($_COOKIE['color']))
			$color = htmlentities($_COOKIE['color']);
		else
			$color = 'block';
		setcookie("color", $color, time()+30*3600*24);
?>
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
	<style type="text/css">
		div
		{
			float: left;
			margin: 10px;
		}
		p
		{
			text-align: center;
			color: <?php echo $color; ?>
		}
	</style>
</head>
<body>
	<div>
		<fieldset>
			<legend><h2>登樂遊原</h2></legend>
  				<p id="line1">向晚意不適，驅車登古原。</p>
  				<p id="line2">夕陽無限好，只是近黃昏。</p>
  				<p>－李商隱</p>

  		</fieldset>
  	</div>	
  	<br>
  	<form method="POST" action="test01.php">
  		<select name="color">
  			<option value="green">綠</option>
  			<option value="pink">粉</option>
  			<option value="blue">藍</option>
  			<option value="orange">橘</option>
  		</select>
  		<input type="submit" value="送出">
  	</form>
</body>
</html>
```
