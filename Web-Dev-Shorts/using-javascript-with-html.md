---
title: "Using Javascript with HTML"
tags: "JS"
---

# Using Javascript with HTML

## How do you add Javascript to your page?

### Internal Javascript

To add javascript internally you would include the script tag shown below in your html file. A good practice is to include the script at the very end of your body tag. This must be done because errors can occur if javascript is processed before the html has loaded in.

```javascript
<script></script>
```

### External Javascript

Instead of including the javascript in your html file, you may want to have it in a seperate javascript file, this is seen most commonly. To use an external javascript file we must create a link to that file in our html page. To do this we would use the script tag below, with the src attribute filled with the location of the javascript file in terms of the html file. You would also include this at the bottom of your html body, to allow all of your html to load in first.(However this is not maintable for large sites, we will cover a solution to this later)

```javascript
<script src="script.js"></script>
```

## Script Loading Strategies

### Internal Strategies

* * *

1.  Including the file at the bottom of the body tag as discussed above.
2.  Adding an event listener to wait until the html has loaded and then loading the javascript included in the block of the listener. This can be seen below:

```javascript
document.addEventListener("DOMContentLoaded", function() {
  //Javascript code goes here
  /*This allows you to place the internal script
	anywhere in your html file instead of just at the bottom of the body.*/
});
```

### External Strategies

* * *

### Async and Defer

Async and defer instruct the browser to download the scripts in a seperate thread, while the rest of the page is downloading. This way the page loading is not blocked by the scripts.

### Async

Below is an example of async being used to load an external script.

```JS
<script async src="js/vendor/jquery.js"></script>
```

Async downloads the script without blocking the rendering of the page. The unique thing about async is that it loads scripts in no particular order. This means that if you have multiple scripts that depend on each other this could potentially cause errors.

**Async is useful when you have multiple scripts that are not dependent on eachother.**

### Defer

Below is an example of defer being used to load an external script.

```JS
<script defer src="js/vendor/jquery.js"></script>
```

Similarly to async, defer downloads the script(s) without blocking the rendering of the page. However, when downloading multiple scripts, it downloads them in the order that they are written.

**Defer is to be used when you have multiple scripts that must be loaded in a particular order.**

## Comments

There are two different ways of declaring/using comments, single line and multi-line. Examples of both are below.

### Single line

```JS
//This is a single line comment
```

### Multi-line

```JS
/*This is how to use 
a multiline comment*/
```
