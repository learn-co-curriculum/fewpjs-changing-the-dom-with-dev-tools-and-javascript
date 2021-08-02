# Changing The DOM with DevTools and JavaScript

## Learning Goals

1. Demonstrate viewing the DOM through Chrome DevTools
2. Select an element with Chrome DevTools
3. Delete an element with Chrome DevTools
4. Demonstrate that the source is not changed when the DOM is
5. Demonstrate opening the DevTools' JavaScript console
6. Select an element with JavaScript
7. Delete an element with JavaScript
8. Demonstrate that the source is not changed when the DOM is

## Introduction

We've read that updating the DOM will update the browser's rendered page. Let's
experience this now. We're going to change the DOM in two ways. First, we'll use
Chrome's Developer Tools ("DevTools") and our mouse to remove an element from
the DOM. Then we'll use the DevTools' JavaScript console to run JavaScript that
does the same thing.

## Instructions

### Demonstrate Viewing the DOM Through Chrome DevTools

To get started, visit this web page:

- [https://example.com/](https://example.com/)

Right-click anywhere on the page, and select "Inspect" to open up the Developer
Tools (you can also press `Command + Option + I` on Mac or `Control + Shift + I`
on Windows/Linux), and select the Elements tab. You should see something like
this:

![Open the elements tab](https://curriculum-content.s3.amazonaws.com/module-3/fewpjs-changing-the-dom-with-dev-tools-and-javascript/open-elements-tab.gif)

Here we have the DOM representation of the HTML source the browser loaded.

### Select an Element With Chrome DevTools

Scroll through the Elements panel. You will see some HTML: `head` tags, `body`
tags, `div`s, etc.

![Locate the h1 element](https://curriculum-content.s3.amazonaws.com/module-3/fewpjs-changing-the-dom-with-dev-tools-and-javascript/locate-header.gif)

Now, from inside the developer console, locate and click on the element that
says `h1`. You will notice that the `h1` section of the webpage is
highlighted. You've now selected an element with the DevTools.

### Delete an Element With Chrome DevTools

![Delete the h1 element](https://curriculum-content.s3.amazonaws.com/module-3/fewpjs-changing-the-dom-with-dev-tools-and-javascript/delete-header.gif)

Press the delete button on your keyboard (or right-click and select "Delete"
from the menu). The element will vanish from the browser's rendered page.

### Demonstrate That the Source is Not Changed When the DOM Is

View the original HTML by right-clicking on the page and selecting "View Page
Source". You will see the that the HTML is just as it always was, with a header
tag and lots of other elements inside.

![View the page source](https://curriculum-content.s3.amazonaws.com/module-3/fewpjs-changing-the-dom-with-dev-tools-and-javascript/open-page-source.gif)

The changes in the DOM do not affect the HTML file on the server. When you think
about it, that makes sense. If that were true then anyone could be changing
carefully-written HTML.

The HTML, which lives on the server, **is unchanged**.

Close the Page Source view, and refresh the page clicking the refresh button (or
pressing `Command + r` on Mac or `Control + r` on Windows). You will be
reloading the DOM _from the source_. The `h1` will come back.

### Demonstrate Opening the DevTools' JavaScript Console

We can do the exact same work we did by selecting elements and deleting them
with delete key in the DevTools with JavaScript. Open the "Console" tab in the
browser by pressing `Command + Option + J` (for Mac) or `Control + Shift + J`
(for Windows).

At the bottom you will see a cursor. There, type the word `document` and press
"Enter." You'll get a `#document` returned. If you click the disclosure
triangle, you'll see that it's the exact HTML that you would find in the
**Elements** tab.

_Note: `disclosure triangle` is the triangle that is on the left side of the
`#document`. It is hiding the HTML that wouldn't normally be shown. It is good
information to have if you wanted more details about what is going on behind the
scenes. Those triangles are standard for hiding more information throughout
Chrome DevTools. If you want to see more, feel free to click on the triangle!
You're not going to break anything._

Since `document` is an `object` which means that it has properties and `methods`
we can imagine that by calling `methods` on it, it can return DOM elements.
Let's find or `select` an element by speaking JavaScript with the DOM.

### Select an Element With JavaScript

In the **Console** type:

```javascript
document.querySelector("h1");
```

This will return something like this: `<h1>Example Domain</h1>`. This is the DOM
Node, a JavaScript `object`. This means that it, in turn, can have methods
called on it! This is called _method chaining_. Let's use _method chaining_ to
remove our node from the DOM.

### Delete an Element with JavaScript

Now type:

```javascript
document.querySelector("header").remove();
```

The header is gone! We called `document.querySelector('header')` in order
to get the node onto which we _chained_ the call to `remove()`. We use
dot-notation to _chain_ the calls.

Follow the same process we followed earlier to verify that the HTML source has
not changed. To restore it, simply refresh the page (i.e. reload the DOM).

### Preview JavaScript Variables

Our JavaScript code would be really annoying if we always had to refer to a node
by looking it up with `document.querySelector`. We'd like to have JavaScript do
that finding work finding the node _once_ and then _save_ our ability to refer
to that node. That's exactly what _variables_ do. Just like pronouns in human
communication, variables let us refer to a calculation, a process, or a value by
giving it a name. In the next lesson we'll talk in depth about _variables_.

## Conclusion

DOM programming is using JavaScript to:

1. Ask the DOM to find or `select` an HTML element or elements in the rendered page
2. Remove the selected elements and/or insert a new element
3. Adjust a property of the selected element(s)

In this lesson you just did all that stuff! Learning to duplicate what you can
do in DevTools with JavaScript **is** DOM programming. The next lessons are
going to give you `methods` for selecting elements and changing them, but you
just changed the DOM. High fives are in order.
