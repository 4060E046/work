```html
<?php
	header('Content-Type: text/html; charset=utf-8');
	include("mysql.inc.php");
	//價格大於400的書籍與價位
	$sql = "SELECT 書籍名稱, 價格 FROM books WHERE 價格 > 400";
	$result = mysqli_query($conn, $sql);

	//用表格顯示
	echo '<table border="1"><tr><th>書籍名稱</th><th>價格</th></tr>';
	//以mysqli_fetch_array()執行結果做為while迴圈判斷條件
	//資料讀完後再執行mysqli_fetch_array()回傳FALSE讓迴圈停止
	while($row = mysqli_fetch_array($result))
	{
		echo "<tr><th>$row[0]</th><th>$row[1]</th></tr>";
	}
	echo '</table>';
?>
```
