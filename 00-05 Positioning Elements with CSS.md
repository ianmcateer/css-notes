allows us to change position of elements on our website

Why Positioning Will Improve Our Website
----------------------------------------

could change posotion of nav bar to make it sticky and sticky

on packages page dont have background image and plus plan and add a badge to it so our users see this is the recommended plan

Understanding Posotiion: The Theory
-----------------------------------

![Screen Shot 2019-11-20 at 1.37.56 pm.png](resources/07210141979A33584C0F0E369B841F88.png)

these elemeents are following the document flow- is there already some property applied already to make sure this document flow is followed? yes the posotiion is applied by default with a value of static

```css
position: static
```

but what if want to place div somewhere else liek the upper right

![Screen Shot 2019-11-20 at 1.39.37 pm.png](resources/FD0F39D6057DA77E26A1F364979C9E1A.png)

have to specify either absolute, relative or fixed- sticky is a new value for this property

![Screen Shot 2019-11-20 at 1.56.07 pm.png](resources/6B38E2F1D717D0E72EC36D74A9C665DA.png)

Change the position:

once we set position to a value other than static we have 4 different options:

1. top
2. bottom
3. left
4. Right

with these properties you change your element from its original position in the document flow

top could mean move top or position from the top of the viewport, html or body

Working with the Fixed Value
----------------------------

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <link rel="stylesheet" href="main.css">
        <title>Position</title>
    </head>
    <body>
        <div class="parent">
            <div class="child-1">Navigation Bar</div>
            <div class="child-2">Background Image</div>
            <div class="child-3">Features</div>
        </div>
    </body>
</html>
```

```css
html {
    background: #b3b3b3;
    padding: 15px;
    border: 5px solid white;
    margin: 15px;
    height: 2000px;
}

body {
    background: #fa923f;
    padding: 20px;
    border: 5px solid black;
    margin: 0;
  }
  
.parent {
    background: white;
    padding: 20px;
    border: 5px solid black;
    margin: 0;
  }
  
.parent div {
    background: rgb(105, 105, 109);
    color: white;
    padding: 10px;
    border: 5px solid black;
    margin: 10px;
}
```



```css
.parent .child-1 {
    top: 100px;
}
```

nothing happens- all the positioning changes can only happen if we use a posotiin other than static

```css
.parent .child-1 {
    position: fixed;
}
```

we can see that the posootion already canged

1- the width decreased significantly

2- the element now is basically not existing now for the other elements- it is taken out of the document flow- means for all the other elements this nav element is non existing

![Screen Shot 2019-11-20 at 2.23.45 pm.png](resources/32FDAF5226242BE04EC4C295BAEC0417.png)

did we create an inline element here?? if try change the width on an inlien element it should have no effect

but in this case you can set the width- it behaves like an inline block element

```css
.parent .child-1 {
    position: fixed;
    width: 400px;
    top: 100px;
}
```

the element moved down a bit

![Screen Shot 2019-11-20 at 2.29.01 pm.png](resources/CBBBAC9424DD11F20B6CF55E1863529E.png)

but top from where? if set it to 0 should see

![Screen Shot 2019-11-20 at 2.29.51 pm.png](resources/676067C6D2C2548AFB62957C72F1CC86.png)

remove the margin as well and it becomes evident

![Screen Shot 2019-11-20 at 2.31.14 pm.png](resources/E56214FC5F3A3E97724DD43F2594ED02.png)

nav bar is not dependend on the html element but basically has the viewport as the positiioning context

```css
.parent .child-1 {
    position: fixed;
    width: 400px;
    top: 0;
    margin: 0;
    width: 100%;
}
```

but problem is border is kind of located outside of our viewport

![Screen Shot 2019-11-20 at 2.34.24 pm.png](resources/F38F2E21F719F0F1E9950738C081E24A.png)

```css
.parent .child-1 {
    position: fixed;
    width: 400px;
    top: 0;
    margin: 0;
    width: 100%;
    /*add box sizing border box*/
    box-sizing: border-box;
}
```

Lets Add it to Our Website
--------------------------

```html
 <header class="main-header">
        <div>
            <a href="index.html" class="main-header__brand">
                uHost
            </a>
        </div>
        <nav class="main-nav">
            <ul class="main-nav__items">
                <li class="main-nav__item">
                    <a href="packages/index.html">Packages</a>
                </li>
                <li class="main-nav__item">
                    <a href="customers/index.html">Customers</a>
                </li>
                <li class="main-nav__item main-nav__item--cta">
                    <a href="start-hosting/index.html">Start Hosting</a>
                </li>
            </ul>
        </nav>
    </header>
```

```css
.main-header {
    width: 100%;
    position: fixed;
    padding: 8px 16px;
    background: #2ddf5c;
}
```

generally seems to work fine- why not add top: 0 ? as soon as you add a margin to a html element or the body element or any parent eleement of ehader then have to add top: 0 and left :0 in case want to stick to left top of the page

![Screen Shot 2019-11-20 at 3.05.41 pm.png](resources/8377CC43A7E38B75B8F90CD9A27DF268.png)

Using Position to add a Background Image to the Packages Page
-------------------------------------------------------------

going to add a new div with class background

```html
<header class="background">
    <div>
        <a href="index.html" class="main-header__brand">
            uHost
        </a>
    </div>
    <div class="background"></div>
    <nav class="main-nav">
        <ul class="main-nav__items">
            <li class="main-nav__item">
                <a href="packages/index.html">Packages</a>
            </li>
            <li class="main-nav__item">
                <a href="customers/index.html">Customers</a>
            </li>
            <li class="main-nav__item main-nav__item--cta">
                <a href="start-hosting/index.html">Start Hosting</a>
            </li>
        </ul>
    </nav>
</header>
```

create new images folder and add plans-background.jpg

```css
.background {
    background: url("../imagesplans-background.jpg");
}
```

not alot changed

```css
.background {
    background: url("../imagesplans-background.jpg");
    width: 100%;
    height: 100%;
}
```

this also doesnt work

this one below works

```css
.background {
    background: url("../imagesplans-background.jpg");
    width: 500px;
    height: 500px;
}
```

want the image behind the content of the page

```css
.background {
    background: url("../imagesplans-background.jpg");
    width: 500px;
    height: 500px;
    position: fixed;
}
```

![Screen Shot 2019-11-25 at 11.18.46 am.png](resources/76B7086ED19EF4B3F6E699B42E811728.png)

can change the height and width back to 100% now

```css
.background {
    background: url("../imagesplans-background.jpg");
    width: 100%;
    height: 100%;
    position: fixed;
}
```

![Screen Shot 2019-11-25 at 11.20.13 am.png](resources/89551721EE454F0B1FC5328B4844B2B5.png)

Understanding the Z-Index
-------------------------

we also need to posiiton elements to position against the z-index- can do that in css

z-index by default is auto. the auto value is equal to zero

adding a z-index to elemenets not in position: static z-index has no effect

```css
.background {
    background: url("../imagesplans-background.jpg");
    width: 100%;
    height: 100%;
    position: fixed;
    z-index: -1;
}
```

![Screen Shot 2019-11-25 at 11.25.11 am.png](resources/76FB3D6DDA579C45B0AC6C8945D4741F.png)

if two elements position:fixed and no-z index set then the order in html will matter- the html element that comes last will appear above the first element

Adding a Badge to Our Package
-----------------------------

```html
 <main>
        <section class="package" id="plus">
            <a href="#">
                <h1 class="package__title">Our PLUS Plan</h1>
                <h1 class="package__badge">RECOMMENDED</h1>
                <h2 class="package__subtitle">The most popular choice of our customers.</h2>
                <p class="package__info">Benefit from increased storage and faster support to ensure that your mission-critical data and applications
                    are always available!</p>
            </a>
        </section>
        <section class="package" id="free">
            <a href="#">
                <h1 class="package__title">Our FREE Plan</h1>
                <h2 class="package__subtitle">An extremely solid start into our hosting world.</h2>
                <p class="package__info">Get started immediately at zero cost!</p>
            </a>
        </section>
        <section class="package" id="premium">
            <a href="#">
                <h1 class="package__title">Our PREMIUM Plan</h1>
                <h2 class="package__subtitle">All your enterprise needs. Instant support, guaranteed uptime. </h2>
                <p class="package__info">The best solution for small to large enterprises. Because hosting shouldn't be in the way!</p>
            </a>
        </section>
    </main>
```

```css
.package__badge {
    position: fixed;
}
```

now taken out of the document flow

![Screen Shot 2019-11-25 at 11.49.33 am.png](resources/65E6C1116F6C85D3FC5805FCA72A4322.png)

```css
.package__badge {
    position: fixed;
    top: 0;
    left: 0;
}
```

now position left to viewport

```css
.package__badge {
    position: fixed;
    top: 50px;
    left: 400px;
    margin: 20px;
}
```

but htis is now alot of trial and error and positon: fixed is related to the viewport

not the behaviour we want to have- need another value

we can change position fixed to absolute

```css
.package__badge {
    position: absolute;
    top: 50px;
    left: 400px;
    margin: 20px;
}
```

this position abolsute also takes the element out of the document flow

the positioning context is now based on two cases- if none of the parents have posiiton applied then the positioning context is simply the html element

if we have any posiiton ancestors then the closes element with position applied is the positioning context for this element

```css
.package__badge {
    position: absolute;
    top: 0;
    left: 400px;
    margin: 20px;
}
```

see that it is stuck to the html element

can applied relative to parent element

```css
.package {
    position: relative;
}

.package__badge {
    position: absolute;
    top: 0;
    left: 400px;
    margin: 20px;
}
```

the relative value doesnt take out elements out of the document flow - the posiitoning context now changed to the closest ancestor with a position property applied

fixed and absolute are similar but for fixed the position context is always the viewport. with absolute it depends. if no parent element has position the positioning context is the html. if parent has position applied then positioning context will be set to the parent element

```css
.package {
    position: relative;
}

.package__badge {
    position: absolute;
    top: 0;
    right: 0;
    margin: 20px;
    font-size: 12px;
    color: white;
    background: #ff5454;
    padding: 8px;
}
```

![Screen Shot 2019-11-25 at 1.35.05 pm.png](resources/7138C5B48323A33699E26C8E671ED1AA.png)

Diving Depper Into Relative Positioning
---------------------------------------

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <link rel="stylesheet" href="main.css">
        <title>Position</title>
    </head>
    <body>
        <div class="parent">
            <div class="child-1">Navigation Bar</div>
            <div class="child-2">Background Image</div>
            <div class="child-3">Features</div>
        </div>
    </body>
</html>
```

```css
html {
    background: #b3b3b3;
    padding: 15px;
    border: 5px solid white;
    margin: 15px;
    height: 2000px;
}

body {
    background: #fa923f;
    padding: 20px;
    border: 5px solid black;
    margin: 0;
  }
  
.parent {
    background: white;
    padding: 20px;
    border: 5px solid black;
    margin: 0;
  }
  
.parent div {
    background: rgb(105, 105, 109);
    color: white;
    padding: 10px;
    border: 5px solid black;
    margin: 10px;
}
```

![Screen Shot 2019-11-25 at 1.38.05 pm.png](resources/037BA740AD5D773CC27C0EB47B686AA1.png)

```css
.parent .child-1 {
    position: relative;
}
```

the element stays and behaves the same way- we can change the posiitoning context of other elements

```css
.parent .child-1 {
    position: relative;
    top: 50px;
    left: 50px;
}
```

for relative positioning the element is not taken out of the document flow - the positioning contet is the elmenet itself- we are moving it according to its initial position

can even make it leave its parent

Working with Overflow and Relative Positioning
----------------------------------------------

to avoid moving element out of parent

```css
.parent {
    overflow: hidden;
}
```

will hide the element once it is outside the parent

if apply overflow: hidden to body will simply be passed onto the html element - so not on body element really

cant change htis behaviour- can add it to both html and body element and it will work

![Screen Shot 2019-11-25 at 2.07.04 pm.png](resources/7567EBFE61C0BA50174277F054A5ADA0.png)

Introducing Sticky Positioning 
-------------------------------

![Screen Shot 2019-11-25 at 2.08.01 pm.png](resources/535E8F6095CA6BA5360A769022FFB766.png)

sticky is a combo of relative and fixed- as soon as add top property behaves like a fixed element once we reach a certain border

the border is reached depending on our posiiton of the viewport

Understanding the Stacking Context
----------------------------------

we set all parent elements with posiiton fixed- each element has its own stacking context

for the elements inside the parent elemenent the z-index will only have an impact inside the parent element but not outside

