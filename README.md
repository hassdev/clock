<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8" />
<title>svg test</title>
<style>
	svg {
		border: solid 1px #00f;
		width: 700px;
		height: 550px;
	}
</style>
</head>

<body>
	<svg id="mysvg" width="300" height="300"></svg>
	<p id="status">a</p>
	<p id="status2">b</p>
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
	<script>
	$(document).ready(function(){
		//dimension of svg
		var svgw = $("#mysvg").width();
		var svgh = $("#mysvg").height();

		//center point of svg
		var xcenter = svgw/2;
		var ycenter = svgh/2;

		var time = 0;
		setInterval(function() {
			time = time + 6;
			$("#status").html(time);

			var d = new Date();
			var y = d.getFullYear(); //年
			var m = d.getMonth()+1; //月
			var n = d.getDate(); //日
			var h = d.getHours(); //時
			var i = d.getMinutes(); //分
			var s = d.getSeconds(); //秒

			var sec = s * 6;
			var min = i * 6;
			var hour = (h * 30) + (i/2);

			var point = '<circle cx="' + xcenter + '" cy="' + ycenter + '" r="10" stroke="red" stroke-width="2" fill="orange" />';
			var path_sec = '<path d="M' + xcenter + ',' + ycenter + ' l 250,0' + '" stroke="orange" stroke-width="1" transform="rotate(' + (sec-90) + ' ' + xcenter + ' ' + ycenter + ')" />';
			var path_min = '<path d="M' + xcenter + ',' + ycenter + ' l 200,0' + '" stroke="blue" stroke-width="2" transform="rotate(' + (min-90) + ' ' + xcenter + ' ' + ycenter + ')" />';
			var path_hour = '<path d="M' + xcenter + ',' + ycenter + ' l 150,0' + '" stroke="red" stroke-width="2" transform="rotate(' + (hour-90) + ' ' + xcenter + ' ' + ycenter + ')" />';
			var path1 = '<path d="M' + (xcenter+200) + ',' + ycenter + ' l 50,0' + '" stroke="orange" stroke-width="3" transform="rotate(30 ' + xcenter + ' ' + ycenter + ')" />';
			var path2 = '<path d="M' + (xcenter+200) + ',' + ycenter + ' l 50,0' + '" stroke="orange" stroke-width="3" transform="rotate(60 ' + xcenter + ' ' + ycenter + ')" />';
			var path3 = '<path d="M' + (xcenter+200) + ',' + ycenter + ' l 50,0' + '" stroke="orange" stroke-width="3" transform="rotate(90 ' + xcenter + ' ' + ycenter + ')" />';
			var path4 = '<path d="M' + (xcenter+200) + ',' + ycenter + ' l 50,0' + '" stroke="orange" stroke-width="3" transform="rotate(120 ' + xcenter + ' ' + ycenter + ')" />';
			var path5 = '<path d="M' + (xcenter+200) + ',' + ycenter + ' l 50,0' + '" stroke="orange" stroke-width="3" transform="rotate(150 ' + xcenter + ' ' + ycenter + ')" />';
			var path6 = '<path d="M' + (xcenter+200) + ',' + ycenter + ' l 50,0' + '" stroke="orange" stroke-width="3" transform="rotate(180 ' + xcenter + ' ' + ycenter + ')" />';
			var path7 = '<path d="M' + (xcenter+200) + ',' + ycenter + ' l 50,0' + '" stroke="orange" stroke-width="3" transform="rotate(210 ' + xcenter + ' ' + ycenter + ')" />';
			var path8 = '<path d="M' + (xcenter+200) + ',' + ycenter + ' l 50,0' + '" stroke="orange" stroke-width="3" transform="rotate(240 ' + xcenter + ' ' + ycenter + ')" />';
			var path9 = '<path d="M' + (xcenter+200) + ',' + ycenter + ' l 50,0' + '" stroke="orange" stroke-width="3" transform="rotate(270 ' + xcenter + ' ' + ycenter + ')" />';
			var path10 = '<path d="M' + (xcenter+200) + ',' + ycenter + ' l 50,0' + '" stroke="orange" stroke-width="3" transform="rotate(300 ' + xcenter + ' ' + ycenter + ')" />';
			var path11 = '<path d="M' + (xcenter+200) + ',' + ycenter + ' l 50,0' + '" stroke="orange" stroke-width="3" transform="rotate(330 ' + xcenter + ' ' + ycenter + ')" />';
			var path12 = '<path d="M' + (xcenter+200) + ',' + ycenter + ' l 50,0' + '" stroke="orange" stroke-width="3" transform="rotate(360 ' + xcenter + ' ' + ycenter + ')" />';

			$("#mysvg").html(point + path_sec + path_min + path_hour + path1 + path2 + path3 + path4 + path5 + path6 + path7 + path8 + path9 + path10 + path11 + path12);
			$("#status2").html("seconds: " + s + "<br>" + sec + "<br>minutes: " + i + "<br>" + min + "<br>hours: " + h + "<br>" + hour);
		}, 1000);
	});





/*
	var svg = document.querySelector('#mysvg');

	//dimension of svg
	var svgRect = svg.getBoundingClientRect();
	var svgw = svgRect.width;
	var svgh = svgRect.height;

	//center point of svg
	var xcenter = svgw/2;
	var ycenter = svgh/2;

	var rayCount = 20;


	//http://stackoverflow.com/a/3642265/1869660
	function makeSVGElement(tag, attrs) {
	    var el= document.createElementNS('http://www.w3.org/2000/svg', tag);
	    for (var k in attrs) {
	        el.setAttribute(k, attrs[k]);
	    }
	    return el;
	}

	var circle = makeSVGElement('circle', { cx: xcenter,
	                                        cy: ycenter,
	                                        r: 10,
	                                        stroke: 'red',
	                                       'stroke-width': 2,
	                                        fill: 'orange' });
	svg.appendChild(circle);

	var rayAngle = 360/rayCount;
	for(var i=0; i<rayCount; i++) {
	    var path = makeSVGElement('path', { d: 'M' + [xcenter, ycenter] + ' h250',
	                                        stroke: 'orange',
	                                       'stroke-width': 1,
	                                        transform: 'rotate(' + [(rayAngle*i), xcenter, ycenter] + ')' });
	    svg.appendChild(path);
	}
*/
	</script>
</body>
</html>
