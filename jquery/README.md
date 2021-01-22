# JQuery
### What is JQuery?
<b>
The JavaScript library that prevent our fingers from breaking</b><br>
jQuery is a lightweight, "write less, do more", JavaScript library.
<br>
The purpose of jQuery is to make it much easier to use JavaScript on your website.<br>
There's thousands of Javascript libraries out there, but none of these libraries have been used or downloaded as often as jQuery.<br>
The jQuery library contains the following features:
<ol><li>
HTML/DOM manipulation<li>
CSS manipulation<li>
HTML event methods<li>
Effects and animations<li>
AJAX<li>
Utilities</ol>

### Working of JQuery
jQuery allows you to do is take a line of code, say this,

```JavaScript
document.querySelector("h1")
```

if we were to use the jQuery library, then we can get rid of all of that and simply say
```JavaScript
jQuery("h1")
```
if you want to be even shorter, the shorthand way to write jQuery is simply a dollar sign.
```JavaScript
$("h1")
```
So  $("h1") does exactly the same as
```JavaScript
document.querySelector("h1")
```
<hr>

## How to incorporate JQuery into websites
Add this script tag to your html document for using JQuery.

```HTML
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>

```

Changing color of element

```JavaScript
$("h1").css("color","red");
// after loaded the page
$(document).ready(function(){
    $("h1").css("color","red");
}); 
```

## How minification works to reduce file size
<a href="https://minifier.org/">https://minifier.org/</a> is a way to convert our JavaScript or CSS code to minfied version.

# Selecting elements with JQuery

for example if we wanted the h1 then we can simply say 
```JavaScript
querySelector("h1")
```

Now if we were to write this in jQuery then we can remove all of this part and instead only have the dollar sign which is short for jQuery.
```JavaScript
$("h1");
```

# Manipulating Styles with JQuery
we can manipulate the CSS style of a selected element by simply using the .css method from jQuery.

for example we can select our h1 and we can say .css, and we can add the CSS property that we want to change, so for example the color.
And our second input is the value for that property.
```JavaScript
$("h1").css("color":"green");
```
we can get the current value of the CSS property by simply having the name of the property in some quotation marks as a string inside the method.
```JavaScript
var colorOfElement = $("h1").css("color");
console.log(colorOfElement);
```
We can do in a different way<br>
-- define styles for a class in css file
suppose the classname  is btn, that you used in your css file.
```JavaScript
$("h1").addClass("btn");
// Removing class
$("h1").removeClass("btn");
// we can add multiple classes 
$("h1").addClass("btn marg");
// Query for a class
$("h1").hasClass("class-name");
```

# Manipulating text with JQuery
there's two ways of going about this. One is you can simply, say, select an element, then .text, and inside the parentheses you'll add the new text that you want it to say,
```JavaScript
// in javascript we use innerHTML
$("h1").text("Good Bye"); // this will not add html
// to add html code also 
$("h1").html("<a href="">Hello</a>");
```
# Manipulating Attributes with JQuery


Finding an attribute
```JavaScript
$("img").attr("src");
// Changing an attribute
$("a").attr("href",""link");
```
# Adding Event Listeners using JQuery
we're going to wrap the thing that we're looking for which is the h1, and now all we need to do is say .click, and that will add an event listener and call this callback function once it detects a click.
```JavaScript
$("h1").click(function(){
    $("h1").css("color","red");
})
```
if we wanted to add an event listener to all five buttons we had to write a for loop if we only had Javascript in our toolset. So we had to write something like
```JavaScript
for(var i=0;i<5;i++){
    document.querySelectorAll("button")[i].addEventListener("click",function(){
        document.querySelectorAll(".loc").style.color = "purple";
    })
    
}
```
How to do this with JQuery--

```JavaScript
$("button").click(function(){
    $("h1").css("color","purple");
})
```

# Adding and removing elements using JQuery
We can actually use jQuery to add new elements on the fly.
#### **Before**
If I selected my h1 and I decided to add a new button before the h1, then I simply use the **before()** method.
And inside these parentheses I can put down the HTML that I want to add before our h1.

```JavaScript
$("h1").before("<button>Submit</button>");
```
So that means that we can create HTML elements at any time we wish just by using code.But there're just a few ways for this.
<br>

#### **After**
Now there's also **after()** which creates our HTML elements after the element that we've selected.
```JavaScript
$("h1").after("<h2>Hello</h2>");
```
#### **Prepend and Append**
There's also **prepend()** and **append()**, and the difference between, say, 
prepend and before is that prepend will add your new HTML element into the item that you've selected just after the opening tag.


```JavaScript
$("h1").prepend();
```
Using append element will tag just after the content of selected element but before the end of the element.
```JavaScript
$("h1").append();
```
#### **remove()**
removing elements is also simple using remove method.
```JavaScript
$("h1").remove();
```

# Website Animations using JQuery

#### **hide()**
we can hide any element using hide method.

```JavaScript
$("button").hide();
```
#### **show()**
to show hided content
```JavaScript
$("button").show();
```
#### **toggle()**
If we want to toggle hide and show
```JavaScript
$("h1").toggle();
```
#### **fadeOut()**
we can use fadeOut() instead of toggle, if we want this a little bit more progressive.
it reduces the opacity of the element then hide it.
```JavaScript
$("h1").fadeOut();
```
#### **fadeIn()**
relative of fadeOut() for showing up the faded element.
```JavaScript
$("h1").fadeIn();
```

#### **fadeToggle()**
fadeout and fadein by one method

```JavaScript
$("h1").fadeToggle();
```
#### **slideUp(), slideDown(), slideToggle()**
collapse and uncollapse


```JavaScript
$("h1").slideUp();
$("h1").slideDown();
$("h1").slideToggle(); // For both
```
### **animate()** 
Allows you to define custom css that you want to gradually animate towards.
```JavaScript
$("h1").animate({opacity: 0.5})// we can't properties that not take number values like color
```
### Example of these methods

#### HTML---
```HTML
<div>
    <h1>Hello</h1>
</div>
<button class="hide">Hide</button>
<button class="show">Show</button>
<button class="toggle">Toggle</button>
<button class="fadeout">FadeOut</button>
<button class="fadein">Fade in</button>
<button class="fadetoggle">Fade Toggle</button>
<button class="slideup">Slide UP</button>
<button class="slidedown">Slide Down</button>
<button class="slidetoggle">Slide toggle</button>
<button class="animate">Animate</button>
```
#### JQuery----

```JavaScript
$(".hide").on("click",()=>{
    $("div h1").hide();
})
$(".show").on("click",()=>{
    $("div h1").show();
})
$(".toggle").on("click",()=>{
    $("div h1").toggle();
})
$(".fadeout").on("click",()=>{
    $("div h1").fadeOut();
})
$(".fadein").on("click",()=>{
    $("div h1").fadeIn();
})
$(".fadetoggle").on("click",()=>{
    $("div h1").fadeToggle();
})
$(".slideup").on("click",()=>{
    $("div h1").slideUp();
})
$(".slidedown").on("click",()=>{
    $("div h1").slideDown();
})
$(".slidetoggle").on("click",()=>{
    $("div h1").slideToggle();
})
$(".animate").on("click",()=>{
    $("div h1").animate({opacity: 0.5})
})
```

### How to use these methods to animate something
we can use these methods in chain like this
```JavaScript
$("div h1").slideUp().slideDown().animate({opacity: 0.5}).animate({opacity:0}).animate({opacity:0.5}).animate({opacity:1});
```

