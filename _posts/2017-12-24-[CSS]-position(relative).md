# CSS position
<html>
	<head>
		<style>
		div{
				border:5px solid tomato;
				margin:10px;
			}
		#me{
			position:relative;
			left:100px; 
			top:100px;
		}
		</style>
	</head>
	<body>
		<div id="other">other</div>
		<div id="parent">
		parent
		
postions이 relative이면 이 상태이다.
이때 offset을 사용할 수 있다.(static 이면 사용 불가)
		<div id="me">me</div>
		</div>
	</body>
</html>



