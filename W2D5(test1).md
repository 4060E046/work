火車訂票系統
```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
	<style>
		form,p
		{
			float: left;
			background-color: pink;
			margin: 10px;
			padding: 10px;
		}
	</style>
</head>
<body>
	<form method="post" action="<?php echo $_SERVER['PHP_SELF'] ?>">
		<select name="begin">
			<?php
				$station = array("台北", "桃園", "新竹", "台中", "嘉義", "台南", "高雄", "屏東",);
				for($i=0;$i<=7;$i++)
				{
					if($i == 0)
					{
						echo '<option value="' . $i .'" selected>';
					}
					else
					{
						echo '<option value="' . $i .'">';
					}
					echo $station[$i] . "</option>";
				}
			?>
		</select>到
		<select name="end">
			<?php 
				for($i=0;$i<=7;$i++)
				{
					if($i == 7)
					{
						echo '<option value="' .$i .'" selected>';
					}
					else
					{
						echo '<option value="' .$i .'">';
					}
					echo $station[$i] . "</option>";
				}
			?>
		</select><br>

		車廂:<input type="radio" name="class" value="標準" checked>標準
			 <input type="radio" name="class" value="商務">商務<br>
		票種:<input type="radio" name="type" value="普通" checked>普通
			 <input type="radio" name="type" value="優待">優待<br>
		張數:<input type="number" name="number" size="4" value="1">張<br>
		<input type="submit" value="確定">
		<input type="reset" value="清除">
	</form>

	<?php
		$price = array(
		[0, 	225,    380,    560,    1095,   1595, 	1955,   2140], 
    	[45, 	0, 	    345, 	515, 	1060, 	1560, 	1910, 	2095], 
    	[175,	140, 	0,      345, 	880, 	1380, 	1740, 	1925], 
    	[315,   280, 	140,	0, 	    715, 	1215, 	1565, 	1750], 
    	[765,	730, 	590, 	450, 	0,  	670, 	1030, 	1215], 
    	[1180, 	1145, 	1005, 	860, 	410,	0, 	    540, 	715],  
    	[1480, 	1445, 	1305, 	1160, 	710, 	295, 	0, 	    355],  
    	[1630,  1595, 	1455, 	1310, 	860, 	450, 	150, 	0]);

    if(isset($_POST['begin']) && isset($_POST['end']) && $_POST['begin'] != $_POST['end'])
    {
    	echo '<p>';
    	$from = $_POST['begin'];
    	$to = $_POST['end'];
    	echo "從<b>{$station[$from]}</b>到<b>{$station[$to]}</b>站<br>";
    	echo $_POST['class'] . "車廂" . $_POST['type'] . "票" . $_POST['number'] . "張<br><br>";

    	
    	if(($_POST['class'] == '商務' && $to > $from) || ($_POST['class'] == '標準' && $to < $from))
    	{
    	  	$total=$price[$from][$to] * $_POST['number'];
    	}
    	else
    	{
    	  	$total=$price[$to][$from] * $_POST['number'];
    	}
    	if($_POST['type'] == '優待') $total = $total*0.5;
    	{
    		echo "小計 " .$total."元";
    	}
   	 	echo '</p>';
       
    }

	?>
</body>
</html>
```
