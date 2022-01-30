<!doctype html>
<html>
<head>
	<meta charset='utf-8'>
	<meta name="viewport" content="width=device-width,initial-scale=1.0,minimum-scale=1.0,maximum-scale=1.0,user-scalable=no">
	<title>슬라이드</title>

	<style>
	/* 브라우저 마진과 패딩 리셋 */
	* {margin:0;padding:0;}
	
	/* INPUT 가리기 */
	.section input[id*="slide"] {display:none;}

	/* 슬라이드 영역 - max-width 크기를 조절해주면 됩니다*/
	.section .slidewrap {max-width:1920px;margin:0 auto;overflow:hidden;}
	.section .slidelist {white-space:nowrap;font-size:0;}
	.section .slidelist > li {display:inline-block;vertical-align:middle;width:100%;transition:all .5s;}
	.section .slidelist > li > a {display:block;position:relative;overflow:hidden;} /* 화살표 화면 밖으로 나가면 안보이도록 OVERFLOW로 가림처리 */
	.section .slidelist > li > a img {width:100%;}

	/* 좌우로 넘기는 LABEL버튼에 대한 스타일 */
	.section .slidelist label {position:absolute;z-index:1;top:50%;transform:translateY(-50%);padding:50px;cursor:pointer;}
	.section .slidelist .left {left:-300px;background:url('https://user-images.githubusercontent.com/80767378/151693253-6af0c53e-d7d8-49b0-b9b5-c50e8a6d2929.png') center center / 100% no-repeat;} /* LEFT -300px로 화살표가 안보이게 되어있도록 준 스타일 */
	.section .slidelist .right {right:-300px;background:url('https://user-images.githubusercontent.com/80767378/151693276-7bfcee67-326a-4d99-8ee8-25338c97499f.png') center center / 100% no-repeat;} /* RIGHT -300px로 화살표가 안보이게 되어있도록 준 스타일 */

	/* INPUT이 체크되면 변화값이 li까지 전달되는 스타일 */
	.section input[id="slide01"]:checked ~ .slidewrap .slidelist > li {transform:translateX(0%);}
	.section input[id="slide02"]:checked ~ .slidewrap .slidelist > li {transform:translateX(-100%);}
	.section input[id="slide03"]:checked ~ .slidewrap .slidelist > li {transform:translateX(-200%);}

	/* INPUT이 체크되면 변화값이 LEFT,RIGHT에 전달되는 스타일 */
	.section input[id="slide01"]:checked ~ .slidewrap li:nth-child(1) .left {left:30px;transition:all .35s ease .5s;} /* 1번 INPUT이 체크되면 1번 슬라이드의 왼쪽 화살표의 LEFT값이 변하면서 나타나도록 준 스타일 */
	.section input[id="slide01"]:checked ~ .slidewrap li:nth-child(1) .right {right:30px;transition:all .35s ease .5s;} /* 1번 INPUT이 체크되면 1번 슬라이드의 오른쪽 화살표의 LEFT값이 변하면서 나타나도록 준 스타일 */
	.section input[id="slide02"]:checked ~ .slidewrap li:nth-child(2) .left {left:30px;transition:all .35s ease .5s;} /* 2번 INPUT이 체크되면 1번 슬라이드의 왼쪽 화살표의 LEFT값이 변하면서 나타나도록 준 스타일 */
	.section input[id="slide02"]:checked ~ .slidewrap li:nth-child(2) .right {right:30px;transition:all .35s ease .5s;} /* 2번 INPUT이 체크되면 1번 슬라이드의 오른쪽 화살표의 LEFT값이 변하면서 나타나도록 준 스타일 */
	.section input[id="slide03"]:checked ~ .slidewrap li:nth-child(3) .left {left:30px;transition:all .35s ease .5s;} /* 3번 INPUT이 체크되면 1번 슬라이드의 왼쪽 화살표의 LEFT값이 변하면서 나타나도록 준 스타일 */
	.section input[id="slide03"]:checked ~ .slidewrap li:nth-child(3) .right {right:30px;transition:all .35s ease .5s;} /* 3번 INPUT이 체크되면 1번 슬라이드의 오른쪽 화살표의 LEFT값이 변하면서 나타나도록 준 스타일 */
	</style>
</head>
<body>

	<div class="section">
		<input type="radio" name="slide" id="slide01" checked>
		<input type="radio" name="slide" id="slide02">
		<input type="radio" name="slide" id="slide03">

		<div class="slidewrap">
			<ul class="slidelist">
				<li>
					<a>
						<label for="slide03" class="left"></label>
						<img src="https://user-images.githubusercontent.com/80767378/151693290-1924da05-e336-45b1-b174-55dad1a6d638.jpg">
						<label for="slide02" class="right"></label>
					</a>
				</li>
				<li>
					<a>
						<label for="slide01" class="left"></label>
						<img src="https://user-images.githubusercontent.com/80767378/151693912-8029e062-70d2-4684-bfa4-04bb120a4a75.jpg">
						<label for="slide03" class="right"></label>
					</a>
				</li>
				<li>
					<a>
						<label for="slide02" class="left"></label>
						<img src="https://user-images.githubusercontent.com/80767378/151693312-3390de98-307c-4cb9-b942-171d0a7dd1ff.jpg">
						<label for="slide01" class="right"></label>
					</a>
				</li>
			</ul>
		</div>
	</div>

</body>
</html>
