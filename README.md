<!DOCTYPE html>
<html lang="en">

<head>
	
	<title>Digital Clock</title>

	<style>
		#clock {
            background-color: rgb(192, 174, 16);
			font-size: 175px;
			width: 900px;
			margin: 200px;
			text-align: center;
			border: 6px solid rgb(49, 131, 117);
			border-radius: 20px;
		}
	</style>
</head>

<body>
	<div id="clock">8:10:45</div>

	<script>
		setInterval(showTime, 1000);
		function showTime() {
			let time = new Date();
			let hour = time.getHours();
			let min = time.getMinutes();
			let sec = time.getSeconds();
			am_pm = "AM";

			if (hour > 12) {
				hour = hour-12;
				am_pm = "PM";
			}
			if (hour == 0) {
				hour = 12;
				am_pm = "AM";
			}

			hour = hour < 10 ? "0" + hour : hour;
			min = min < 10 ? "0" + min : min;
			sec = sec < 10 ? "0" + sec : sec;

			let currentTime = hour + ":"
				+ min + ":" + sec + am_pm;

			document.getElementById("clock")
				.innerHTML = currentTime;
		}

		showTime();
	</script>
</body>

</html>
