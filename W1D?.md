```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
<?php
$A = "小王";
$B = 18;
$D = "50";
$C = "300W";

print "姓名:" . $A . "<br/>";
print "年齡:" . $B . "<br/>";
print "年齡:" . $D . "<br/>";
print "儲蓄:" . $C . "<br/>";

$Q = "吃吃";
$W = $Q;
print "學生姓名:" . $Q ."<br/>";
print "姓名" . $W ."<br/>";
$test = &$Q;
$test = "凹凹";
print "沒明子" . $Q ."<br/>";
print "看啥?" . $test ."<br/>";


$name = "GGWP";
$$name = "ㄎㄎ";
$username = $$name;
$username1 = ${$name};
echo "變數\$name = $name<br/>";
echo "變數$$name = $GGWP<br/>";
echo "變數$$name = ${$name}<br/>";


echo "string<br/>";
echo ("string<br/>");
print("arg<br/>");
print "arg<br/>";

define("PI", 3);
define("AREA", "面積");
print "此地的" . AREA . ":" . PI*3*3 . "<br/>";

$AA = 5678;
$BB = -1234;
$CC = 0234;
$DD = 0x1A;
$EE = 0x3fc;
echo "5678 = $AA<br/>";
echo "-1234 = $BB<br/>";
echo "0234 = $CC<br/>";
echo "0x1A = $DD<br/>";
echo "0x3fc = $EE<br/>";

echo "測試\t";
echo "測試\r";
echo "測試\n";
echo "測試\\";
echo "測試\$";
echo "測試\"<br/>";

echo 1 <=> 1;
echo 3 <=> 4;
echo 6 <=> 5;
echo "x" <=> "X";
echo "y" <=> "x";
echo "x" <=> "y";

?>
<?php
$AAA = 10;
$BBB = 20;
?>
後遞增:<?php echo $AAA++;?><br/>
AAA現值:<?php echo $AAA;?><br/>
前遞減:<?php echo --$BBB;?><br/>
BBB現值:<?php echo 	$BBB;?><br/>






</body>
</html>
```
