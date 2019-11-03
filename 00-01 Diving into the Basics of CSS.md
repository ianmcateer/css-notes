this is the starting code...

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>uHost</title>
    <link rel="shortcut icon" href="favicon.png">
</head>

<body>
    <main>
        <section>
            <h1>Get the freedom you deserve.</h1>
        </section>
    </main>
</body>

</html>
```

3 ways adding css
-----------------

1. inline styling: by adding the style attribute to the tag- can add a css declaration inside the style string- you define what you want to style and how
  1. the what is the property
  2. the how is the value- the value depends on the property

```html
<section style="background: red"></section>
```

this approach is not recommended- bc does not scale well

2\. .css file

in head seciton can add a special style tag

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>uHost</title>
    <link rel="shortcut icon" href="favicon.png">
    <style>
        section {
            background: red;
        }
    </style>
</head>
```

add a selector

3\. using external style sheet

in example calling it main.css

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>uHost</title>
    <link rel="shortcut icon" href="favicon.png">
    <link href="main.css" rel="stylesheet">
</head>
```

Importing Google Fonts
----------------------

Index.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>uHost</title>
    <link rel="shortcut icon" href="favicon.png">
    <link href="https://fonts.googleapis.com/css?family=Anton" rel="stylesheet">
    <link rel="stylesheet" href="main.css">
</head>

<body>
    <main>
        <section id="product-overview">
            <h1>Get the freedom you deserve.</h1>
        </section>
        <section id="plans">
            <h1 class="section-title">Choose Your Plan</h1>
        </section>
    </main>
</body>

</html>
```

main.css

```css
section {
    background: red;
}

h1 {
    /* this changes color of the text*/
    color: white;
    font-family: 'Anton' , sans-serif;
}

```

Understanding Selectors
-----------------------

element or tag selections

```css
h1 {
    color: red;
}
```

Classes- can define a style and apply to all elements that have that class

```html
<h1 class="blog-post">Our header</h1>
```

```html
.blog-post {
    color: red;
}
```

universal

with the star selector you style every element on your page- rarely used

```html
* {
    color: red;
}
```

id selectors

set style to one specific element

```html
#main-title {
 color: red;
}
```

attributes

select html elements by the attribute they have and can select multiple elements

```html
<button disabled>
    Click
</button>
```

this applies to all elements that have a disabled attribute

```html
[disabled] {
    color: red;
}
```

going to give id’s to our sections- id’s also allow you to allow to add a hashtag at the end of url and browser will jump down to that element on the page

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>uHost</title>
    <link rel="shortcut icon" href="favicon.png">
    <link href="https://fonts.googleapis.com/css?family=Anton" rel="stylesheet">
    <link rel="stylesheet" href="main.css">
</head>

<body>
    <main>
        <section id="product-overview">
            <h1>Get the freedom you deserve.</h1>
        </section>
        <section id="plans">
            <h1 class="section-title">Choose Your Plan</h1>
        </section>
    </main>
</body>

</html>
```

```css
#product-overview {
    background: red;
}

h1 {
    /* this changes color of the text*/
    color: white;
    font-family: 'Anton' , sans-serif;
}

/*classes can add to more than one element*/
.section-title {
    color: #2ddf5c;
}
```

Specificity
-----------

we set the h1 to have a white color but then we set the section-title to a green color. the class seems to override the h1 style. different rules seem to have differnt priorities

in developer tools - the top style in the dev tools is the highest priority - also browser defaults that have lowest priority

cascading means multiple rules can be applied ot same element- can elad to conflicts - css uses specificty to resolve conflicts

1. inline styles have highest specifity
2. id selectors
3. :class, :pseudo-class and [attribute] selectors are on same level
4. \<Tag\> and pseudo-selectors have the lowest priority. actually \* does but rarely sues that

Inheritance
-----------

```css
body {
    font-family: 'Montserrat';
}

#product-overview {
    background: red;
}

h1 {
    /* this changes color of the text*/
    color: white;
    font-family: 'Anton' , sans-serif;
}

/*classes can add to more than one element*/
.section-title {
    color: #2ddf5c;
}
```









