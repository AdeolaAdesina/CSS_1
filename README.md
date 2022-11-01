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
