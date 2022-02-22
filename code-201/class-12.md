# Class 12 Reading Notes

## Article [Chart.js API](https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/)



Charts are better for displaying data visually. <br>
They're easier to look at and to convey data quickly, but not as easy to create. <br>

Fast way to start : [Chart.js docs](https://www.chartjs.org/docs/latest/)
      
        <canvas id="myChart" width="400" height="400"></canvas>
        <script>
        const ctx = document.getElementById('myChart').getContext('2d');
        const myChart = new Chart(ctx, {
            type: 'bar',
            data: {
                labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
                datasets: [{
                    label: '# of Votes',
                    data: [12, 19, 3, 5, 2, 3],
                    backgroundColor: [
                       'rgba(255, 99, 132, 0.2)',
                       'rgba(54, 162, 235, 0.2)',
                       'rgba(255, 206, 86, 0.2)',
                       'rgba(75, 192, 192, 0.2)',
                       'rgba(153, 102, 255, 0.2)',
                       'rgba(255, 159, 64, 0.2)'
                    ],
                    borderColor: [
                      'rgba(255, 99, 132, 1)',
                      'rgba(54, 162, 235, 1)',
                      'rgba(255, 206, 86, 1)',
                      'rgba(75, 192, 192, 1)',
                      'rgba(153, 102, 255, 1)',
                      'rgba(255, 159, 64, 1)'
                    ],
                    borderWidth: 1
              }]
        },
         options: {
            scales: {
                 y: {
                      beginAtZero: true
                  }
              }
         }
        });
       </script>
       
 You can download this file and link it in your HTML
 
#### Drawing a Line chart
 first thing you need to do is create a canvas element in your HTML
      
        <canvas id="" width="" height=""></canvas>
        
 next you need to write a script to retrieve the context of the canvas
                                                                                    
        <script>
            let buyers = document.getElementById('buyers').getContext('2d');
            new Chart(buyers).Line(buyerData);
        </script>
  
  in the same script from above you should create the data. with an object that contains labels for the base of the chart and datasets to describe the values on the chart. 
  

          let buyerData = {
	            labels : ["January","February","March","April","May","June"],
            	datasets : [
		              {
			              fillColor : "rgba(172,194,132,0.4)",
			              strokeColor : "#ACC26D",
		               	pointColor : "#fff",
		               	pointStrokeColor : "#9DB86D",
		              	data : [203,156,99,251,305,247]
		            }
            	]
            }
      
      
#### Drawing a pie chart

Canvas element:

          <canvas id="countries" width="600" height="400"></canvas>

Context to instantiate chart:

          let countries= document.getElementById("countries").getContext("2d");
          new Chart(countries).Pie(pieData, pieOptions);
          
Create the Data:

         let pieData = [
	          {
		          value: 20,
		          color:"#878BB6"
	          },
	          {
		          value : 40,
		          color : "#4ACAB4"
          	},
          	{
        		  value : 10,
		          color : "#FF8153"
          	},
	          {
      		    value : 30,
		          color : "#FFEA88"
	          }
         ];
 
Add options: 
  
          let pieOptions = {
	            segmentShowStroke : false,
  	          animateScale : true
           }
           
           
#### Drawing a Bar Chart
         
Canvas Element: 
  
          <canvas id="income" width="600" height="400"></canvas>
          
 Retrieve element and create graph:
 
          let income = document.getElementById("income").getContext("2d");
          new Chart(income).Bar(barData);
         
Add Data:

        let barData = {
	            labels : ["January","February","March","April","May","June"],
	            datasets : [
		              {
			                fillColor : "#48A497",
			                strokeColor : "#48A4D1",
                			data : [456,479,324,569,702,600]
               		},
	              	{
	                		fillColor : "rgba(73,188,170,0.4)",
                			strokeColor : "rgba(72,174,209,0.4)",
                			data : [364,504,605,400,345,320]
		              }

	            ]
         }
       
### Conclusion
Chart.js is simple to use and really flexible. Once you've mastered the basics, you'll find there are a ton of options. 

       
## Article [Basic Usage](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage)

### THe Canvas Element

At first glance a canvas looks like an img but it doesn't have src or alt attributes 


### Fallback Content

Canvas element differs from img tag in that its easy to define some fallback content to be displayed in older browswers that it's not supported in. 

        <canvas id="stockGraph" width="150" height="150">
              current stock price: $3.15 + 0.15
        </canvas>

        <canvas id="clock" width="150" height="150">
              <img src="images/clock.png" width="150" height="150" alt=""/>
        </canvas>

### The rendering context

Canvas element created a fixed sized drawing surface that exposes one or more rendering contexts 
The canvas is initially blank, to display something a script first needs to access the rendering context and draw on it.
  
        let canvas = document.getElementById('tutorial');
        let ctx = canvas.getContext('2d');

### Checking for support

        let canvas = document.getElementById('tutorial');

          if (canvas.getContext) {  
          let ctx = canvas.getContext('2d');
            // drawing code here
          } else {
           // canvas-unsupported code here
          }

### A skeleton Template

        <!DOCTYPE html>
        <html>
          <head>
           <meta charset="utf-8"/>
           <title>Canvas tutorial</title>
           <script>
              function draw() {
                let canvas = document.getElementById('tutorial');
                if (canvas.getContext) {
                  let ctx = canvas.getContext('2d');
                }
              }
            </script>
            <style>
                canvas { border: 1px solid black; }
            </style>
          </head>
          <body onload="draw();">
             <canvas id="tutorial" width="150" height="150"></canvas>
          </body>
       </html>

![image](https://user-images.githubusercontent.com/85004124/155044271-69fc051d-a9d9-499b-89d6-124e06360c93.png)
<br>


### A simple example 

          <!DOCTYPE html>
          <html>
             <head>
                <meta charset="utf-8"/>
                <script type="application/javascript">
                    function draw() {
                      let canvas = document.getElementById('canvas');
                      if (canvas.getContext) {
                          let ctx = canvas.getContext('2d');

                          ctx.fillStyle = 'rgb(200, 0, 0)';
                          ctx.fillRect(10, 10, 50, 50);

                          ctx.fillStyle = 'rgba(0, 0, 200, 0.5)';
                          ctx.fillRect(30, 30, 50, 50);
      }
                        }
                 </script>
              </head>
              <body onload="draw();">
                  <canvas id="canvas" width="150" height="150"></canvas>
              </body>
           </html>

![image](https://user-images.githubusercontent.com/85004124/155044249-24f5eb91-b66a-4209-b2fb-1f5d9ceba4a1.png)
<br>

## Article [Drawing Shapes with canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes)

Once you have set up a canvas area, you can draw on it! <br>
Canvas has a grid or coordinate space.  <br>

#### Rectangles

You can draw rectangles  <br>

        function draw() {
          let  canvas = document.getElementById('canvas');
          if (canvas.getContext) {
              let ctx = canvas.getContext('2d');

              ctx.fillRect(25, 25, 100, 100);
              ctx.clearRect(45, 45, 60, 60);
              ctx.strokeRect(50, 50, 50, 50);
           }
         }
         
![image](https://user-images.githubusercontent.com/85004124/155044981-0a139781-4352-4136-a634-41d993330dbe.png)
<br>
#### Drawing Paths 

Path is a list of points, connected by segments of lines that can be different shapes, curved or not, of different widths and of different colors. <br>
To make shapes using paths take these steps. 
1. Create a path
2. Use drawing commands to draw into the path
3. once the path has been created you can stroke or fill the path to render it

beginPath() <br>
Creates a new path. Once created, future drawing commands are directed into the path and used to build the path up. <br>
 <br>
Path methods <br>
Methods to set different paths for objects. <br>
 <br>
closePath() <br>
Adds a straight line to the path, going to the start of the current sub-path. <br>
 <br>
stroke() <br>
Draws the shape by stroking its outline. <br>
 <br>
fill() <br>
Draws a solid shape by filling the path's content area <br>
 <br>

#### Triangle
You can draw a triangle <br>

        function draw() {
           let canvas = document.getElementById('canvas');
           if (canvas.getContext) {
               let ctx = canvas.getContext('2d');

               ctx.beginPath();
               ctx.moveTo(75, 50);
               ctx.lineTo(100, 75);
               ctx.lineTo(100, 25);
               ctx.fill();
            }
         }
         
![image](https://user-images.githubusercontent.com/85004124/155045235-af69aed5-1e67-4204-8a99-46c1e8c6a26d.png)
<br>
#### Moving the pen
Create a smiley! move the pen like lifting your pencil off the page

          function draw() {
             let canvas = document.getElementById('canvas');
             if (canvas.getContext) {
                let ctx = canvas.getContext('2d');

                ctx.beginPath();
                ctx.arc(75, 75, 50, 0, Math.PI * 2, true); // Outer circle
                ctx.moveTo(110, 75);
                ctx.arc(75, 75, 35, 0, Math.PI, false);  // Mouth (clockwise)
                ctx.moveTo(65, 65);
                ctx.arc(60, 65, 5, 0, Math.PI * 2, true);  // Left eye
                ctx.moveTo(95, 65);
                ctx.arc(90, 65, 5, 0, Math.PI * 2, true);  // Right eye
                ctx.stroke();
            }
          }

![image](https://user-images.githubusercontent.com/85004124/155045460-e361996a-6cae-421a-aca1-eee732cf748b.png)
<br>
#### Lines    

```js
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    // Filled triangle
    ctx.beginPath();
    ctx.moveTo(25, 25);
    ctx.lineTo(105, 25);
    ctx.lineTo(25, 105);
    ctx.fill();

    // Stroked triangle
    ctx.beginPath();
    ctx.moveTo(125, 125);
    ctx.lineTo(125, 45);
    ctx.lineTo(45, 125);
    ctx.closePath();
    ctx.stroke();
  }
}
```
![image](https://user-images.githubusercontent.com/85004124/155045548-19c3e3eb-d089-409e-aa6c-a9216b696d70.png)
<br>
#### Arcs
```js
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    for (var i = 0; i < 4; i++) {
      for (var j = 0; j < 3; j++) {
        ctx.beginPath();
        var x = 25 + j * 50; // x coordinate
        var y = 25 + i * 50; // y coordinate
        var radius = 20; // Arc radius
        var startAngle = 0; // Starting point on circle
        var endAngle = Math.PI + (Math.PI * j) / 2; // End point on circle
        var counterclockwise = i % 2 !== 0; // clockwise or counterclockwise

        ctx.arc(x, y, radius, startAngle, endAngle, counterclockwise);

        if (i > 1) {
          ctx.fill();
        } else {
          ctx.stroke();
        }
      }
    }
  }
}
```
![image](https://user-images.githubusercontent.com/85004124/155045569-083b7107-3698-4064-a02b-0da938b18117.png)
<br>
#### Quadratic Bezier Curves

```js
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    // Quadratic curves example
    ctx.beginPath();
    ctx.moveTo(75, 25);
    ctx.quadraticCurveTo(25, 25, 25, 62.5);
    ctx.quadraticCurveTo(25, 100, 50, 100);
    ctx.quadraticCurveTo(50, 120, 30, 125);
    ctx.quadraticCurveTo(60, 120, 65, 100);
    ctx.quadraticCurveTo(125, 100, 125, 62.5);
    ctx.quadraticCurveTo(125, 25, 75, 25);
    ctx.stroke();
  }
}
```
![image](https://user-images.githubusercontent.com/85004124/155045603-68e5c84a-8ca2-4176-9188-82899efc3755.png)
<br>
#### Cubic Bezier Curves

```js
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    // Cubic curves example
    ctx.beginPath();
    ctx.moveTo(75, 40);
    ctx.bezierCurveTo(75, 37, 70, 25, 50, 25);
    ctx.bezierCurveTo(20, 25, 20, 62.5, 20, 62.5);
    ctx.bezierCurveTo(20, 80, 40, 102, 75, 120);
    ctx.bezierCurveTo(110, 102, 130, 80, 130, 62.5);
    ctx.bezierCurveTo(130, 62.5, 130, 25, 100, 25);
    ctx.bezierCurveTo(85, 25, 75, 37, 75, 40);
    ctx.fill();
  }
}
```
![image](https://user-images.githubusercontent.com/85004124/155045636-e8b799fa-5cb3-414c-8a5a-7f80c9afc7e7.png)
<br>

#### PACMAN!

```js
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    roundedRect(ctx, 12, 12, 150, 150, 15);
    roundedRect(ctx, 19, 19, 150, 150, 9);
    roundedRect(ctx, 53, 53, 49, 33, 10);
    roundedRect(ctx, 53, 119, 49, 16, 6);
    roundedRect(ctx, 135, 53, 49, 33, 10);
    roundedRect(ctx, 135, 119, 25, 49, 10);

    ctx.beginPath();
    ctx.arc(37, 37, 13, Math.PI / 7, -Math.PI / 7, false);
    ctx.lineTo(31, 37);
    ctx.fill();

    for (var i = 0; i < 8; i++) {
      ctx.fillRect(51 + i * 16, 35, 4, 4);
    }

    for (i = 0; i < 6; i++) {
      ctx.fillRect(115, 51 + i * 16, 4, 4);
    }

    for (i = 0; i < 8; i++) {
      ctx.fillRect(51 + i * 16, 99, 4, 4);
    }

    ctx.beginPath();
    ctx.moveTo(83, 116);
    ctx.lineTo(83, 102);
    ctx.bezierCurveTo(83, 94, 89, 88, 97, 88);
    ctx.bezierCurveTo(105, 88, 111, 94, 111, 102);
    ctx.lineTo(111, 116);
    ctx.lineTo(106.333, 111.333);
    ctx.lineTo(101.666, 116);
    ctx.lineTo(97, 111.333);
    ctx.lineTo(92.333, 116);
    ctx.lineTo(87.666, 111.333);
    ctx.lineTo(83, 116);
    ctx.fill();

    ctx.fillStyle = 'white';
    ctx.beginPath();
    ctx.moveTo(91, 96);
    ctx.bezierCurveTo(88, 96, 87, 99, 87, 101);
    ctx.bezierCurveTo(87, 103, 88, 106, 91, 106);
    ctx.bezierCurveTo(94, 106, 95, 103, 95, 101);
    ctx.bezierCurveTo(95, 99, 94, 96, 91, 96);
    ctx.moveTo(103, 96);
    ctx.bezierCurveTo(100, 96, 99, 99, 99, 101);
    ctx.bezierCurveTo(99, 103, 100, 106, 103, 106);
    ctx.bezierCurveTo(106, 106, 107, 103, 107, 101);
    ctx.bezierCurveTo(107, 99, 106, 96, 103, 96);
    ctx.fill();

    ctx.fillStyle = 'black';
    ctx.beginPath();
    ctx.arc(101, 102, 2, 0, Math.PI * 2, true);
    ctx.fill();

    ctx.beginPath();
    ctx.arc(89, 102, 2, 0, Math.PI * 2, true);
    ctx.fill();
  }
}

// A utility function to draw a rectangle with rounded corners.

function roundedRect(ctx, x, y, width, height, radius) {
  ctx.beginPath();
  ctx.moveTo(x, y + radius);
  ctx.arcTo(x, y + height, x + radius, y + height, radius);
  ctx.arcTo(x + width, y + height, x + width, y + height - radius, radius);
  ctx.arcTo(x + width, y, x + width - radius, y, radius);
  ctx.arcTo(x, y, x, y + radius, radius);
  ctx.stroke();
}
```
![image](https://user-images.githubusercontent.com/85004124/155045676-56519c1a-6393-4bf7-8f0c-0da299b5a3b9.png)
<br>
Overall theres a ton you can do with these, be creavtive!
(All code and images from MDN article)


## Article [Applying Styles and colors](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors)

Colors! You can apply colors to the shapes from before  <br>
*For space* I'm going to leave out the code examples but they can all be found within the article linked above. In my notes I'll put the pictures of the examples for quick personal reference.   <br>

#### Fillstyle:
![image](https://user-images.githubusercontent.com/85004124/155045831-843f8bd9-7f2c-4a9f-b14b-72aba606da36.png)
<br>

#### strokestyle: 
![image](https://user-images.githubusercontent.com/85004124/155045862-a8429fca-58ec-4a83-8b02-4339fa62a757.png)
<br>

#### transparency: 
globalAlpha = transparencyValue <br>

#### globalAlpha: <br>
![image](https://user-images.githubusercontent.com/85004124/155045906-7bb6ca70-afd9-4230-b65d-67605b7b5b8b.png)
<br>

### Line styles: 

#### Line width: 
![image](https://user-images.githubusercontent.com/85004124/155045998-3f083f1d-26d2-4241-8e78-1569073a3254.png)
<br>
#### Line caps:
butt: end at end points <br>
round: rounded ends <br>
square: squared ends <br>
![image](https://user-images.githubusercontent.com/85004124/155046048-9ad74ebd-e2b9-42e0-8f3e-30d31121940f.png)
<br>

#### lineJoin 
![image](https://user-images.githubusercontent.com/85004124/155046611-c0acd726-a94b-49e4-b4cc-72399123b486.png)
<br>

#### miterlimit
![image](https://user-images.githubusercontent.com/85004124/155046642-cb07ba7b-fff1-4c0a-82ef-b7674c0db4b6.png)
<br>

#### createLinearGradient 
![image](https://user-images.githubusercontent.com/85004124/155046695-b1434f11-bf31-4979-bc4e-c478bc71fe62.png)

#### createRadialGradient 
![image](https://user-images.githubusercontent.com/85004124/155046750-46d3e982-9fcf-4ebb-9ac4-fb693a4e1049.png)
<br>

#### createConicGradient 
![image](https://user-images.githubusercontent.com/85004124/155046787-67f3a734-2ee2-47c5-879b-d0035471bc76.png)
<br>

There's a ton that you can do with colors and styles, play around with it, be creative
(All images from MDN article)


## Article [Drawing Text](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text)

There are two methods to render text: 
#### fillText
![image](https://user-images.githubusercontent.com/85004124/155046949-e2e2beea-c911-4671-87c0-76fb77277c65.png)

#### stroke text
![image](https://user-images.githubusercontent.com/85004124/155046963-4b16525e-f49c-4d74-ae6a-ee0ddf4d098f.png)

### Styling text

some properties that let you adjust the way the text gets displayed on the canvas<br>
font = value : current text style being used when drawing text. default is 10px sans-serif <br>
textAlign = value : possible values are start, end, left, right or center, default is start <br>
textBaseline = value : possible values are top, hanging, middle, alphabetic, ideographic, bottom, default is alphabetic  <br>
direction = value : possible values or ltr, rtl, inherit, default is inherit  <br>

(All images from MDN article)
