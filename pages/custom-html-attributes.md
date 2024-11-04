---
title: Custom HTML Attributes
timestamp: 2016-08-31T09:00:01
tags:
  - HTML
  - JavaScript
  - getElementsByTagName
  - getAttribute
  - dataset
published: true
author: szabgab
---


If you are familiar with HTML, and the valid attributes of most of the elements,
you probably also know that if you provide an attribute that is not one of the official
attributes of that element the browsers will disregard it.

What you might not know is that those attributes are still parsed and are still part of
the DOM, the [Document Object Model](https://en.wikipedia.org/wiki/Document_Object_Model).

That is, they are still accessible by JavaScript running in the browser.


Let's see an example.

In the following HTML file we have an `h1` element and some text.
If you click on the 'try' link you'll be able to see how that is displayed in your brower.
It shows the text within the `h1` element with bigger letters, because that's what
we expect from a header element.

{% include file="examples/html/html_attribute_h1.html" %}

[view](examples/html/html_attribute_h1.html)

We can add a `style` attribute and within that we can add CSS instructions.
For example we can tell the browser to use smaller fonts for the `h1` element:

{% include file="examples/html/html_attribute_style.html" %}

[view](examples/html/html_attribute_style.html)

This works because `style` is a known attribute of `h1` and for
that matter for every HTML element.

## Custom attribute

In the next example removed the `style` attribute and added a different
attribute, called `secret-sauce`. If you open the html in a
browser you'll see that the content of the `h1` element returned to
it original size, and you won't see any impact of the new attribute.

{% include file="examples/html/custom_html_attribute.html" %}

[view](examples/html/custom_html_attribute.html)

No warnings, no errors. That's because the browser simply disregards those attributes.

## Attributes are in the DOM

While the browser seems to disregard the existance of this attribute, it actually
parses it and puts it on the DOM. Meaning we can access this attribute using JavaScript.

{% include file="examples/html/custom_html_attribute_show.html" %}

[view](examples/html/custom_html_attribute_show.html)

Using `document.getElementsByTagName` we fetch the list of all the
`h1` elements in the document and the we use the index `[0]` to
access the first such element. On that element we use the `getAttribute`
method to access the value of the given attribute.

Then we use `console.log` to print it. click on the 'Try' link and in
the new window
[open the JavaScript console](/open-javascript-console) to see the value.


## data-* attributes


HTML5 defined a set of attributes using the prefix `data-` that get special treatment.
They are not used by the browser, but they, (the broswers) provide access to them through special
syntax. The objects representing the HTML tags that we retreive from the DOM of modern browsers
have a standard attribute called `dataset` that provides access to all the `data-*`
attributes as in this example:

{% include file="examples/html/custom_html_attribute_show_data.html" %}

[view](examples/html/custom_html_attribute_show_data.html)

As you might have noticed however, the names of the attributes in the HTML and the names
we use in JavaScript to access them are not exactly the same. That's because JavaScript
cannot have dash `-` in attribute names when using the `.` syntax.

So the attribute name called `data-secret-sauce` in the HTML is accessible as 
`dataset.secretSauce` in the JavaScript code.

Another issue with this special syntax is that Internet Explorer started to support this
only in version 11. For older version you'll still have to use the regular `getAttribute`
syntax.

For further examples check out the 
[guide from Mozilla](https://developer.mozilla.org/en/docs/Web/Guide/HTML/Using_data_attributes).


## ng-* custom attributes used by AngularJS

[AngularJS](/angularjs) uses the `ng-` prefix
for all the custom attributes. This makes it clear to the reader that something
is related to AngularJS.

Actually Angular will also work with attributes using `data-ng-` prefix, in case
you'd like to stick to the HTML specifications.

## Caveat

The problem with the arbitrary attribute names is that if two JavaScript libraries happen to rely
on the same attribute name and we try to use the two libraries in the same HTML file, then those
two will collide. Using some kind of project-specific prefix, such as the `ng-` in case
of AngularJS, can reduce the risk of this problem.


