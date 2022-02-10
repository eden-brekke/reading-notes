# Class 05 Reading Notes

## HTML and CSS Chapter 5 pg 94-125

### Key Topics
- How to add images to pages
- Choosing the right format
- optimizing images for the web

#### Adding an Img
< img >  <br>
needs a src, can have an alt, and can have a title  <br>
< img src"path/path.img" alt = "image descript"> <br>
you can use CSS to dictate height and width of IMGs <br>

#### Where to place the img code
- before a paragraph: paragraph will start on a new line after img
- inside the start of a paragraph: the first line of text aligns with the bottom of the img
- in the middle of the paragraph: img is placed between the words of the paragraph that it appears in
- block elements always appear on new line
- inline elements sit within block level elements and dont start a new line

#### Three rules for creating imgs
1. Save img in right format
2. Save img at the right size
3. measure image in pixels

#### HTML5 Figure and Figure Captions
- < figure > You can put an image in the figure, and add a < figcaption > under it

### Chapter 5 Summary
- The < img > element is used to add images to a webpage
- you must always specify a src attribute to indicate the source of an img and an alt attribute to describe the content of the img
- you should save images at the size you will be using them on the webpage and in the appropriate format
- photographs are best saved as JPEGs; illustratioins or logos that use flat color are better as PNG or GIF

## HTML and CSS Chapter 11 pg 246-263

### Key Topics
- How to specify colors
- Color terminology and contrast
- background color

#### Types of Color
- Foreground color use color:
- background color use background-color:
- When choosing foreground and background colors, make sure there is enough contrast so they are easily seen

#### Aspects of Color
- RGB Values: values for red green blue (the primary colors)
- HEX codes: hexadecimal codes for red green and blue
- Color Names: represented by predefined names
- Hue: a combo of saturation and brightness
- Saturation: amount of gray in the color
- Brightness(Lightness): amount of black in the color

### Chapter 11 Summary 
- Color Not only brings your site to life, but also helps convey the mood and evokes reactions
- There are three ways to specify colors in CSS
  - RGB Values, Hex Codes, and color name
- Color pickers can help you find the color you want
- It is important to ensure that there is enough contrast between any text and the background color
- CSS3 has introduced an extra value for RGB colors to indicate opacity. it is known as RGBA
- CSS3 also allows you to specify colors as HSL values (Hue Saturation Lightness) with an optional opacity value. HSLA

<br>

## HTML and CSS Chapter 12 pg 264-299

### Key Topics
- Size and Typeface of Text
- Bold, Italics, Captials, Underlines
- Spacing between lines, words, and letters

#### Typeface Terminology 
Font Types
  - Serif : have extra details on the ends of the main strokes
    - Georgia
    - Times
    - Times New Roman 
  - Sans-Serif: straight end to letters (clean)
    - Arial
    - Verdana
    - Helvetica   
  - Monoscape: every letter is the same width 
    - Courier
    - Courier New
  - Cursive
    - Comic Sans MS
    - Monotype Corsiva
  - Fantasy
    - Impact
    - Haettenschweiler    
  
Font Styles
 - weight
   - light: thins
   - medium: norms
   - bold: kinda thick
   - black: THICK
 - Style
   - Normal: norms
   - Italic: slanty
   - Oblique: MORE italicz  
 - Stretch
   - condensed: pushtogetherlike
   - Regular: norms
   - Extended: i  l i k e  m y  s p a c e

#### Specifying
font-family <br>
font-size <br>
font-weight <br>
font-style <br>
text-transform <br>
text-decoration <br>
line-height <br>
letter-spacing <br>
word-spacing <br>
text-align <br>
vertical-align <br>
text-indent <br>
text-shadow <br>
:first-letter <br>
:first-line <br>
:link <br>
:visited <br>
:hover <br>
:active <br>
:focus <br>

#### Attribute Selectors

** Any () are actually scare brackets
|Selector|Meaning|Example|
|:---:|:---:|:---|
|Existence| () matches a specific attribute| p(class)|
|Equality |(=) matches a specific attribute with specific value|p(class="dog"|
|Space|(~=) matches attribute whose value appears in a space spearate list of words|p(class~="dog")|
|Prefix|(^=) matches a specific attribute whose value beings with a specific string|p(attr^"d")|
|Substring|(star=) matches a specific attribute whose value contains a specific substring|p(attrstar="do")|
|Suffix|($=) matches a specific attribute whose value ends with a string|p(attr$"g")|

#### Pixel Percent EMS comparisons 

|Element|Pixel|Percent|EMS|
|:---:|:---:|:---:|:---|
|12px Scale|12px Scale|12px Scale|12px Scale|
|h1|24px|200%|1.5em|
|h2|18px|150%|1.3em|
|h3|14px|117%|1.17em|
|body|12px|75%|100%|
|p|--|--|0.75em|
|16px Scale|16px Scale|16px Scale|16px Scale|
|h1|32px|200%|2em|
|h2|24px|150%|1.5em|
|h3|18px|133%|1.125em|
|body|16px|100%|100%|
|p|--|--|1em|


### Chapter 12 Summary
- There are properties to control the choices of font, size, weight, style, and spacing
- There is a limited choice of fonts that you can assume most people will have installed
- if you want to use a wider range of typefaces there are several options, but you need to have the righ tlicense to use them
- You can control the space between lines of text, individual letters, and words. Text can also be aligned to the left, right, center, or justified. It can also be indented
- you can use pseudo-classes to change the style of an element when a user hovers over a clicks on text, or when they have visisted a link

<br>

## Blog Post [JPEG vs PNG vs GIF](https://blog.imagekit.io/jpeg-vs-png-vs-gif-which-image-format-to-use-and-when-c8913ae3e01d)

Three main file types for images are JPEG, PNG and GIF <br>

#### Compression
 All forms of data we consume on the internet are compressed to reduce size of data(fast) <br>
 Compression can be two types <br>
 1. Lossless
    possible to reconstruct orginal image no info is lost
 2. lossy
    compression is irreversible
 
 #### The three file types
  JPEG is a form of lossy compression; takes advantage of human perception.  <br>
  PNG is a lossless img format. no data is lost, retain higher quality  <br>
  GIF is also lossless, PNG compression is 5-25% better than GIF so now GIF is mostly only used for animations  <br>

#### Transparency
- JPEG don't support transparency
- PNG support transparency in two ways
  -  inserting in alpha channel
  -  or by declaring a single color as transparent
- GIF support transparency by declaring single color in palette as transparent 

#### Colors 
- JPEG image can support around 16million colors
- PNG have two modes
  - PNG8- supports up to 256 colors
  - PNG24 can handle up to 16million like JPEG
- GIF are limited to 256 colors 

#### Animation 
- Of the three file types only GIF supports animation

### tldr;
- use JPEG for all images that contain a natural scene or photograph where variation in color and intensity is smooth
- Use PNG format for any image that needs transparency or for images with text and objects with sharp contrast edges(logos)
- Use GIF format for images that contain animations
