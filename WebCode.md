```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
	<style type="text/css">
		body
		{
			background-image: url(https://i.pinimg.com/originals/94/73/6b/94736bae93845f832c1f816579d85cdb.png); /*url()*/
			background-repeat: no-repeat; /*指定背景圖案重不重複。預設值是 "repeat"*/
			background-attachment: fixed; /*指定背景圖案是否在螢幕上固定 當網頁捲動時，背景圖案固定不動*/
			background-position: center; /*指定背景圖案的位置*/
			background-size: 100%; /*背景填滿度*/
		}
		.AAA
		{
			background-color: rgb(255,255,240);
			/*overflow: auto; /*預設會自動使用捲軸*/
			/*overflow: hidden; /*自動隱藏超出的文字或圖片*/
		}
		ul
		{
			margin: 0;
			padding: 0;
			list-style: none;
		}
		ul.float-nav
		{
			border: #css 1px solid;
			display: inline-block;	
			font-family: 'Open Sans',Arial,sans-serif; /*字體*/
			font-size: 13px;
		}
		ul.float-nav li
		{
			position: relative; /*可以結合top 、 bottom、 left 、 right 的屬性來偏移其文檔的常規位置*/
			white-space: nowrap; /*強制不換行,在同一行內顯示所有內容,不使用overflow:auto時,文字將超過畫面外*/
			border-right: #AAAAAA 1px solid; /*border-right:  border-width:1px; border-style:solid;的縮寫*/
			/*#ccc（顏色代碼）的顏色，1px(1像素，px是像素的縮寫)，solid(邊框為實線)*/
		}
		ul.float-nav > li:last-child
		{
			border-right: none; /* border-right 是?性'border-right-color', 'border-right-style', 和'border-right-width'的三者的??*/
														/*'右邊框顏色'			'右邊框樣式'			'右邊框寬度'				*/
		}	
		ul.float-nav > li
		{
			float: left; /* 只有第一層是靠左對齊*/
		}
		ul.float-nav a
		{
			background-color: #fff;
			color: #333;
			display: block; /*可以設定寬高/padding/margin，但其屬性仍會向右占滿容器，下個元素就會換行來呈現，並不會並排*/
			padding: 0 30px;
			text-decoration: none;/*替網頁的文字做特效，例如增加文字的上線、文字底線或刪除線的效果*/
			line-height: 40px;/*line-height 的中文是「行高」，簡單來說就是兩行文字中間的高度*/
		}
		ul.flost-nav a:hover /* 滑鼠滑入按鈕變色*/
							/*https://www.great-good.tw/articles/css-hover/   >>>>   hover效果*/
		{
			background-color: #ef5c28;
        	color: #fff;
		}
		ul.float-nav li:hover > a
		{
			background-color: #9955FF;
        	color: #fff;
		}
		ul.float-nav ul
		{
			border: #ccc 1px solid;
			position: absolute;
			z-index: 99; /*控制 z 軸的位置*/
			left: -1px;
			top: 100%;
			min-width: 180px; /*min-width 屬性的功能是用來控制網頁元素的最小寬度*/
		}
		ul.float-nav ul li
		{
			border-bottom: #ccc 1px solid; /*下框線*/
		}
		ul.float-nav ul li:last-child
		{
			border-bottom: none; /*下框線*/
		}
		ul.float-nav ul ul /*第三層以後的選單出現位置與第二層不同*/
		{
			z-index: 999;
			top: 10px;
			left: 90%;
		}
		ul.float-nav ul
		{
			display: none;
		}
		ul.float-nav li:hover > ul
		{
			display: block;
		}
		.BBB
		{

		}
	</style>
</head>
<body>
	<div id="menu">
		<header>

			<nav class="AAA">
				<a href="https://www.kali.org/downloads/">
					<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcR_J0jeV
					tpPPGGGrD0mxIz3sm4H50ymNBHZEg&usqp=CAU" width="65" alt="dd"></a>
				<ul class="float-nav">
					<li><a href="#"><h4>註冊 登入</h4></a>
						<ul>
							<li>
								<div class="alert">
  									<center>
  									<form method="get">
  										<fieldset>
  											<legend><h2>Login</h2></legend>
  										<div class id="BBB">
  										<br>
										帳號:<input type="text" name="帳號"  size="20" value="" placeholder="輸入帳號" autocomplete="off" 
										style=" 
										border:1px; 
										border-bottom-style: groove;
										border-top-style: none;
										border-left-style:none;
										border-right-style:none;">
										<br/>
										<br/>
										密碼:<input type="password" name="密碼" size="20" value="" placeholder="輸入密碼" 
										style=" 
										border:1px; 
										border-bottom-style: groove;
										border-top-style:none;
										border-left-style:none;
										border-right-style:none;">
										</div>
										</fieldset>
										<br/>
										<br/>
										<input type="submit" name="" value="登入" >
										<input type="reset" name="" value="清除">
									</form>
									</center>
								</div>
							</li>
							<li><a href="#">測試1.2</a></li>
							<li><a href="#">測試1.3</a></li>
							<li><a href="#">測試1.4</a></li>
						</ul>
					</li>
					<li><a href="#"><h4>實習W2</h4></a>
						<ul>
							<li><a href="#">測試2.1</a></li>
							<li><a href="#">測試2.2</a></li>
							<li><a href="#">測試2.3</a></li>
							<li><a href="#">測試2.4</a></li>
						</ul>
					</li>
					<li><a href="#"><h4>實習W3</h4></a>
						<ul>
							<li><a href="#">測試3.1</a></li>
							<li><a href="#">測試3.2</a></li>
							<li><a href="#">測試3.3</a></li>
							<li><a href="#">測試3.4</a></li>
						</ul>
					</li>
					<li><a href="#"><h4>實習W4</h4></a>
						<ul>
							<li><a href="#">測試4.1</a></li>
							<li><a href="#">測試4.2</a></li>
							<li><a href="#">測試4.3</a></li>
							<li><a href="#">測試4.4</a></li>
						</ul>
					</li>
					<li><a href="#"><h4>實習W5</h4></a>
						<ul>
							<li><a href="#">測試5.1</a></li>
							<li><a href="#">測試5.2</a></li>
							<li><a href="#">測試5.3</a></li>
							<li><a href="#">測試5.4</a></li>
						</ul>
					</li>
					<li><a href="#"><h4>實習W6</h4></a>
						<ul>
							<li><a href="#">測試6.1</a></li>
							<li><a href="#">測試6.2</a></li>
							<li><a href="#">測試6.3</a></li>
							<li><a href="#">測試6.4</a></li>
						</ul>
					</li>
				</ul>
			</nav>
		</header>
	</div>

</body>
</html>


```
