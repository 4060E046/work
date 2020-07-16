test05.php
```html
<!DOCTYPE html>
<html>
<head>
  <title>就學貸款</title>
  <meta charset="utf-8">
  <style>
    form
    {
      width: 240px;
      background-color:pink;
      padding: 10px;
    }
    input
    {
      width: 3em;
    }
  </style>
</head>
<body>
    <form method="post" action="<?php echo $_SERVER['PHP_SELF'] ?>">
    貸款金額:<input type="number" name="money" value="5" required>萬元<br><!--[required]交表單之前必須填寫輸入-->
    年利率:<input type="decimal" name="nll" value="1.8" required>%<br>
    還款年數:<input type="number" name="hkns" value="1" required>年<br>
    <input type="submit" name="送出">
    </form>
    <p>
    <?php
        if
          ((isset($_POST['money']) && $_POST['money']>0) &&
            (isset($_POST['nll']) && $_POST['nll']>0) &&
            (isset($_POST['hkns']) && $_POST['hkns']>0))
        {
          $month = $_POST['hkns'] *12; //還款期數
          $ull = $_POST['nll'] /100/12; //月利率
        
    //                               {[(1＋月利率)^月數]×月利率} 
    // 每期(月)攤還金額 = 貸款金額× -----------------------------
    //                                  {[(1＋月利率)^月數]－1}        
        $power = 1;
        for($i=1;$i<=$month;$i++)
        {
          $power = $power * ($ull+1);
        }

        $pay = $_POST['money'] * 10000 *
                        ($power*$ull)/($power-1);
        echo '每月需還:'.ceil($pay).'元';
        }
    ?>     


</body>
</html>
```
41~45程式碼解說
```
$power = 1;
    for($i=1;$i<=$month;$i++)
      {
        $power = $power * ($ull+1);
      }
        
        $ull為月利率
        $power初始值為1
        for迴圈執行直到還款期數'$month'到達為止
        假設$month=5
        令($ull+1)為y
        $power = 1
        ------------------------
        迴圈開始
        1 = 1 * y            // 第1次
        >>>$power = 1y

        1y = 1y * y          // 第2次
        >>>$power = 1y²

        1y² = 1y² * y        // 第3次
        >>>$power = 1y³

        1y³ = 1y³ * y        // 第4次
        >>>$power = 1y⁴

        1y⁴ = 1y⁴ * y        // 第5次
        >>>$power = 1y⁵

        將$ull+1帶入y
        結果為($ull+1)⁵>>月利率的5次方
        -------------------------
```
