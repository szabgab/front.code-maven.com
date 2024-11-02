---
title: Hello World in plain HTML
timestamp: 2015-11-07T11:30:01
published: true
author: szabgab
description: The text for the search engines
tags:
    - HTML
---


The first step in building web applications is to learn about HTML and the first thing there is to
learn is to create an HTML file showing **Hello World!**.


## Plain text as HTML

As you can read in the [HTML Basics](/html-basics), even plain text can be considered to be `HTML`.
If we create a file with `.html` and open it with a web browser such as Firefox, Chrome, Opera, Safari, or even Internet Explorer,
then the browser will try to do its best to display the content of the file as HTML.

Therefore the most simple solution is to create a file with `.html` and have the following content in it:

{% include file="examples/html/hello_world.html" %}

[view](examples/html/hello_world.html)

You can either click on the "try" link to see it working, or you can copy the content of the example and open it
from your hard disk using the **File/Open** menu option of your browser.


## HTML 5 skeleton

A better solution is to provide a full HTML5 skeleton.

{% include file="examples/html/hello_world_html5.html" %}

[view](examples/html/hello_world_html5.html)

In this example we have "Hello World!" twice. The one in the `title` element is the
one that is displayed on "tab" of the web browser or on the frame of the window showing the web browser.

The one inside the `body` element is the one that we usually see in the browser.

