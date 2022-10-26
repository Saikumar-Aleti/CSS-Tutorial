CSS - Cascading Style Sheets - Responsible for styling the web
Syntax - Selector{property:value} Example - h1{color:red; font-size:30px}
Inline CSS - specifying styles directly in the element using style property.
Internal CSS - specifying styles in the head element using style tag.
External CSS - Creating a separate file for styles and linking it to the HTML page using <link> tag with a relationship of stylesheet.
Example - <link rel="stylesheet" href="./styles.css" />
when we're getting something externally, let's say in our case, that is going to be fonts and icons, you always want to place those links above your stylesheet because you want to use those external resources in your stylesheet.
Power Struggle
Last rule, let's say if an element has color property in inline CSS, and internal CSS. inline CSS is going to override internal CSS. Let's say if the element has a color property in external CSS. inline CSS is going to override internal and external CSS.
CSS rule - h1{color:red;}
h1 is the selector
{} is the declaration block
each property inside the declaration block is called a declaration.
color is property
red is a value for color property
Element Selector - We type out the name of the HTML element we would like to type out. Exampel - h1{}h2{}p{}
Grouping Selectors - h1,h2,p{}
ID Selector - You can use the id property on an element to style the element.

<h1 id="title">Hello world!</h1>
#title{color:red;background:black}
Please keep in mind that id of an element should be unique. If multiple elements are going to have the same ID, you might as well use the class property.
color property is for the color of the text in an element.
background property is the color of the background color of an element.
Class Selector - You can use class property to group elements together.
<h1 class="green">I'm green!</h1>
<h1 class="red">I'm red!</h1>
<h1 class="green">I'm green!</h1>
<h1 class="red">I'm red!</h1>
.green{
    color:green;
}
.red{
    color:red;
}

an element can have multiple classes - <h1 class="red uppercase">I'm red!</h1>
.red{
color:red;
}
.uppercase{
text-transform:Uppercase;
}

ID and Class can be used on the same element.

<h1 id="title" class="red uppercase">Hello world!</h1>

div - used to group multiple elements

<div class="red">
<h1>Hello world!</h1>
<h2>This is Saikumar Aleti!</h2></div>
<div class="green">
<h1>Hello world!</h1>
<h2>This is Saikumar Aleti!</h2></div>
span - used to group inline content
<p>Hey! This is <span class="name">Saikumar Aleti</span>

Inheritance
Children inherit styles from parent unless, they have their own styles.
body element is the parent of all the elements placed inside of it. If the children has a matching style property, it is going to override the parent property.

Last rule, specificity and universal selector
Last rule - if the value of a property of an element is declared multiple times in a CSS file, then you're always going to see that the values specified during the last declaration will be applied to the element
Specificity
If there are two or more CSS rules that point to the same element, the selector with the highest specificity value will "win", and its style declaration will be applied to that HTML element.

Think of specificity as a score/rank that determines which style declaration is ultimately applied to an element.
![alt text](./Screenshots/Screenshot%202022-09-18%20140501.png)

Universal Selector - Using universal selector, you can select all elements in you document. Syntax \*{}. Mainly we use it to get rid of default browser styles.

Combining selectors - You can combine multiple selectors together to select an element. For example to select a paragraph within an div with a class of container, you can use .container p{}. This is known as a descendant selector. Futher examples, .container #main {} div p{}

Color Properties
Color property is going to control the color of the element and background-color or background property is going to control background color of an element. background can be used instead of back-ground color. background shorthand comes from background-color and background-image.
You can use one or more of the following options for colors,

1. Direct names, example, white, red, black blue etc.
2. RGB (Red Blue Green), values range from 0-255. Syntax, color: rgb(255, 255, 255) - white color
   color: rgb(255,0,0) - red color
   color: rgb(0,255,0) - green color
   color: rgb(0,0,255) - blue color
   color: rgb(0,0,0) - black color
   You can values between 0 to 255 to form various colors.
3. RGBA (Red Blue Green Opacity/transparency) - Opacity and transparency values ranges from 0 to 1. 0 is totally transparent and 1 is totally opaque.
   background: rgba(255, 0, 0, 0.75)
   rgba() of opacity one is same as using rgb()
4. Hexadecimal value or Hex values in short. Hex values are similar to RGB but instead of one value for RGB we have two values and they range form 1-15. 1-9 are regular numbers but 10-15 are alphabets. 10-A, 11-B, 12-C, 13-D, 14-E and 15-F.
   For red color, we'll be using, #ff0000.
   For green color, we'll be using, #00ff00.
   For blue color, we'll be using, #0000ff.
   For black, we'll be using, #000000 or #000.
   For white, we'll be using, #ffffff or #fff.
   If you're using three values between 0 and 255, you'll be getting black.

CSS Units
pixels - absolute values, one pixel is 1/96th of an inch.
96 pixels = 1 inch
font-size, width and height use CSS units as their values.
font-size controls the size of the font
width controls width of an element
height controls height of an element
Default font-size of a browser is 16px. Size of h3 is also 16px.
h1 is a block level element.

percent units - relative units, they depend on parents.

<div class="outer">
<div class="inner"></div>
</div>

.outer{
width: 200px;
height: 200px;
background: black
}
.inner{
width: 50%;
height: 50%
background: #0000ff
}

em units - relative units, depends on parent if no parent has a matching style then browser - the default of browser is 16px
1em - 16px - default browser style
1em - base value (16px)*1 = 16px
2em - base value (16px)*2 = 32px
em is unit that is dependent on the font-size of the element. If the font-size increases for the element, height specified by em also increases.

<div>
<h1 class="absolute">
CSS Units!</h1><h2 class="relative">CSS Units</h2>
</div>

div{
font-size: 30px;
}
.absolute{
font-size:32px;
}
.relative{
font-size:2rem;
}

Web Page
h1 - 32px
h2 - 60px

rem units - relative units, depends on the root element which is html. If the root has no matching property, it takes default browser value. You can change the default browser value from the browser setting. rem doesn't not depend on their parent. In the below example, div will have no effect on h2.

<div>
<h1 class="absolute">CSS Units!</h1>
<h2 class="relative">CSS Units</h2>
</div>

html{
font-size: 30px;
}
div{
font-size:5px;
}
.absolute{
font-size:32px;
}
.relative{
font-size:2rem;
}

Web Page
h1 - 32px
h2 - 60px

Viewport Units - relative units, depends on the screen-size. vh and vw doesn't depend upon parent.
vh - viewport height - percent of the screen
vw - viewport width - percent of the screen

<div>
<h1 class="absolute">CSS Units!</h1>
<h2 class="relative">CSS Units</h2>
</div>
div{
    background:red;
    width: 100vw;
    height: 100vh;
}

Default browser styles and google chrome DevTools
Browser will by default provide styles for all HTMl elements These styles come from user-agent stylesheet. We need to overwrite these styles in our stylesheet. We can test our styles using chrome dev tools.

Calc() - as the name indicates it is a function to perform math operations. It is very useful in calculating width and height. We can mix and match values with calc().

<ul class="navbar">
      <li>Home</li>
    </ul>
    <div></div>

universal selector {
margin: 0;
padding: 0;
box-sizing: border-box;
}
.navbar {
background: grey;
color: aqua;
width: 100vw;
height: 20px;
}
div {
background: rgba(140, 100, 20, 0.7);
width: 100vw;
height: calc(100vh - 20px);
}

height:auto,min-height, max-height, overflow
By default if we don't don't provide any value, height would be set to auto. Let's say, if a div has two headings, then the height of the div will be equal to the height of the two headings. In other words, height of the div will be the height of the content.
if we set height property and if the connect is exceeding the height specified, we can use min-height instead, this property sets the height of the element to be atleast equal to the height of the content. If the content is meeting the specified height then it goes with the specified height.
max-height - max-height is used to set maximum height of an element and we can use overflow property with it, if the content is exceeding the height limit. Overflow property can have a values, hidden and scroll, hidden will hide the overflowing text. Scroll will allow you to scroll the content within the overflowing element.

Typography
font-size -size of the fonts
font-family - describes the font family of the element

h1{
font-size: 16px;
font-family: Verdana;
}

There might be case where the browser might not support the font-family you're using. To avoid this case, we supply multiple fonts as a stack to the font-family and end of the stack we place the generic font-family, if the browser couldn't find any of the before font families, then it will see the generic font family and get something closer to it. Generic font-family example - serif, san-serif, cursive, fantasy and monospace.

font-weight - describes the thickness of the font. Can be a number of word. Example h1{font-weight:400;}h1{font-weight:500;}h1{font-weight:bold;}
font-style - describes the style of the font. Example, normal, italic ect. Example h1{font-style:italic;}h1{font-style:normal;}h1{font-style:oblique;}

text-align and text-indent
text-align is for the alignment of the text. Example values are left, right, center ect..
text-indent is for indenting the text. Example values are 20px, 6rem, 6em ect..

line-height - it can be an absolute or relative value. Example, h1{
line-height:24px;
}
h1{
line-height: 1.5rem;
}
If we don't assign any type for the values, it is going to multiply the number with font-size of that element to get line height.
h1{
line-height: 1.5;
}

letter-spacing - spacing in between the individual letter. It can be an absolute or relative value.
h1{
letter-spacing:0.5rem;
}
h1{
letter-spacing:8px;
}

word-spacing - spacing in between the individual words. It can be an absolute or relative value.
h1{
letter-spacing:10px;
}

text-decoration - used for text underlining, over-lining, line-through etc.
a{
text-decoration:none; //removing the underlining that comes by default with a link
}
h1{
text-decoration:underline; // Adding underline to a h1
}
h1{
text-decoration:line-through; // adding line through text
}

text-transform - it's gonna control what kind of casing we have for our text.
h1{
text-transform:uppercase;
}
h1{
text-transform:lowercase;
}
h1{
text-transform:capitalize;
}

CSS Box Model - Each and every element in CSS is represented as a box. We have multiple properties that allows us to work with that box.
A box model has a margin, border, padding and content. Consider content to the text inside of your element. Padding is the distance from content to the edge of our element. A border will be spanning all across our element. You can margin to be the distance between elements or edges of the screen.

padding - distance between content and edge of the element.
Example, h1{padding-top:20px;
padding-right:20px;
padding-bottom:20px;
padding-left:20px;}
Alternatively you can also give only two values, h1{padding: 20px 20px;} first value will be applied to the top and bottom and second value will be applied to right and left.
If all the four values are matching, you can provide a single value like h1{padding: 20px}

margin - distance between element and the screen or the element and other element. Browser will by default provide a marign for our page. You can set the browser margin to 0 for all elements using \*{margin:0}
Example, h1{margin-top:20px;
margin-right:20px;
margin-bottom:20px;
margin-left:20px;}
Alternatively you can also give only two values, h1{margin: 20px 20px;} first value will be applied to the top and bottom and second value will be applied to right and left.
If all the four values are matching, you can provide a single value like h1{margin: 20px}
margin is shared by two elements technically. If you margin of one element to 0, you cannot be sure that will be case between there might been a margin for other element.

padding creates space around elements content and margins create space around elements. We have full control over each side of the element for both margin and padding.

border - creates border around an element. For example, a solid border, a dashed border etc. You can control all the sides using border propety with a value of width.
Example,
h1{
border-style:solid;
border-width:1rem;
border-color:red;
}

There is a shorthand for border property selector{border: width style color;}. Example - h1{border: 1rem solid red}

You can control individual side of a border by using border-top, border-bottom, border-right and border-left properites. You can use the shorthand even in this case.
h1{
broder-top-style:solid;
broder-top-width: 20px;
border-top-color: red;
}
h1{
border-top:20px solid red;
border-right:30px solid red;
border-bottom:20px solid red;
border-left:30px solid red;
}

border-radius, negative margins
border-radius - makes the edges of a border rounder. Can be any value, absolute or relative.
h1{
padding:1.5rem;
border: 20px solid red;
border-radius: 1rem
}

negative margins - You can use negative values for margin property to reduce the distance between the elements.
h1{
margin: 50px
}
p{
margin: -50px 50px 50px 50px; //places p right below h1
}

Outline and Outline Offset
Outline is after border and before margin in our box-model. Outline offset property make the outline property rather useful. You can offset the outline inwards or outwards using the outline offset property. Outline can also be written using a shorthand.

a{
background:green;
color:black;
text-decoration: none;
padding: 1.25rem 1.5rem;
text-transform: uppercase;
border: 20px solid blue;
outline-width: 0.5rem;
outline-color: red;
outline-style:solid;
outline-offset: -22px
}
a{
background:green;
color:black;
text-decoration: none;
padding: 1.25rem 1.5rem;
text-transform: uppercase;
border: 20px solid blue;
outline: 20px solid red;
outline-offset: -22px;
}

CSS Hack
When you feel something is off in your layout, you can troubleshoot it using a bordero on all elements.
\*{
border: 2px solid red;
}
That way you'll clearly see where the element starts, where it ends and what's the distance between them.

Display Property
Elements have display property set by default. block elements always start a new lines and spans full width of the screen because they have a display property set to block. Example block level elements are div, h1, p etc.
Inline elements doesn't start in a new line and spans only the content because they have a display property set to inline. Example inline elements are span, link, img.
Using CSS we can change the display property of the elements.
Display property is mostly used in horizontal alignment. To align inline elements in the center, you can simply set text-align:center on the parent of the inline element.
To align block elements in the center you need to give it first a width and then set right and left margins to auto. Value of margin top and bottom doesn't matter.
h1{
margin:0 auto;}
text-alignment:center only aligns the text of the block level elements. We need to set margin right and left to auto to get them into center.

For block level elements, browser respects width, height, margin top and margin bottom. For inline elements, browser doesn't respect width, height, margin top and margin bottom.

<h1>Hello world!</h1>
<span>This is Saikumar Aleti</span>
h1{
    color:white;
    background:blue;
    width:200px;
    height:200px;
    margin-top:100px;
    margin-bottom: 100px;
}
span{
    color:white;
    background:blue;
    width:200px;
    height:200px;
    margin-top:100px;
    margin-bottom: 100px;
}
Width, height, margin-top and margin-bottom styles will only be applied to the h1 element, they will not be applied to span element.
