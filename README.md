# test

<!DOCTYPE html>
<html lang="en">

<head>
	<title>без имени</title>
	<meta charset="utf-8">

	<style>
		
		#game {
			width: 200px;
			height: 200px;
			background: white;
			border: 1px solid black;
		}
		
		.block {
			width: 50px;
			height: 50px;
			float: left;
			border: 1px solid black;
			box-sizing: border-box;
		}
		
		
	</style>

	<script type = "text/javascript">
		
		function f0(i,A) {
			document.getElementById('game').onclick = function(event) {
			
			if( i < A.length - 1){
					
				
				if(event.target.id == A[i] || event.target.id == A[i+1]){
					
					event.target.innerHTML = String(i);
					
				} else {
						
					document.getElementById(A[i]).innerHTML = ' ';
					document.getElementById(A[i+1]).innerHTML = ' ';
				
				}
				
				if(document.getElementById(A[i]).innerHTML == String(i) && document.getElementById(A[i+1]).innerHTML == String(i) ){
					console.log("yes");
					i = i + 2;
					
				}
				 
				}
			}
		}
		
		window.onload = function(){ //ждем загрузку окна а потом выполняем код 
			for(var i = 0; i < 16; i++){
				document.getElementById('game').innerHTML+='<div class = "block" id = "'+"a"+i+'"></div>';
			}
			
			var hod = 0;
			
			var i = 0;
					
				
				var B = [];
				
				
				
				var A = { 'a0' : 0,
						  'a1' : 2,
						  'a2' : 7,
						  'a3' : 4,
						  'a4' : 4,
						  'a5' : 5,
						  'a6' : 1,
						  'a7' : 7,
						  'a8' : 2,
						  'a9' : 6,
						  'a10' : 0,
						  'a11' : 5,
						  'a12' : 6,
						  'a13' : 1,
						  'a14' : 3,
						  'a15' : 3,
						   };
				var color = ['blue','green','#4D4D4D','#FFFF00','#A020F0','#A52A2A','#FFA500','#FFC0CB'];	
				
				
				document.getElementById('game').onclick = function(event) {
				
				B.push(event.target.id);
				//console.log(B);
				
				//console.log("color = "+color[A[event.target.id]]);
				
				
				if(B.length){
					//event.target.innerHTML = String(A[event.target.id]);
					document.getElementById(event.target.id).style.backgroundColor = color[A[event.target.id]];
					
					if(B.length%2 == 0)
					{
						
						
						if(A[B[B.length-2]] == A[B[B.length-1]] && B[B.length-2] != B[B.length-1] ){
							//console.log("yes : "+A[B[B.length-2]]+" = "+B[B.length-2]);
							
							
							document.getElementById(B[B.length-2]).style.backgroundColor = color[A[B[B.length-2]]];
							document.getElementById(B[B.length-1]).style.backgroundColor = color[A[B[B.length-1]]];
							
							
							
							//console.log(document.getElementById(String(A[B[0]])).innerHTML);
							
						} else {
							//console.log("no");
							event.target.innerHTML = String(A[event.target.id]);
							document.getElementById(B[B.length-2]).innerHTML = ' ';
							document.getElementById(B[B.length-1]).innerHTML = ' ';
							
							document.getElementById(B[B.length-2]).style.backgroundColor = '#FFFFFF';
							document.getElementById(B[B.length-1]).style.backgroundColor = '#FFFFFF';
							
						}
						
					}
				}
				
				for(var i = 0; i < 16; i++)
					console.log('=> '+Math.floor(Math.random() * 8));
				
				
			}
			
		}
		
	</script>
	
</head>

<body>
	
	<div id = "game"></div>
	
</body>

</html>
