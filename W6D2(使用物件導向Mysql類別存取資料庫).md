```
<?php
	header('content-type:text/html; charset=utf8');

	$dbServer = "localhost";
	$dbUser = "root";
	$dbPass = "123456";
	$dbName = "ch09";

	//使用@抑制建構方法可能產生錯誤訊息
	$mysqli = @new mysqli($dbServer, $dbUser, $dbPass, $dbName);

	//返回錯誤代碼值，如果沒有錯誤發生則返回 0
	if ($mysqli->connect_errno)
		die("無法連結");

	$mysqli->set_charset("utf8");

	$sql = "SELECT 書籍名稱, 價格 FROM books WHERE 價格 > 400";

	//在此取得的查詢結果物件，會於第26行迴圈處呼叫fetch_array()取得每筆資料陣列
	$result = $mysqli->query($sql);

	echo '以下是價格大於 400 的書籍<br>
			<table border="1"><tr><th>書籍名稱</th><th>價格</th></tr>';

	while($row = $result->fetch_array())
	{
		echo "<tr><td>$row[0]</td><td>$row[1]</td></tr>";
	}
	echo '</table>';
	?>
```
