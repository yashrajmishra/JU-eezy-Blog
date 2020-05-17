---
title: "HTML,CSS, and JS"
path: "/webworks"
date: "2020-02-22"
author: "Atul Sharma"
excerpt: 'Always wonder how these websites work how they function, how to code or want to be a web developer.....'
tags: ["html","css","Javascript","web development"]
---

## How the Web Works

The World Wide Web is an information space where documents and other web resources are identified by Unique Resource Locators, or URLs, interlinked by
hypertext links and can be accessed by the internet.

Everything has a unique URL and is based on a document, an HTML document. So, the web works because of some basic ingredients.

The **first ingredient** is resources, like HTML documents, images, or other files. This is the content that we want to use, websites that we want to browse, images to look at, files that we want to share.

The **second ingredient** is URLs. These uniquely identify the resources so that your web browser can ultimately show them to you or download them. Every resource on the web has a unique URL.

The **final main ingredient** that makes all of this work is the Hypertext Transfer Protocol, or HTTP. This protocol is the magic that can retrieve documents and communicate them to your web browser.

The HTTP protocol takes care of the information communication between the web browser and the web server to actually get the document so that the web browser can render it on the screen. Whilst painting an HTML document on the screen, a web browser uses CSS and JavaScript to style the document and give it functionality.

---

## Why Learn About HTML, CSS, and JavaScript

The HTML document that gets rendered and painted on the screen. It gets formatted and styled with CSS, and it gets functionality from JavaScript. These are interesting technologies.

### *Displaying the Web with HTML*

HTML is the standard markup language for creating web pages and applications, so it is the standard language for the web, and it is a markup language and not a programming language or a scripting language. This means that you use it to control the presentation of data just like we've seen in the websites where the data is as text or images.

These are documents with the HTM or HTML extension that are served by web servers on unique URLs. HTML documents contain various elements that are specified in the HTML specification and can be understood by all web browsers.

The first element in any HTML document is the DOCTYPE element. Next are the HTML elements. Every element has an open and a close element. This tells the browser that everything in here is HTML. Then`there is the head element. This can include a title for the document, scripts, styles, metainformation, and more.` And finally, there is the body element that contains everything that you want to be displayed on the screen. These are all the elements that are necessary in an HTML document. All the basic HTML elements are here.In the body element, it has a div tag, which indicates that everything in his tags belongs togethor. A example is given below:

```html
<!DOCTYPE html>
<html>
<head>
<title>A first HTML document</title>
<meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no" />
  <meta name="description" content="" />
  <meta name="keywords" content="" />
  <script type="text/javascript" src="./assets/js/calculation.js"></script>
  </head>
<body>
<div>......
<section>....
</section>
</div>
</body>
</html>
```

There are much more elements and tags in HTML than just these standard ones which make webpages much more expressive.

You can, for instance, write your HTML documents from scratch using a simple text editor like Notepad or an integrated development environment (IDE), these are tools that provide you with any extra features, like suggesting HTML tags to use error checking.I would recommend Visual Studio as IDE provides a lot of benefits over a simple text editor.There are also online HTML editors that you don`t have to install on our computer.

#### Styling the Web with CSS

Displaying text and images on the web is nice, but we need to be able to style the content so that it is readable and useable.

CSS, or Cascading Style Sheets, is a style sheet language that is used to describe the presentation of a document. There is also other style sheet languages to style different things like XML. CSS is one of those and is the most important for the web.When the browser loads this HTML, it also loads this CSS file and uses the styles on HTML.

FIrst of all, the styles are not in the HTML document anymore, which makes everything easier to read and maintain. Also because the styles are in a separate document, you can link that document in multiple HTML documents and apply the same styles there.

As in the example below CSS consists out of properties and attributes, like the color being blue or the text being italic. Also CSS can indicate to what elements the properties should be apllied.

```css
pre {
 background: #1a1a1d;
 padding: 20px;
 border-radius: 8px;
 font-size: 1rem;
 overflow: auto;
 @media (--phone) {
 white-space: pre-wrap;
 word-wrap: break-word;
 }
 code {
 background: none !important;
 color: #ccc;
 padding: 0;
 font-size: inherit;
 .dark-theme & {
 color: inherit;
 }
 }
}
```

CSS is called cascading, as in Cascading Style Sheets, because properties are applied in a specific order, based on priority.

To work with CSS, all we need to know is how to couple CSS to HTML and for that we`ve to host CSS documents on web servers.There are several ways to create CSS from scratch by using text editor or IDE. Another way of using CSS is to use CSS from a library.These are CSS files that are written by other people that alreay contain lot of styles that you can use in your document. There are lots of CSS libraries around, and most of them are open source and free. A very popular CSS library is **Bootstrap** which is created by Twitter. And there is Font Awesome, Ionic and Materialize.

Each of these provides different styles and different capabilities, and all of these are designed to make life easier for you as you don't have to create the styles, you just use them.

#### Interacting with the Web with Javascript

You will use Javascript to interact with HTML, the browser, and other systems to make the web more interactive.

JavaScript is a high-level interpreted programming language.And it is an interpreted language which means you don`t have to compile the code before you execute it. It is interpreted at runtime, and it is a high-level programming language , which means that it is a high abstraction from the computer, which makes it easy to use. In contrast, the C programming language, which is more complicated, but gives you more control over things like memory management.

JavaScript sounds like it is the script version of Java. It really isn`t, it only shares its looks with Java, not its implementation.

JS can be used manipulate HTML, the browser, and to talk with services like API`s (Application Programming Interface) that live on other servers. It can be written anywhere in HTML. It is used to select an HTML element and alter one of its properties, as it does this without refreshing the page. A example is given below:

```javascript
const distance = (x0, y0, x1, y1) => Math.hypot(x1 - x0, y1 - y0);
distance(1, 1, 2, 3); // 2.23606797749979- output
```

JS code can be written in a separate file and can be called from within the script tag in HTML. A way to work with JavaScript is by using libraries and frameworks. Just like there are CSS libraries that provide premade styles for you, there are JavaScript
libraries that provide premade JavaScript functionality for you. There are so many JavaScript libraries that it is hard to keep up with. Here are some of them. A very well-known library is jQuery. You can use this to do all sorts of things that you don't have to write yourself.

There are more advanced libraries and frameworks,These are things like Angular,Knockout, React, and TypeScript. They all help you to be more productive in
some way, but they also require specific knowledge.

### Resources to learn more

Now that you've learned the concepts of HTML, CSS, and JavaScript, you might want to learn more. Here are some links that I find very useful. These can help you to start learning how to develop in each of these technologies. First of all, some general links. At **w3schools.com**, you can learn everything about HTML, CSS, and JavaScript. It contains information and tutorials that you can use for free.
