## Table of Contents

* [Introduction](#-1-introduction)


## # 1. Introduction

### Q. What is difference between HTML and XHTML?

The Extensible Hypertext Markup Language, or XHTML, has two important notes for front end developers.

    It needs to be well formed, meaning all elements need to be closed and nested correctly or you will return errors.
    Since it is more strict than HTML is requires less pre-processing by the browser, which may improve your sites performance.

### Q. What are the semantic tags available in html5?

HTML5 semantic tags define the function and the category of your text, simplifying the work for browsers and search engines, as well as developers.

HTML5 offers new semantic elements to define different parts of a web page:

    <article>
    <aside>
    <details>
    <figcaption>
    <figure>
    <footer>
    <header>
    <main>
    <mark>
    <nav>
    <section>
    <summary>
    <time>

Syntax:
```
<!DOCTYPE html> 

<html>  
   <head> 
      <meta charset = "utf-8"/> 
      <title>...</title> 
   </head> 
  
   <body> 
      <header>...</header> 
      <nav>...</nav> 
      
      <article> 
         <section> 
            ... 
         </section> 
      </article> 
      <aside>...</aside> 
      
      <footer>...</footer> 
   </body> 
</html> 
```

### Q. Why you would like to use semantic tag?

    Search Engine Optimization, accessibility, repurposing, light code.
    Many visually impaired person rely on browser speech and semantic tag helps to interpret page content clearly.
    Search engine needs to understand page content to rank and semantic tag helps.
    Semantic code aids accessibility. Specially, many people whose eyes are not good rely on speech browsers to read pages to them. These programs cannot interpret pages very well unless they are clearly explained.
    Help Search engines to better understand pages. Search engine need to understand what your content is about when rank you properly on search engines. Semantic code tends to improve your placement on search engines, as it is easier for the "search engine spiders" to understand.
    It's easier to read and edit, which saves time and money during maintenance.

### Q. What does a <DOCTYPE html> do?

A DOCTYPE is always associated to a DTD ( Document Type Definition ). A DTD defines how documents of a certain type should be structured (i.e. a button can contain a span but not a div), whereas a DOCTYPE declares what DTD a document supposedly respects (i.e. this document respects the HTML DTD). For webpages, the DOCTYPE declaration is required. It is used to tell user agents what version of the HTML specifications your document respects.

Once a user agent has recognized a correct DOCTYPE, it will trigger the no-quirks mode matching this DOCTYPE forreading the document. If a user agent doesn't recognize a correct DOCTYPE, it will trigger the quirks mode.

### Q. What is Quirks mode?

Refer - [MDN docs Quirks Mode](https://developer.mozilla.org/en-US/docs/Web/HTML/Quirks_Mode_and_Standards_Mode)

### Q. Explain meta tags in HTML.

Meta Tag ```<meta/>``` is a HTML component that gives the metadata about a HTML document. 
They are always present inside the <Head> tag and are utilized to portray Page portrayals, Certain Keywords, Author of the Document, viewport settings, determining character sets, and so on.
They are used by Web Browsers, Search Engines, and other Web Services to rank the web pages accordingly.

[Read this](https://www.freecodecamp.org/news/meta-tag-in-html-what-is-metadata-and-meta-description-example/)

Read [Use of meta tag](https://www.geeksforgeeks.org/explain-use-of-meta-tags-in-html/).

### Q. What is difference between SVG and Canvas?

1. SVG:

The Scalable Vector Graphics (SVG) is an XML-based image format that is used to define two-dimensional vector based graphics for the web. Unlike raster image (e.g. .jpg, .gif, .png, etc.), a vector image can be scaled up or down to any extent without losing the image quality.

There are following advantages of using SVG over other image formats like JPEG, GIF, PNG, etc.

    SVG images can be searched, indexed, scripted, and compressed.
    SVG images can be created and modified using JavaScript in real time.
    SVG images can be printed with high quality at any resolution.
    SVG content can be animated using the built-in animation elements.
    SVG images can contain hyperlinks to other documents.

Example:

```<!DOCTYPE html>
<html>
   <head>
      <style>
         #svgelem {
            position: relative;
            left: 50%;
            -webkit-transform: translateX(-20%);
            -ms-transform: translateX(-20%);
            transform: translateX(-20%);
         }
      </style>
      <title>HTML5 SVG</title>
   </head>
   <body>
      <h2 align="center">HTML5 SVG Circle</h2>
      <svg id="svgelem" height="200" xmlns="http://www.w3.org/2000/svg">
         <circle id="bluecircle" cx="60" cy="60" r="50" fill="blue" />
      </svg>
   </body>
</html>```

2. Canvas:

Canvas is a HTML element is used to draw graphics on a web page. It is a bitmap with an “immediate mode” graphics application programming interface (API) for drawing on it. The <canvas> element is only a container for graphics. In order to draw the graphics, you are supposed to use a script. Canvas has several strategies when it comes to drawing paths, boxes, circles, text & adding images.

Example:

```<!DOCTYPE html>
<html>
   <head>
      <title>HTML5 Canvas Tag</title>
   </head>
   <body>
      <canvas id="newCanvas" width="200" height="100" style="border:1px solid #000000;"></canvas>
      <script>
         var c = document.getElementById('newCanvas');
         var ctx = c.getContext('2d');
         ctx.fillStyle = '#7cce2b';
         ctx.fillRect(0,0,300,100);
      </script>
   </body>
</html>```

Differences:
SVG 	Canvas
Vector based (composed of shapes) 	Raster based (composed of pixel)
Multiple graphical elements, which become the part of the page's DOM tree 	Single element similar to in behavior. Canvas diagram can be saved to PNG or JPG format
Modified through script and CSS 	Modified through script only
Good text rendering capabilities 	Poor text rendering capabilities
Give better performance with smaller number of objects or larger surface, or both 	Give better performance with larger number of objects or smaller surface, or both
Better scalability. Can be printed with high quality at any resolution. Pixelation does not occur 	Poor scalability. Not suitable for printing on higher resolution. Pixelation may occur

### 2. What is iframe element in HTML
An iFrame, also knowns as Inline Frame, is an element that loads another HTML element inside of a web page. They are commonly used to embed specific content like external ads, videos, tags, or other interactive elements into the page.

```HTML
<iframe src="https://github.com" height="300px" width="300px"></iframe>
```

### Q. What is progressive rendering?

Progressive Rendering is the technique of sequentially rendering portions of a webpage in the server and streaming it to the client in parts without waiting for the whole page to rendered.

It implies that once the important material is produced on the server, you may stream it to the client without having to wait for non-critical stuff to be displayed. It combines the advantages of both CSR (Client Side Rendering) and SSR (Server Side Rendering) (Server Side Rendering).

1. Client Side Rendering:

Client Side Rendering (CSR) is a technique in which content is rendered in the browser using JavaScript. Instead of getting all the content from the HTML file itself, the server sends HTML with an empty body and script tags that contain links to JavaScript bundles that the browser will use to render the content.

Typical page load behaviour in CSR —

    Browser requests the server for HTML
    Server sends HTML with script tags in head and no content in body
    Browser parses the HTML and makes http requests to load the scripts
    Once the scripts are loaded, the browser parses them and makes API requests and loads all the content asynchronously

Since the all the content starts loading only after loading the initial JavaScript, it takes a longer time to show any content on the page. If the user is on a slow network, the content is blocked for an even longer time due to lower bandwidth and higher latency.

2. Server Side Rendering:

When rendering on the server side, the HTML is rendered on the server and sent to the client. The content that we need to display on the screen becomes available immediately after the HTML is parsed; hence, primary rendering of content is faster than CSR.

Typical page load behaviour in SSR —

    Browser requests the server for HTML.
    Server makes API requests (usually co-located) and renders the content in the server.
    Once the page is ready, the server sends it to the browser.
    The browser loads and parses the HTML and paints the content on the screen without waiting for the JavaScript bundle(s) to load.
    Once the JavaScript bundle(s) are loaded, the browser hydrates interactivity to DOM elements, which is usually attaching event handlers and other interactive behaviours.

Since the APIs are usually co-located with the server, the content is loaded super fast (faster than CSR) and the HTML is sent to the browser. Initial JavaScript load doesn't block content load as the HTML sent by the server already has the content.


### 3.  How can you highlight text in HTML?
If you are working with an HTML5 page, the ```<mark>``` tag can be a quick and easy way of highlighting or marking text on a page:

```
<mark>highlighted text</mark>
```

To highlight text with just HTML code and support for all browsers, set the background-color style, as shown in the example below, using the HTML tag.
```
<span style="background-color: #FFFF00">Yellow text.</span>
```

### 4. How Can I Get Indexed Better by Search Engines?

It is possible to get indexed better by placing the following two statements in the ```<HEAD>``` part of your documents:
```
<META NAME="keywords" CONTENT="keyword keyword keyword keyword">

<META NAME="description" CONTENT="description of your site">
```

Both may contain up to 1022 characters. If a keyword is used more than 7 times, the keywords tag will be ignored altogether. Also, you cannot put markup (other than entities) in the description or keywords list.


### 5. Briefly describe the correct usage of the following HTML5 semantic elements: header, article, section, footer

```<header>``` is used to contain introductory and navigational information about a section of the page. This can include the section heading, the author’s name, time and date of publication, table of contents, or other navigational information.

```<article> ```is meant to house a self-contained composition that can logically be independently recreated outside of the page without losing it’s meaining. Individual blog posts or news stories are good examples.

```<section>``` is a flexible container for holding content that shares a common informational theme or purpose.

```<footer>``` is used to hold information that should appear at the end of a section of content and contain additional information about the section. Author’s name, copyright information, and related links are typical examples of such content.


### 6. Difference between property and attributes in HTML

[Geeks for Geeks article](https://www.geeksforgeeks.org/what-is-the-difference-between-properties-and-attributes-in-html/)


### 7. What's new in HTML 5?

HTML 5 adds a lot of new features to the HTML specification

New Doctype

Still using that pesky, impossible-to-memorize XHTML doctype?
```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```
If so, why? Switch to the new HTML5 doctype. You'll live longer -- as Douglas Quaid might say.
```
<!DOCTYPE html>
```
New Structure

    <section> - to define sections of pages
    <header> - defines the header of a page
    <footer> - defines the footer of a page
    <nav> - defines the navigation on a page
    <article> - defines the article or primary content on a page
    <aside> - defines extra content like a sidebar on a page
    <figure> - defines images that annotate an article

New Inline Elements

These inline elements define some basic concepts and keep them semantically marked up, mostly to do with time:

    <mark> - to indicate content that is marked in some fashion
    <time> - to indicate content that is a time or date
    <meter> - to indicate content that is a fraction of a known range - such as disk usage
    <progress> - to indicate the progress of a task towards completion

New Form Types

    <input type="datetime">
    <input type="datetime-local">
    <input type="date">
    <input type="month">
    <input type="week">
    <input type="time">
    <input type="number">
    <input type="range">
    <input type="email">
    <input type="url">

New Elements

There are a few exciting new elements in HTML 5:

    <canvas> - an element to give you a drawing space in JavaScript on your Web pages. It can let you add images or graphs to tool tips or just create dynamic graphs on your Web pages, built on the fly.
    <video> - add video to your Web pages with this simple tag.
    <audio> - add sound to your Web pages with this simple tag.

No More Types for Scripts and Links

You possibly still add the type attribute to your link and script tags.
```
<link rel="stylesheet" href="path/to/stylesheet.css" type="text/css" />
<script type="text/javascript" src="path/to/script.js"></script>
```
This is no longer necessary. It's implied that both of these tags refer to stylesheets and scripts, respectively. As such, we can remove the type attribute all together.
```
<link rel="stylesheet" href="path/to/stylesheet.css" />
<script src="path/to/script.js"></script>
```
Make your content editable

The new browsers have a nifty new attribute that can be applied to elements, called contenteditable. As the name implies, this allows the user to edit any of the text contained within the element, including its children. There are a variety of uses for something like this, including an app as simple as a to-do list, which also takes advantage of local storage.
```
<h2> To-Do List </h2>
<ul contenteditable="true">
<li> Break mechanical cab driver. </li>
<li> Drive to abandoned factory
<li> Watch video of self </li>
</ul>
```
Attributes

require to mention the form field is required
autofocus puts the cursor on the input field