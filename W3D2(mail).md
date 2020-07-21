```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
	<?php
	    //mail(to, subject, message, header)
		//mail(收件人, 標題, 內容, 寄件人)
		$to = 'tony@php.flag.com.tw';
		$big = 'Look it!!';
		$little = 'nothing, I just say hello,

		I am very nice.

		HAHA';
		$header = "nuylxha0@gmail.com";
		mail($to, $big, $little, $biger);

	?>

</body>
</html>
```
