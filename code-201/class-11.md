# Class 11 Reading Notes

## HTML and CSS Chapter 16 (pg 406-427)
Images 

### Key Topics
- controlling sizes o fimages in CSS
- aligning images in CSS
- adding background imgs

Sizes: class small, large, medium <br>
Aligning: float: left margin Right, float: right margin left, width and height <br>
background-image <br>
background-repeat <br>
background-attachment <br>
background-position  <br>


### Chapter 16 Summary
- you can specify the dimension of images using CSS. this is very helpful when you use the same sized img on several pages
- images can be aligned both horizontally and vertically using CSS
- you can use a background img behind the box created by any element on a page
- background img can appear just once or be repeated across the background of the box
- you can create img rollover effects by moving the background position of an img 
- to reduce the num of img your browser has to load, you can create img sprites 

## HTML and CSS Chapter 19 (pg 476-492)
Practical Information

### Key Topics
- Search engine optimization
- using analytics to understand visitors 
- putting your site on the web

#### Search engine optimization SEO
huge topic! <br>
There are  both on and off page techniques to this <br>
On-page  7 key places where words can improve findability <br>
1. Page title
2. URL/web address
3. headings
4. text
5. link text
6. img alt text
7. page description 

#### how to identify keywords and phrases
determing which keywords to use for your site can be hard: tips to find good keywords:
1. brainstorm
2. organize
3. research 
4. compare
5. refine 
6. map


### Chapter 19 Summary 
- Search engine optimization helps visitors find your sites when using search engines 
- analytics tools such as google analytics allow you to see how many people visit your site, how they find it, and what they do when they get there
-  to put your site on the web you will need to obtain a domain name and webhosting
-  FTP programs allow you to transfer files from your local computer to your web server
-  many companies provide platforms for blogging, email newsletters, e-commerce and other popular website tools (to save you writing them from scratch) 


## Article [Audio and Video Elements](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs)

HTML5 comes with elements for embedding media in documents
   
    <video> 
    <audio>
    
These come with their own APIs for controlling their aspects <br>
creates a video player inside the browser  Example code:
          
          <video controls>
              <source src="rabbit320.mp4" type="video/mp4">
              <source src="rabbit320.webm" type="video/webm">
              <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
          </video>

Here the whole player is wrapped in a div element so it can be styled as one unit: <br>
The video contains two sources, so it can be loaded depending on the browser: <br>
And it contains buttons so that you can control the functions of the video (play/pause): 

Referenced Example code:

          <div class="player">

              <video controls>
                <source src="video/sintel-short.mp4" type="video/mp4">
                <source src="video/sintel-short.webm" type="video/webm">
                <!-- fallback content here -->
              </video>
            <div class="controls">
               <button class="play" data-icon="P" aria-label="play pause toggle"></button>
               <button class="stop" data-icon="S" aria-label="stop"></button>
            <div class="timer">
            <div></div>
               <span aria-label="timer">00:00</span>
             </div>
                <button class="rwd" data-icon="B" aria-label="rewind"></button>
                 <button class="fwd" data-icon="F" aria-label="fast forward"></button>
             </div>
          </div>
          
 You can also use CSS to style the video: 
Example CSS: 
      
          .controls {
            visibility: hidden;
            opacity: 0.5;
            width: 400px;
            border-radius: 10px;
            position: absolute;
            bottom: 20px;
            left: 50%;
            margin-left: -200px;
            background-color: black;
            box-shadow: 3px 3px 5px black;
            transition: 1s all;
            display: flex;
        }

        .player:hover .controls, player:focus .controls {
           opacity: 1;
        }
        
        @font-face {
           font-family: 'HeydingsControlsRegular';
           src: url('fonts/heydings_controls-webfont.eot');
           src: url('fonts/heydings_controls-webfont.eot?#iefix') format('embedded-opentype'),
                url('fonts/heydings_controls-webfont.woff') format('woff'),
                url('fonts/heydings_controls-webfont.ttf') format('truetype');
           font-weight: normal;
            font-style: normal;
         }

        button:before {
          font-family: HeydingsControlsRegular;
          font-size: 20px;
          position: relative;
          content: attr(data-icon);
          color: #aaa;
          text-shadow: 1px 1px 0px black;
         }

And finally some example JS code:

      const media = document.querySelector('video');
      const controls = document.querySelector('.controls');

      const play = document.querySelector('.play');
      const stop = document.querySelector('.stop');
      const rwd = document.querySelector('.rwd');
      const fwd = document.querySelector('.fwd');

      const timerWrapper = document.querySelector('.timer');
      const timer = document.querySelector('.timer span');
      const timerBar = document.querySelector('.timer div');
      
 More goes into this but these are a small snippet of just how much can go into a single video 
 
    

