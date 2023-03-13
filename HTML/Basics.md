### 1. Explain meta tags in HTML.

Meta Tag ```<meta/>``` is a HTML component that gives the metadata about a HTML document. 
They are always present inside the <Head> tag and are utilized to portray Page portrayals, Certain Keywords, Author of the Document, viewport settings, determining character sets, and so on.
They are used by Web Browsers, Search Engines, and other Web Services to rank the web pages accordingly.

[Read this](https://www.freecodecamp.org/news/meta-tag-in-html-what-is-metadata-and-meta-description-example/)

Read [Use of meta tag](https://www.geeksforgeeks.org/explain-use-of-meta-tags-in-html/).

### 2. What is iframe element in HTML
An iFrame, also knowns as Inline Frame, is an element that loads another HTML element inside of a web page. They are commonly used to embed specific content like external ads, videos, tags, or other interactive elements into the page.

```HTML
<iframe src="https://github.com" height="300px" width="300px"></iframe>
```


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