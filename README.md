# Intro to CSS

While HTML is the fundamental structure of every web page, it can be visually unappealing on its own. 

Cascading Style Sheets or CSS is a language web developers use to style the HTML content on a web page. If you’re interested in modifying colors, font types, font sizes, images, element positioning, and more, CSS is the tool for the job!

Here's the starting HTML code for our CSS class:

```
<!DOCTYPE html>
<html>
  <head>
    <link href='https://fonts.googleapis.com/css?family=Roboto:400,300,500,100' rel='stylesheet' type='text/css'>
    <link href="style.css" rel="stylesheet">
  </head>
  <body>
    <div class="header">
      <div class="container">
        <h1>Polygon Bootcamp CSS tutorial</h1>
        <p>Learn how to style HTML websites</p>
        <a class="btn" href="#">Learn More</a>
      </div>
    </div>

    <div class="nav">
      <div class="container">
        <ul>
          <li>Register</li>
          <li>Schedule</li>
          <li>Sponsors</li>
          <li>About</li>
          <li>Contact</li>
        </ul>
      </div>
    </div>

    <div class="main">
      <div class="container">
        <img src="https://content.codecademy.com/projects/innovation-cloud/cloud.svg" height="128" width="196">
        <h2>The CSS Styling Conference</h2>
        <p>Connect with the best minds across a wide range of industries to share ideas and brainstorm new solutions to challenging problems.</p>
        <p>Hear industry leaders talk about what worked (and what didn't) so that you can save time on your most challenging projects.</p>
        <p>Learn about the latest research and technologies that you can use immediately to invent the future.</p>
      </div>
    </div>

    <div class="jumbotron">
      <div class="container">
        <h2>Stay Connected</h2>
        <p>Receive weekly insights from industry insiders.</p>
        <a class="btn" href="#">Join</a>
      </div>
    </div>

    <div class="footer">
      <div class="container">
        <p>&copy; Polygon CSS Tutorial</p>
      </div>
    </div>
  </body>
</html>
```


Now open a new text document and name it style.css:

style.css:

```
html, body {
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Roboto', sans-serif;
  font-weight: 100;
}

.container {
  margin: 0 auto;
  max-width: 940px; 
  padding: 0 10px;
}

.header {
  background: url(https://content.codecademy.com/projects/innovation-cloud/bg.jpg) no-repeat center center; 
  background-size: cover;
  height: 800px;
  text-align: center; 
}

.header .container {
  position: relative;
  top: 200px;
}

.header h1 {
  color: #fff;
  line-height: 100px; 
  font-size: 80px;
  margin-top: 0;
  margin-bottom: 80px;
  text-transform: uppercase; 
}

@media (min-width:850px) {
  .header h1 {
    font-size: 120px;
  }
}

.header p {
  color: #fff;
  font-weight: 500;
  letter-spacing: 8px;
  margin-bottom: 40px;
  margin-top: 0;
  text-transform: uppercase; 
}

.btn {
  color: #fff;
  background: #000;
  padding: 10px 40px;
  text-decoration: none; 
  transition: background .5s; 
}

.nav { 
  background: #000;
  height: 80px; 
  width: 100%;
}

.nav ul {
  height: 80px;
  list-style: none;
  margin: 0 auto; 
  padding: 0;
}

.nav ul li {
  color: #fff;
  display: inline-block; 
  height: 80px;
  line-height: 80px; 
  list-style: none;
  padding: 0 10px;
  transition: background .5s; 
}

.btn:hover, .nav ul li:hover {
  background: #117bff;
  cursor: pointer; 
  transition: background .5s;  
}

.main .container {
  margin: 80px auto;
}

.main img {
  float: left;
  margin: 50px 80px 50px 0;
}

.jumbotron {
  background: url(https://content.codecademy.com/projects/innovation-cloud/jumbotron_bg.jpg) center center;
  background-size: cover;
  height: 600px; 
}

.jumbotron .container {
  position: relative;
  top: 220px;
}

.jumbotron h2 {
  color: #fff;
  text-align: right; 
}

.jumbotron p {
  color: #fff; 
  text-align: right; 
}

.jumbotron .btn {
  margin: 10px 0 0;
  float: right; 
}

.footer { 
  background: #000;
  height: 80px; 
  padding-bottom: 50px;
}

.footer p { 
  color: #fff;
  font-size: 14px;  
  height: 80px; 
  line-height: 80px;
  margin: 0;  
}

@media (max-width: 500px) {
  .header h1 {
    font-size: 50px;
    line-height: 64px;
  }

  .main, .jumbotron {
    padding: 0 30px;
  }

  .main img {
    width: 100%;
  }
}
```

Now add this line to the head element of index.txt:

```
<link href="style.css" rel="stylesheet">
```

Save and see the result of your index.html.


# CSS Anatomy

The diagram on the right shows two different methods, or syntaxes, for writing CSS code. The first syntax shows CSS applies as a ruleset, while the second shows it written as an inline style. Two different methods of writing CSS may seem a bit intimidating at first, but it’s not as bad as it looks!

![Screenshot_139](https://user-images.githubusercontent.com/29931071/199235241-37ec8ad0-9e94-4831-b154-3352eef4c5ce.png)


Ruleset Terms:

- Selector—The beginning of the ruleset used to target the element that will be styled.
- Declaration Block—The code in-between (and including) the curly braces ({ }) that contains the CSS declaration(s).
- Declaration—The group name for a property and value pair that applies a style to the selected element.
- Property—The first part of the declaration that signifies what visual characteristic of the element is to be modified.
- Value—The second part of the declaration that signifies the value of the property.

# External Stylesheet
Developers avoid mixing code by storing HTML and CSS code in separate files (HTML files contain only HTML code, and CSS files contain only CSS code).

You can create an external stylesheet by using the .css file name extension, like so: style.css

With an external stylesheet, you can write all the CSS code needed to style a page without sacrificing the readability and maintainability of your HTML file.

# Linking the CSS File

Perfect! We successfully separated structure (HTML) from styling (CSS), but the web page still looks bland. Why?

When HTML and CSS codes are in separate files, the files must be linked. Otherwise, the HTML file won’t be able to locate the CSS code, and the styling will not be applied.

You can use the ```<link>``` element to link HTML and CSS files together. The ```<link>``` element must be placed within the head of the HTML file. It is a self-closing tag and requires the following attributes:

- href — like the anchor element, the value of this attribute must be the address, or path, to the CSS file.
- rel — this attribute describes the relationship between the HTML file and the CSS file. Because you are linking to a stylesheet, the value should be set to stylesheet.

When linking an HTML file and a CSS file together, the <link> element will look like the following:

```
<link href='https://www.codecademy.com/stylesheets/style.css' rel='stylesheet'>
```

If the CSS file is stored in the same directory as your HTML file, then you can specify a relative path instead of a URL, like so:

```
<link href='./style.css' rel='stylesheet'>
```



# Selectors

## Type

Remember that declarations are a fundamental part of CSS because they apply a style to a selected element. 

But how do you decide which elements will get the style? With a selector.

A selector is used to target the specific HTML element(s) to be styled by the declaration. One selector you may already be familiar with is the type selector. Just like its name suggests, the type selector matches the type of the element in the HTML document.

## Class work

For this class, here's the index.txt that we will be styling:

Index.txt:

```
<!DOCTYPE html>
<html>

<head>
  <title>Vacation World</title>
  <link href='style.css' rel='stylesheet'>
</head>

<body>
  <img src='https://content.codecademy.com/courses/freelance-1/unit-2/explorer.jpeg' />
  <h1 class='title'>Top Vacation Spots</h1>
  <h5>By: Stacy Gray</h5>
  <h6>Published: 2 Days Ago</h6>

  <p>The world is full of fascinating places. Planning the perfect vacation involves packing up, leaving home, and experiencing something new.</p>

  <h2 class='destination'>1. Florence, Italy</h2>
  <div class='description'>A city-size shrine to the Renaissance, Florence offers frescoes, sculptures, churches, palaces, and other monuments from the richest cultural flowering the world has known. Names from its dazzling historical past; Dante, Michelangelo, Galileo, Machiavelliare are some of the most resonant of the medieval age. <a href='https://www.nationalgeographic.com/travel/destination/florence' target='_blank'>Learn More</a>.
    <h5>Top Attractions</h5>
    <ul>
      <li>Museums</li>
      <li>Bike Tours</li>
      <li>Historical Monuments</li>
    </ul>
  </div>

  <h2 class='destination'>2. Beijing, China</h2>
  <div class='description'>A city in the midst of reinventing itself and continuing to build on the success of the 2008 Summer Olympics, Beijing is a place of frenzied construction. New housing, new roads, and new sports venues seem to spring up overnight. At the same time, the capital of the Peoples Republic of China remains an epicenter of tradition, with the treasures of nearly 2,000 years as the imperial capital still on view in the famed Forbidden City and in the luxuriant pavilions and gardens of the Summer Palace.
    <a href='https://www.nationalgeographic.com/travel/destination/beijing' target='_blank'>Learn More</a>.
    <h5>Top Attractions</h5>
    <ul>
      <li>Biking</li>
      <li>Historical Sites</li>
      <li>Restaurants and Dining</li>
    </ul>
  </div>

  <h2 class='destination'>3. Seoul, South Korea</h2>
  <div class='description'>The Korean capital is a city of contrasts. Fourteenth-century city gates squat in the shadow of 21st-century skyscrapers, while the broad Han River is back-dropped by granite mountains rising in the city center complete with alpine highways speeding around their contours and temples nestling among their crags. Fashionable, gadget-laden youths battle for sidewalk space with fortune-tellers and peddlers, while tiny neighborhoods of traditional cottages contrast with endless ranks of identical apartments.
    <a href='https://www.nationalgeographic.com/travel/destination/seoul' target='_blank'>Learn More</a>.
    <h5>Top Attractions</h5>
    <ul>
      <li>Parasailing</li>
      <li>Segway Tours</li>
      <li>Spas and Resorts</li>
    </ul>
  </div>

  <h2> More Destinations </h2>
  <ul>
    <li><h4 class='destination'>Jackson Hole, Wyoming</h4></li>
    <li><h4 class='destination'>Cape Town, South Africa</h4></li>
    <li><h4 class='destination'>La Paz, Bolivia</h4></li>
  </ul>

  <p>&mdash;Best of luck with your travels, and be sure to send pictures and stories. We'd love to hear them!</p>


</body>

</html>
```

Now create a style.css file, add a ruleset using the type selector to target all ```<h1>``` elements. 
  
Give it a color: maroon

  
Solution: style.css =
```
p {
  color: green;
}

h1 {
  color: maroon;
}
```
  
## Universal
  
You learned how the type selector selects all elements of a given type. Well, the universal selector selects all elements of any type.
  
Targeting all of the elements on the page has a few specific use cases, such as resetting default browser styling, or selecting all children of a parent element.
  
The universal selector uses the * character in the same place where you specified the type selector in a ruleset, like so:
  
```
* { 
  font-family: Verdana;
}
```
  
In the code above, every text element on the page will have its font changed to Verdana.
  
## Class work
  
To see how the universal selector targets all elements on a page, copy the rule below and paste it on the first line of style.css
  
```
* {
  border: 1px solid red;
}
```
  
## Class
  
CSS is not limited to selecting elements by their type. As you know, HTML elements can also have attributes. When working with HTML and CSS a class attribute is one of the most common ways to select an element.

For example, consider the following HTML:
  
```
<p class='brand'>Sole Shoe Company</p>
```
  
The paragraph element in the example above has a class attribute within the opening tag of the ```<p>``` element. The class attribute is set to 'brand'. To select this element using CSS, we can create a ruleset with a class selector of ```.brand```.
  
```
.brand {
 
}
```
  
To select an HTML element by its class using CSS, a period (.) must be prepended to the class’s name. In the example above, the class is brand, so the CSS selector for it is .brand.
  
## Class work
  
On line 11 of index.html there is an ```<h1>``` element with the class title.

Now, open style.css. use the class selector to create a ruleset that selects that HTML element using the class title.
  
Inside the curly braces of the .title selector, add the declaration:
```
color: teal;
```
  
## ID
  
Oftentimes it’s important to select a single element with CSS to give it its own unique style. If an HTML element needs to be styled uniquely, we can give it an ID using the id attribute.
  
```
<h1 id='large-title'> ... </h1>
```
  
In contrast to class which accepts multiple values, and can be used broadly throughout an HTML document, an element’s id can only have a single value, and only be used once per page.
  
To select an element’s ID with CSS, we prepend the id name with a number sign ```(#)```. For instance, if we wanted to select the HTML element in the example above, it would look like this:
  
```
#large-title {
 
}
```
  
## Class work
  
On line 11 of index.html, inside the h1 opening tag and after the class attribute, add an id with the value article-title.
  
```
<h1 class='title'>Top Vacation Spots id='article-title'</h1>
```
  
Navigate to style.css. Add a ruleset using the ID selector to target the article-title ID. Inside of its curly braces, write the declaration:

```
font-family: cursive;
```
  
style.css:

```
#article-title {
  font-family: cursive;
}
```
  
## Attribute
  
You may remember that some HTML elements use attributes to add extra detail or functionality to the element. Some familiar attributes may be href and src, but there are many more—including class and id!

The attribute selector can be used to target HTML elements that already contain attributes. Elements of the same type can be targeted differently by their attribute or attribute value. This alleviates the need to add new code, like the class or id attributes.

Attributes can be selected similarly to types, classes, and IDs.

```
[href]{
   color: magenta;
}
```
  
The most basic syntax is an attribute surrounded by square brackets. In the above example: [href] would target all elements with an href attribute and set the color to magenta.
  
And it can get more granular from there by adding type and/or attribute values. One way is by using type[attribute*=value]
  
For example:
  
```
<img src='/images/seasons/cold/winter.jpg'>
<img src='/images/seasons/warm/summer.jpg'>
```
  
You can style it this way:
  
```
img[src*='winter'] {
  height: 50px;
}
 
img[src*='summer'] {
  height: 100px;
}
```
  
## Class work
  
To use the attribute selector to select the <a> element with an href attribute value containing ‘florence’, add the following code to style.css:
  
```  
a[href*='florence'] {
  color: lightgreen;
}
```
  
  
## Pseudo-class
  
You may have observed how the appearance of certain elements can change, or be in a different state, after certain user interactions. For instance:

- When you click on an <input> element, and a blue border is added showing that it is in focus.
- When you click on a blue <a> link to visit to another page, but when you return the link’s text is purple.
- When you’re filling out a form and the submit button is grayed out and disabled. But when all of the fields have been filled out, the button has color showing that it’s active.
  
These are all examples of pseudo-class selectors in action! In fact, ```:focus```, ```:visited```, ```:disabled```, and ```:active``` are all pseudo-classes. Factors such as user interaction, site navigation, and position in the document tree can all give elements a different state with pseudo-class.

A pseudo-class can be attached to any selector. It is always written as a colon : followed by a name. For example p:hover.
  
```
p:hover {
  background-color: lime;
}
```
  
In the above code, whenever the mouse hovers over a paragraph element, that paragraph will have a lime-colored background.


## Class work

Add a ruleset to the end of style.css that selects the <a> elements on the page. Leave the declaration block empty for now.


Next, add a :hover pseudo-class to the a selector you just created.

Lastly, set the text color to dark orange by adding the following CSS declaration inside the declaration block:

```
color: darkorange;
```

code:

```
 a:hover {
    color:darkorange;
  }
```

## Classes and IDs

CSS can select HTML elements by their type, class, and ID. CSS classes and IDs have different purposes, which can affect which one you use to style HTML elements.

CSS classes are meant to be reused over many elements. By writing CSS classes, you can style elements in a variety of ways by mixing classes. For instance, imagine a page with two headlines. One headline needs to be bold and blue, and the other needs to be bold and green. Instead of writing separate CSS rules for each headline that repeat each other’s code, it’s better to write a .bold CSS rule, a .green CSS rule, and a .blue CSS rule. Then you can give one headline the bold green classes, and the other the bold blue classes.

## Class work

1 In index.html, there are four <h2> elements. Give each of them a class of heading-background.

2 On line 13 of index.html, there’s an <h6> element that displays the time the article on the page was published.

Add an id attribute to the <h6>, and give it a value of publish-time.

3 Then, in style.css, create a ruleset targeting the new heading-background class, and give it a declaration of:

```
background-color: aqua;
```

4 Finally, in style.css, create another ruleset using the publish-time ID selector. Add the declaration:

```
color: gray;
```

Since ID’s are single-use, this element now has a unique ID that can’t be used again in this document!

Solution: Index.html:

```
<!DOCTYPE html>
<html>

<head>
  <title>Vacation World</title>
  <link href='styles.css' rel='stylesheet'>
</head>

<body>
  <img src='https://content.codecademy.com/courses/freelance-1/unit-2/explorer.jpeg' />
  <h1 class='title' id='article-title'>Top Vacation Spots </h1>
  <h5>By: Stacy Gray</h5>
  <h6 id="publish-time">Published: 2 Days Ago</h6>

  <p>The world is full of fascinating places. Planning the perfect vacation involves packing up, leaving home, and experiencing something new.</p>

  <h2 class='destination heading-background'>1. Florence, Italy</h2>
  <div class='description'>A city-size shrine to the Renaissance, Florence offers frescoes, sculptures, churches, palaces, and other monuments from the richest cultural flowering the world has known. Names from its dazzling historical past; Dante, Michelangelo, Galileo, Machiavelliare are some of the most resonant of the medieval age. <a href='https://www.nationalgeographic.com/travel/destination/florence' target='_blank'>Learn More</a>.
    <h5>Top Attractions</h5>
    <ul>
      <li>Museums</li>
      <li>Bike Tours</li>
      <li>Historical Monuments</li>
    </ul>
  </div>

  <h2 class='destination heading-background'>2. Beijing, China</h2>
  <div class='description'>A city in the midst of reinventing itself and continuing to build on the success of the 2008 Summer Olympics, Beijing is a place of frenzied construction. New housing, new roads, and new sports venues seem to spring up overnight. At the same time, the capital of the Peoples Republic of China remains an epicenter of tradition, with the treasures of nearly 2,000 years as the imperial capital still on view in the famed Forbidden City and in the luxuriant pavilions and gardens of the Summer Palace.
    <a href='https://www.nationalgeographic.com/travel/destination/beijing' target='_blank'>Learn More</a>.
    <h5>Top Attractions</h5>
    <ul>
      <li>Biking</li>
      <li>Historical Sites</li>
      <li>Restaurants and Dining</li>
    </ul>
  </div>

  <h2 class='destination heading-background'>3. Seoul, South Korea</h2>
  <div class='description'>The Korean capital is a city of contrasts. Fourteenth-century city gates squat in the shadow of 21st-century skyscrapers, while the broad Han River is back-dropped by granite mountains rising in the city center complete with alpine highways speeding around their contours and temples nestling among their crags. Fashionable, gadget-laden youths battle for sidewalk space with fortune-tellers and peddlers, while tiny neighborhoods of traditional cottages contrast with endless ranks of identical apartments.
    <a href='https://www.nationalgeographic.com/travel/destination/seoul' target='_blank'>Learn More</a>.
    <h5>Top Attractions</h5>
    <ul>
      <li>Parasailing</li>
      <li>Segway Tours</li>
      <li>Spas and Resorts</li>
    </ul>
  </div>

  <h2> More Destinations </h2>
  <ul>
    <li><h4 class='destination'>Jackson Hole, Wyoming</h4></li>
    <li><h4 class='destination'>Cape Town, South Africa</h4></li>
    <li><h4 class='destination'>La Paz, Bolivia</h4></li>
  </ul>

  <p>&mdash;Best of luck with your travels, and be sure to send pictures and stories. We'd love to hear them!</p>


</body>

</html>
```

Style.css:

```
* {
    border: 1px solid red;
  }
  
  p {
    color: green;
  }
  
  h1 {
    color: maroon;
  }

  .title {
    color: teal;
  }

  #article-title {
    font-family: cursive;
  }

  a[href*='florence'] {
    color: lightgreen;
  }

  a:hover {
    color:darkorange;
  }

  .heading-background {
    background-color: aqua;
  }
  
  #publish-time {
    color: gray;
  }
  ```
  
  
  # Specificity
  
Specificity is the order by which the browser decides which CSS styles will be displayed. A best practice in CSS is to style elements while using the lowest degree of specificity so that if an element needs a new style, it is easy to override.

IDs are the most specific selector in CSS, followed by classes, and finally, type. For example, consider the following HTML and CSS:

```
<h1 class='headline'>Breaking News</h1>
```

```
h1 {
  color: red;
}
 
.headline {
  color: firebrick;
}
```

In the example code above, the color of the heading would be set to firebrick, as the class selector is more specific than the type selector. 

If an ID attribute (and selector) were added to the code above, the styles within the ID selector’s body would override all other styles for the heading.


# Chaining

When writing CSS rules, it’s possible to require an HTML element to have two or more CSS selectors at the same time.

This is done by combining multiple selectors, which we will refer to as chaining. For instance, if there was a special class for ```<h1>``` elements, the CSS would look like below:

```
h1.special {
 
}
```

The code above would select only the <h1> elements with a class of special. If a ```<p>``` element also had a class of special, the rule in the example would not style the paragraph.


## Class work

Let’s use chaining to select only the <h2> elements with destinations, and add a style to them.

In style.css, write a CSS selector for <h2> elements with a class of .destination. Inside the selector’s curly braces, add this declaration:

```
font-family: Tahoma;
```

This will change the font of the h2 elements that also have the class destination. The last ```<h2>``` element (“More Destinations”) will remain unchanged.

Solution:

style.css:

```
h2.destination {
  font-family: Tahoma;
}
```

## Descendant Combinator

In addition to chaining selectors to select elements, CSS also supports selecting elements that are nested within other HTML elements, also known as descendants. For instance, consider the following HTML:

```
<ul class='main-list'>
  <li> ... </li>
  <li> ... </li>
  <li> ... </li>
</ul>
```

The nested ```<li>``` elements are descendants of the ```<ul>``` element and can be selected with the descendant combinator like so:

```
.main-list li {
 
}
```

In the example above, .main-list selects the element with the.main-list class (the ```<ul>``` element). The descendant <li>‘s are selected by adding li to the selector, separated by a space. 

This results in ```.main-list li``` as the final selector.

## Class work

Navigate to style.css. Add a ruleset that uses the descendant combinator to target only the <h5> descendants of elements with the class .description.

Inside the curly braces of the selector, add a declaration of:

```
color: blueviolet;
```

style.css:

```
.description h5 {
  color: blueviolet;
}
```


## Chaining and Specificity

In the last exercise, instead of selecting all ```<h5>``` elements, you selected only the <h5> elements nested inside the .description elements. This CSS selector was more specific than writing only h5. Adding more than one tag, class, or ID to a CSS selector increases the specificity of the CSS selector.

For instance, consider the following CSS:

```
p {
  color: blue;
}
 
.main p {
  color: red;
}
```

Both of these CSS rules define what a ```<p>``` element should look like. Since .main p has a class and a p type as its selector, only the ```<p>``` elements inside the .main element will appear red. 

This occurs despite there being another more general rule that states ```<p>``` elements should be blue.


## Multiple Selectors

In order to make CSS more concise, it’s possible to add CSS styles to multiple CSS selectors all at once. This prevents writing repetitive code.

For instance, the following code has repetitive style attributes:

```
h1 {
  font-family: Georgia;
}
 
.menu {
  font-family: Georgia;
}
```

Instead of writing font-family: Georgia twice for two selectors, we can separate the selectors by a comma to apply the same style to both, like this:

```
h1, 
.menu {
  font-family: Georgia;
}
```

