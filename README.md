# delta-demo
This a Demo for Git &amp; Github Class.
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Analog Clock in HTML - CSS - JS</title>
	<!-- Custom CSS -->
	style{
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;700&display=swap');

*{
	margin: 0;
	padding: 0;
}

body{
	font-family: 'Poppins', sans-serif;
	background: rgb(238,174,202);
	background: radial-gradient(circle, rgba(238,174,202,1) 0%, rgba(148,187,233,1) 100%);
	position: relative;
	display: flex;
	justify-content: center;
	align-items: center;
	height: 100vh;
}

.clock{
	background-color: rgb(49,47,47);
	width: 300px;
	height: 300px;
	border-radius: 50%;
	color: #fff;
	border: 5px solid #fff;
	box-shadow: 0px 0px 10px rgba(255,255,255,0.7), 0px 0px 20px rgba(0,0,0,0.7);
	font-size: 26px;
	font-weight: bold;
	display: flex;
	justify-content: center;
	align-items: center;
	position: relative; 
}

.clock ul li{
	list-style: none;
	position: absolute;
	text-align: center;
	transform: rotate(calc(30deg * var(--i)));
	inset: 5px;
}

.clock ul li span{
	transform: rotate(calc(-30deg * var(--i)));
	display: inline-block;
}

.clock:after{
	content: '';
	width: 10px;
	height: 10px;
	background-color: #fff;
	border-radius: 50%;
	position: absolute;
}

.needle{
	display: flex;
	justify-content: center;
	align-items: flex-end;
}

.needle span{
	width: 5px;
	height: var(--h);
	background-color: var(--clr);
	position: absolute;
	border-radius: 5px;
}
  }
</head>
<body>
	
	<!-- Clock  -->
	<div class="clock">
		
		<div class="needle hr" style="--h:60px; --clr:red"><span></span></div>
		<div class="needle mn" style="--h:80px; --clr:blue"><span></span></div>
		<div class="needle ss" style="--h:100px; --clr:white"><span></span></div>

		<ul>
			<li style="--i:1"><span>1</span></li>
			<li style="--i:2"><span>2</span></li>
			<li style="--i:3"><span>3</span></li>
			<li style="--i:4"><span>4</span></li>
			<li style="--i:5"><span>5</span></li>
			<li style="--i:6"><span>6</span></li>
			<li style="--i:7"><span>7</span></li>
			<li style="--i:8"><span>8</span></li>
			<li style="--i:9"><span>9</span></li>
			<li style="--i:10"><span>10</span></li>
			<li style="--i:11"><span>11</span></li>
			<li style="--i:12"><span>12</span></li>
		</ul>
		
	</div>

<!-- Custom JS -->
<script src="script.js">
  function show_clock(){

	let h = document.getElementsByClassName('hr')[0];
	let m = document.getElementsByClassName('mn')[0];
	let s = document.getElementsByClassName('ss')[0];

	let date = new Date(); 

	let hours = date.getHours();
	let minutes = date.getMinutes();
	let seconds = date.getSeconds();

	h.style.transform = `rotate(${30 * hours + minutes/2}deg)`;
	m.style.transform = `rotate(${6 * minutes}deg)`;
	s.style.transform = `rotate(${6 * seconds}deg)`;

	let sound = new Audio('sound.mp3');
	sound.play();
}


setInterval(show_clock, 1000);
</script>
</body>
</html>
