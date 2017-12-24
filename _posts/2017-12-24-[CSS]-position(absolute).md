# CSS position(absolute)
<html>
	<head>
		<style>
		#parent,#other,#grand{
				border:5px solid tomato;
			}
		#grand{
			position:relative;
		}
		#me{
			position:absolute;
			background-color: black;
			color:white;
			left:0px; 
			top:0px;
		}
		</style>
	</head>
	<body>
		<div id="other">other</div>
		<div id="grand">
			grand
			<div id="parent">
			parent
				<div id="me">me</div>
			</div>
		</div>
		
1. position이 absolute이면 html을 기준으로 하여 위치를 잡는다.(relative라면 parent 엘리먼트를 기준으로 해서 자리를 잡는다.)
		
		
2. absolute의 초기값은 parent의 자식으로서의 위치를 잡는다. absolute로 하면 부모와 관계가 없어진다.(그래서 me의 박스 크기가 작아 졌다. width, height로 크기를 지정)

3. absolute는 부모가 static인 부모는 다 무시하다가 아닌 position이 나타나면 그 엘리먼트를 기준으로 삼는다.	

#### absolute, relative정리
> absolute는 자신의 부모가 static이면 부모를 따르지 않고, 할아버지, 증조할아버지를 찾아서 relative인 조상을 따른다.(위치만 따른다)

> fixed는 조상을 모두 버리고 자신의 길을 간다.
	</body>
</html>



