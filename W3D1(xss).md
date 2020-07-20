```html
<html>
<head>
  <meta charset="UTF-8">
  <title>表單輸入內容</title>
</head>
<body>
  <form method="get" action="<?php echo $_SERVER['PHP_SELF']; ?>">
    反射型XSS測試：<input name="namee">
    <input  type="submit" value="送出">
  </form>
  <?php  
  //<script>alert(1234)</script>
  if($_GET['namee']!='')
    echo $_GET['namee'];    
  ?>
 
</body>
</html>
```
