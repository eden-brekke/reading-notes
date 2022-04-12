# Class 14 Reading Notes

## Article [What Google Learned From its Quest to Build the Perfect Team](https://www.nytimes.com/2016/02/28/magazine/what-google-learned-from-its-quest-to-build-the-perfect-team.html)

This article is going into the dynamics of what makes a good team. Google went through and studied a large number of their companies teams in hopes to find a pattern that made it obvious what made a good team. However, with all the data that they collected that didn't find a clear pattern. Through more research the article goes into more specified findings that a good team really has to do with emotional intelligence, and caring for one-another within the team, being friendly and giving everyone a fair chance to speak, leaning on the individuals strengths and using those strengths to create a team where the sum is greater than the parts. Terms they used for good teams are traits like "conversational turn-taking" and "average social sensitivity" (psychological safety). Direct quote "A shared belief held by members of a team that the team is safe for interpersonal risk-taking, a sense of confidence that the team will not embarrass, reject, or punish someone for speaking up. Describes a tea,m climate characterized by interpersonal trust and mutual respect in which people are comfortable being themselves." I think often in my past I've had good group dynamics and I always kind of felt like I was someone who easily over-shared, I've never really felt embarrassed to share what I''m going through, and I didn't realize that this aspect of myself might contribute to how I tend to have good group dynamics. For example in my last job, I struggled at first and felt kind of a disconnect between myself and my team members, but as soon as I decided to just start sharing and being more personal with my coworkers, they also started opening up, I got more comfortable asking them how they were doing and pointing out when I noticed they weren't doing the best. I think this really fostered our team dynamic to thrive, and we all became a lot closer as individuals and as a team. I really value this article and the perspective it offers on the human aspect of being in a team. 


## Article [CSS Transforms](https://learn.shayhowe.com/advanced-html-css/css-transforms/)

#### Transform syntax 

Transform syntax is pretty simple 
```
CSS:
div {
  -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
}
```

They have multiple vendor prefixes to fain the best support across all browsers. <br>
the unprefix-ed one at the bottom is for browsers that fully support the transform property. <br>

### 2D Transforms
elements can get distorted or transformed on both 2D and 3D planes. <br>
2D transforms work on x and y axes <br>
3D works on x y and z axes <br>

#### 2D rotate

<br>

```html
 HTML Code Example:
 
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

CSS Code Example:

```css
.box-1 {
  transform: rotate(20deg);
}
.box-2 {
  transform: rotate(-55deg);
}
```

#### 2D Scale

Using the scale value within the transform property allows you to change the appeared size of an element. Default is 1 <br>

HTML Code:
```html
HTML: 

<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```
CSS:
```css
.box-1 {
  transform: scale(.75);
}
.box-2 {
  transform: scale(1.25);
}
```

#### 2D Translate 
Translate value works a bit like relative positioning, pushing and pulling an element in different directions without interrupting the normal flow.<br>

HTML Code:
```html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```
CSS:
```css
.box-1 {
  transform: translateX(-10px);
}
.box-2 {
  transform: translateY(25%);
}
.box-3 {
  transform: translate(-10px, 25%);
}
```

#### 2D Skew
Used to distort elements on x and y axes <br>
HTML Code:

```html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```
```css
.box-1 {
  transform: skewX(5deg);
}
.box-2 {
  transform: skewY(-20deg);
}
.box-3 {
  transform: skew(5deg, -20deg);
}
```

#### Combining Transforms 
Common for multiple transforms to be used at once, rotating and scaling the size of an element <br>
Using multiple transform declarations will not work, each declaration will overwrite the one above it.  So instead:

HTML Code: 
```html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```
CSS
```css
.box-1 {
  transform: rotate(25deg) scale(.75);
}
.box-2 {
  transform: skew(10deg, 20deg) translateX(20px);
}
```
Combining it all into a 2D Cube!
HTML :
```html
<div class="cube">
  <figure class="side top">1</figure>
  <figure class="side left">2</figure>
  <figure class="side right">3</figure>
</div>
```
CSS: 
```css
.cube {
  position: relative;
}
.side {
  height: 95px;
  position: absolute;
  width: 95px;
}
.top {
  background: #9acc53;
  transform: rotate(-45deg) skew(15deg, 15deg);
}
.left {
  background: #8ec63f;
  transform: rotate(15deg) skew(15deg, 15deg) translate(-50%, 100%);
}
.right {
  background: #80b239;
  transform: rotate(-15deg) skew(-15deg, -15deg) translate(50%, 100%);
}
```
#### Transform Origin

Default transform origin is dead center of an element (50% vertical and 50% horizontal)  <br>
transform-origin can accept values for either axis <br>

#### Perspective

in order for 3D transforms to work the element needs a perspective from which to transform (a vanishing point) <br>
the value for perspective can be set to none or a length measurement. <br>
perspective-origin  can use the same values as transform-origin,<br>
main difference between the two is that transform determines coordinates used to calculate the change of transform <br>
but perspective identifies coordinates of the vanishing point of a transform <br>

#### 3D transforms 
3D adds in the z axis from all the 2d tranforms.  giving us control of depth, as well as length and width. <br>

#### 3D rotate
rotates an object either clockwise or counterclockwise on a flat plane

#### 3D scale 
by using scaleZ the 3D element transform can be scale on the z axis

#### 3D translate
by using translateZ value a negative value will push the element further away, resulting in a smaller element 

#### shorthand 3D transforms
rotate3d, scale3d, transistion3d, and matrix3d

#### transform style
transform-style to allow nested elements to transform within their own three-dimensional plane 

#### Backface visibility
when working with 3D you can transform an element causing them to face away from the screen. <br>
if you prefer not to see them you can set backface-visibility to hidden <br>






## Article [CSS Transitions and Animations](https://learn.shayhowe.com/advanced-html-css/transitions-animations/)

### Transitions
For a transition to take place an element must have a change in state <br>
different styles must be identified for each state <br>
easy was for determining styles for different states is by using the :hover :focus :active and :target pseudoclasses <br>
Below are ways to play with the transition function <br>


#### Property
Determines exactly what properties will be altered in conjunction with the other transitional properties. <br>
by default all properties within an elements different states will be altered upon change. 

#### properties 
background-color <br>
background-position <br>
border-color <br>
border-width <br>
border-spacing <br>
bottom <br>
clip <br>
color <br>
crop <br>
font-size <br>
font-weight <br>
height <br>
left <br>
letter-spacing <br>
line-height <br>
margin <br>
max-height <br>
max-width <br>
min-height <br>
min-width <br>
opacity <br>
outline-color <br>
outline-offset <br>
outline-width <br>
padding <br>
right <br>
text-indent <br>
text-shadow <br>
top <br>
vertical-align <br>
visibility <br>
width <br>
word-spacing <br>
z-index <br>

#### Duration
set using general timing values (s and ms can be fractional too) how long the transition runs

#### Timing
Set the speed in which the transition will move

#### Delay
Set a delay with a time value (s or ms) show how long to delay before transition starts

#### Shorthand Transitions
Shorthands include: property, duration, timing-function, delay

### Animations

#### Keyframes
To set multiple points at which an element should undergo a transition, <br>
use the @keyframe rules to include name and breakpoints as well as propterties intended to be animated 

#### Name
once keyframes for an animation have been declared they need to be assigned a name 

#### Duration, timing function and delay
once you have declared the name you can also include duration, timing and a delay if desired

#### Iteration
By deafult animations run their cycle once from beginning to end and then stop <br>
you can set them to repeat 

#### Direction
declares the direction an animation completes. 

#### Play state
allows animation to be played or paused. <br>
running and paused are the keyword values

#### Fill Mode
Fill mode is how the element should be styled either before or after the animation is run<br>
(none, forward, backwards or both) are the keyword values

#### Shorthand Animations
animation-name, duration, timing-function, delay, iteration-count, direction, fill-mode and play-state are all the shorthand

## Article [8 simple CSS3 Transitions that will wow users](https://www.webdesignerdepot.com/2014/05/8-simple-css3-transitions-that-will-wow-your-users)

### 1. Fade in: having things fade in is pretty common 
```css
.fade
{
        opacity:0.5;
}
.fade:hover
{
        opacity:1;
}
```

### 2. Change Color
```css
.color:hover
{
        background:#53a7ea;
}
```
### 3. Grow and Shrink 
```css
.grow:hover
{
        -webkit-transform: scale(1.3);
        -ms-transform: scale(1.3);
        transform: scale(1.3);
}

.shrink:hover
{
        -webkit-transform: scale(0.8);
        -ms-transform: scale(0.8);
        transform: scale(0.8);
}
```
### 4. Rotate Elements 
```css
.rotate:hover
{
        -webkit-transform: rotateZ(-30deg);
        -ms-transform: rotateZ(-30deg);
        transform: rotateZ(-30deg);
}
```
### 5. Square to Circle
```css
.circle:hover
{
        border-radius:50%;
}
```
### 6. 3D shadow
```css
.threed:hover
{
        box-shadow:
                1px 1px #53a7ea,
                2px 2px #53a7ea,
                3px 3px #53a7ea;
        -webkit-transform: translateX(-3px);
        transform: translateX(-3px);
}
```
### 7. Swing
```css
@-webkit-keyframes swing
{
    15%
    {
        -webkit-transform: translateX(5px);
        transform: translateX(5px);
    }
    30%
    {
        -webkit-transform: translateX(-5px);
       transform: translateX(-5px);
    } 
    50%
    {
        -webkit-transform: translateX(3px);
        transform: translateX(3px);
    }
    65%
    {
        -webkit-transform: translateX(-3px);
        transform: translateX(-3px);
    }
    80%
    {
        -webkit-transform: translateX(2px);
        transform: translateX(2px);
    }
    100%
    {
        -webkit-transform: translateX(0);
        transform: translateX(0);
    }
}
@keyframes swing
{
    15%
    {
        -webkit-transform: translateX(5px);
        transform: translateX(5px);
    }
    30%
    {
        -webkit-transform: translateX(-5px);
        transform: translateX(-5px);
    }
    50%
    {
        -webkit-transform: translateX(3px);
        transform: translateX(3px);
    }
    65%
    {
        -webkit-transform: translateX(-3px);
        transform: translateX(-3px);
    }
    80%
    {
        -webkit-transform: translateX(2px);
        transform: translateX(2px);
    }
    100%
    {
        -webkit-transform: translateX(0);
        transform: translateX(0);
    }
}

.swing:hover
{
        -webkit-animation: swing 1s ease;
        animation: swing 1s ease;
        -webkit-animation-iteration-count: 1;
        animation-iteration-count: 1;
}
```
### 8. Inset Border
```css
.border:hover
{
        box-shadow: inset 0 0 0 25px #53a7ea;
}
```


## DEMO [6 buttons animated](https://codepen.io/retyui/pen/ByoaXV)
Code in Demo:
HTML: 
```html
<div class="group">
		<button class="blam">Blam</button>
		<button style="-webkit-animation-delay: .3s;animation-delay: .3s;" class="syke">Syke</button>
		<button style="-webkit-animation-delay: .6s;animation-delay: .6s;" class="later">Later</button>
	</div>
```

And the CSS: 
```CSS
@import url(https://fonts.googleapis.com/css?family=Droid+Sans:700);
		*{
			margin: 0;
			padding: 0;
			box-sizing: border-box;
			transition: all .1s;
		}
		body{
		background-color: #424242;
			font-family: 'Droid Sans', sans-serif;
		}
		.group{
			text-align: center;
			margin: 20px auto;
		}
		.group button{
			margin-top: 10px;
		}
		button{
/*			box-sizing: border-box;*/
			background: NONE;
			border: none;
			outline: none;
			border-radius: 3px;
			padding: 15px 70px;
			color:white;
			text-transform: uppercase;
			font-weight: 700;
			text-shadow: 0 1px 3px rgba(0, 0, 0, 0.41);
			box-shadow: 0 3px 0 0 #383838;
			border:3px solid transparent;
			
		
			animation: pulse 1s linear infinite alternate;
			-webkit-animation: pulse 1s linear infinite alternate;
		}
		.active,
		button:active{
			background-image: linear-gradient(rgba(0,0,0,.1) 13%, transparent 13%,transparent);
			box-shadow: 0 1px 0 0 #383838;
			color: rgba(0, 0, 0,.45);
			text-shadow: none;
			
			
			-webkit-animation-play-state: paused; 
    	animation-play-state: paused;
		}
		button:focus,
		button:hover{
			-webkit-animation-play-state: paused; 
    	animation-play-state: paused;
		}
		
		
		.blam:focus,
		.blam:hover{
			background-color:#0097bd;
		}
		.blam{
			background-color:#00bff0;
			border-color: #00bff0;
		}
		
		.syke:focus,
		.syke:hover{
			background-color:#ad4e4e;
		}
		.syke{
			background-color:#e06464;
			border-color:#e06464;
		}
		
		.later:focus,
		.later:hover{
			background-color:#7c8b8f;
		}
		.later{
			background-color:#a8bdc2;
			border-color:#a8bdc2;
		}
		
		@-webkit-keyframes pulse {
			100% {
				transform: translateY(6.9px); 
			} 
		}

		@keyframes pulse {
			100% {
				transform: translateY(6.9px); 
			} 
		}
```   
A lot of code just for three floating buttons!

## DEMO [CSS3 Animations: Keyframes](https://codepen.io/akshaychauhan/pen/dyBqVo)

Code in Demo: 
HTML featuring some inline script:
```html
<h1>CSS3 Animations: Keyframes</h1>


<div class="exampleDiv">
  <div class="ball" style="-webkit-animation: bouncing 2s 15 linear;-moz-animation: bouncing 2s 15 linear;"></div>
</div>


<!-- WhatsHelp.io widget -->
<script type="text/javascript">
    (function () {
        var options = {
            facebook: "220186546416", // Facebook page ID
            company_logo_url: "//storage.whatshelp.io/widget/d2/d2db/d2dbaa07f22d96b7ad8426beb00493d0/20031613_10154783116346417_1007255058190022230_n.png", // URL of company logo (png, jpg, gif)
            greeting_message: "Hello, how may I help you? Just send us a message now to get assistance.", // Text of greeting message
            call_to_action: "Message me", // Call to action
            position: "right", // Position may be 'right' or 'left'
        };
        var proto = document.location.protocol, host = "whatshelp.io", url = proto + "//static." + host;
        var s = document.createElement('script'); s.type = 'text/javascript'; s.async = true; s.src = url + '/widget-send-button/js/init.js';
        s.onload = function () { WhWidgetSendButton.init(host, proto, options); };
        var x = document.getElementsByTagName('script')[0]; x.parentNode.insertBefore(s, x);
    })();
</script>
```
and the CSS involved: 
```CSS
@import url(https://fonts.googleapis.com/css?family=Montserrat:700);
body {
  background-color: #ffcc46;
}

::-webkit-scrollbar {
    width: 8px;
}

::-webkit-scrollbar-thumb {
    background: rgba(0,0,0,0.12);
}

::-webkit-scrollbar-track {
    visibility: hidden;
}

h1 {
  font-family: 'Montserrat', helvetica, arial;
  sans-serif;
  margin: 20px;
}

.exampleDiv {
  height: 200px;
  width: 200px;
  border: 1px solid rgba(0, 0, 0, 0.1);
  float: left;
  margin: 20px;
  text-align: center;
  position: relative;
  background-color: #ffffff;
  border-radius: 4px;
}

.ball {
  position: absolute;
  height: 20px;
  width: 20px;
  border-radius: 10px;
  background-color: #c0392b;
}

@-webkit-keyframes bouncing {
  40%, 70%, 90% {
    bottom: 0;
    -webkit-animation-timing-function: ease-out;
  }
  0% {
    bottom: 200px;
    left: 0;
    -webkit-animation-timing-function: ease-in;
  }
  55% {
    bottom: 50px;
    -webkit-animation-timing-function: ease-in;
  }
  80% {
    bottom: 25px;
    -webkit-animation-timing-function: ease-in;
  }
  95% {
    bottom: 10px;
    -webkit-animation-timing-function: ease-out;
  }
  100% {
    left: 110px;
    bottom: 0;
    -webkit-animation-timing-function: ease-out;
  }
  @-moz-keyframes bouncing {
    40%, 70%, 90% {
      bottom: 0;
      -webkit-animation-timing-function: ease-out;
    }
    0% {
      bottom: 200px;
      left: 0;
      -webkit-animation-timing-function: ease-in;
    }
    55% {
      bottom: 50px;
      -webkit-animation-timing-function: ease-in;
    }
    80% {
      bottom: 25px;
      -webkit-animation-timing-function: ease-in;
    }
    95% {
      bottom: 10px;
      -webkit-animation-timing-function: ease-out;
    }
    100% {
      left: 110px;
      bottom: 0;
      -webkit-animation-timing-function: ease-out;
    }
```

It baffles me how complicated CSS can get


## DEMO [404](https://codepen.io/kieranfivestars/pen/MYdQxX)

Code in Demo:
HTML: very simple
```html
<h1>4</h1>
<h1>0</h1>
<h1>4</h1>
```
And the Less simple: CSS:
```CSS
body {
  margin:0;
  font-family:sans-serif;
  color:#f25252;
  background:#f7f7f7;
}
h1 {
  font-size:11rem;
  position:absolute;
  transform:translate(-50%,-50%);
  margin:0;
}
h1:nth-of-type(1){
  animation: range 4s infinite;
}
h1:nth-of-type(2){
  left:50%;
  top:50%;
  animation: size 4s infinite;
}
h1:nth-of-type(3){
  animation: range2 4s infinite;
}
@keyframes range {
  0%  {left:42%;top:50%;font-size:11rem;}
  25% {left:50%;top:40%;font-size:4.5rem;}
  50% {left:58%;top:50%;font-size:11rem;}
  75% {left:50%;top:60%;font-size:4.5rem;}
  100%{left:42%;top:50%;font-size:11rem;}
}
@keyframes range2 {
  0%  {left:58%;top:50%;font-size:11rem;}
  25% {left:50%;top:60%;font-size:4.5rem;}
  50% {left:42%;top:50%;font-size:11rem;}
  75% {left:50%;top:40%;font-size:4.5rem;}
  100%{left:58%;top:50%;font-size:11rem;}
}
@keyframes size {
  0%  {font-size:11rem;}
  25% {font-size:26rem;}
  50% {font-size:11rem;}
  75% {font-size:26rem;}
  100%{font-size:11rem;}
}
```


## DEMO [Pure CSS Bounce Animation](https://codepen.io/dp_lewis/pen/QWMxRR)

Code found in the demo: 
the HTML involved: very little 
```html
	<div class="animation animation-1">
		<div class="ball"></div>
	</div>
	<div class="animation animation-2">
		<div class="ball"></div>
	</div>
	<div class="animation animation-3">
		<div class="ball"></div>
	</div>	
```
And the CSS Invovled: 
```CSS 
/* Animation -------------------- */

@keyframes balltransform {
	0% {
		border-radius:50%;
		height:100%;
		width:60%;
	}
	29% {
		height:100%;
		width:60%;
	}
	30% {
		height:50%;
		width:100%;
	}
	40% {
		height:80%;
		width:80%;
	}
	59% {
		height:100%;
		width:60%;
	}
	60% {
		height:50%;
		width:100%;
		border-radius:50%;
		transform:rotate(0);
	}
	100% {
		height:80%;
		width:80%;
		border-radius:0;
		transform: rotate(-180deg);
	}
}

@keyframes ballbounce {
	/* up */
	0% {
		top:-30%;
		animation-timing-function: ease-in;
	}
	/* floor */
	30% {
		top:80%;
		animation-timing-function: ease-out;
	}
	/* up */
	40% {
		top: 20%;
	}
	/* up */
	45% {
		top:17%;
		animation-timing-function: ease-in;
	}
	/* floor */
	60% {
		top:80%;
		animation-timing-function: ease-out;
	}
	/* up */
	75% {
		top:30%;
	}
	90% {
		top:25%;
		animation-timing-function: ease-in;
	}
	/* floor */
	100% {
		top:110%;
		animation-timing-function:ease-out;
	}
}

@keyframes scalemask {
	0% {
		mask-size:0%;
	}
	65% {
		mask-size:0%;
	}
	78%,100% {
		mask-size:300%;
	}
}

@keyframes scalemask2 {
	0% {
		-webkit-mask-size:0%;
	}
	83% {
		-webkit-mask-size:0%;
	}
	100% {
		-webkit-mask-size: 300%;
	}
}

* {
	box-sizing:border-box;
}

body {
	padding:0;
	margin: 0;
}

/* Ball -------------------- */
.ball {
	width:5rem;
	height:5rem;
	left:50%;
	position:absolute;
	z-index:1;
	margin-left:-2.5rem;
	animation:ballbounce 4s 1s infinite;
	animation-fill-mode:both;
}

.ball:after {
	content:" ";
	color:#fff;
	display:block;
	margin:auto;
	border-radius:50%;
	background:#fff;
	width:100%;
	height:100%;
	animation: balltransform 4s 1s infinite;
}

/* Animation containers -------------------- */
.animation {
	background:#297acb;
	height:100vh;
	width:100vw;
	position:relative;
	z-index:1;
}

.animation-2,
.animation-3 {
	position:absolute;
	top:0;
	left:0;
	-webkit-mask-size:0;
	-webkit-mask-image:radial-gradient(circle closest-side,black 0%,black 90%,rgba(255,255,255,0) 92%);
	-webkit-mask-repeat:no-repeat;
	-webkit-mask-position:center center;
	animation-fill-mode:both;
}

.animation-2 {
	background:purple;
	animation:scalemask 4s 1s infinite;
}

.animation-3 {
	animation:scalemask2 4s 1s infinite;
}

.animation-2 .ball:after {
	background: #297acb;
}
```
 Wow that's a lot of Code for a simple animation! 
