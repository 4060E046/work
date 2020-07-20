str_replace(string的部分字串, 要用來取代search的字串, 被取代的字串)
```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
	<form method="post" action="<?php echo $_SERVER['PHP_SELF'] ?>">
		原始字串:<input name="str" required><br>
		搜尋字串:<input name="find" required><br>
		取代為:<input name="getout" ><br>
		<input type="submit" value="GO" name="submit"> &nbsp;&nbsp;
		<input type="reset" value="NO" name="reset">
	</form>
	<?php
		if( isset($_POST['str']) && isset($_POST['find']) && isset($_POST['getout']))
		{
			$str=$_POST['str'];
			$find = $_POST['find'];
			$getout = $_POST['getout'];
		
		//如果 $str 和 $find 不是空字串
			if($str!='' && $find!='')
			{
				//str_replace(search, replace, string)
				//str_replace(string的部分字串, 要用來取代search的字串, 被取代的字串)
				//str_replace()會區分大小寫
				//str_ireplace()不會區分大小寫
				echo "<p>str_replace('find','getout', 'str')" . '執行結果為=>;<b>' .
				str_replace($find, $getout, $str) . '</b></p>';
			}
		}
	?>	

</body>
</html>
```
