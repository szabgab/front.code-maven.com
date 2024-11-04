---
title: HTML basics
timestamp: 2015-06-01T15:10:01
tags:
  - HTML
  - br
  - h1
published: true
author: szabgab
---


In the first episode we are going to look at the basics of HTML, the language that allows us to describe the
structure of a web page.


## What you need

You'll need a web browser such as [Chrome](https://www.google.com/chrome/browser/desktop/) or [Firefox](https://www.mozilla.org/en-US/firefox/new/).

You'll also need a text editor. If you are using Microsoft Windows you can use [Notepad++](https://notepad-plus-plus.org/).
On Mac OSX I hear [TextWrangler](http://www.barebones.com/products/textwrangler/) is a nice editor.
On Linux you might want to use Gedit.

Create a directory called 'tso' somewhere on your computer. It can be on the Desktop, or directly on drive `c:\`. For now, the only important thing is that you'll easily find that directory. Open the editor, start a new document. Type in the following line:

```
Welcome to the Spaceship Operator!
```

Then save the file in the `tso` directory calling it `index.html`.

Now switch to your browser and open the `index.html` in the browser. You'll seee the same line that you typed in the file.

```
Welcome to the Spaceship Operator!
```

This is the first HTML file you created. It does not contain any special character that would indicate that it is an HTML file,
but that's ok.

{% include file="examples/tso/1/index.html" %}

[view](examples/tso/1/index.html)


## Second line

Now let's add a second line to the text file and save it again. The content in the editor will look like this:

```html
Welcome to the Spaceship Operator!
Following this series of articles you'll learn programming.
```

If you now open the file with the browser again you'll see only one line:

```
Welcome to the Spaceship Operator! Following this series of articles you'll learn programming.
```

That happen because the browsers disregard multiple so called "white-spaces" and uses a single "space" instead of them. A "white-space" is something that we normally cannot see. For example a real "space" character. A "TAB" character. A "newline" character we can add by pressing the ENTER/return button on the keyboard.

So even though you typed in two lines of text and you can see those two line in your editor, the browser shows them on one line.

You can now click the right button of your mouse and ask to "View Page Source". This will open a separate window with the real content
of the file where you can see the two lines.

{% include file="examples/tso/2/index.html" %}

[view](examples/tso/2/index.html)

## Add first HTML tags

In order to convince the browser to show the text in two lines we need to start adding real HTML.
HTML has "tags" that look like this:

```
<br>
```

A few letters between two angle-brackets.

Some of the tags stand on their own, like the above `br`-tag.

Others need to be added in pairs: an opening part and a closing part. For example this:

```
<div> Some content </div>
```

If there is a closing tag, it is always the same name with a leading slash `/`.


The opening part of the tags can also have so called "attributes". In the next example we see an `a` tag
that has both an opening side and a closing side. It also has an attribute called `href` with a value
`/`.

```
[Code Maven](/)
```

There is a whole [reference guide for HTML](https://developer.mozilla.org/en/docs/Web/HTML/Element),
but don't worry you won't need to learn all that. At least not to get started.

Let's see now how can we display those two lines on two separate lines. The `br` tag tells the browser to insert a line-break.
So if we put it at the end of the first row and reload the file in the browser we'll see the two rows on separate lines.

Source:

{% include file="examples/tso/3/index.html" %}

[view](examples/tso/3/index.html)

Result in the browser:

```
Welcome to the Spaceship Operator!
Following this series of articles you'll learn programming.
```

As you can see in the browser we don't see the `<br>` tag, but we see its impact: The two lines are on separate lines.

Before showing another HTML tag you could play try something. What will happen if you put the whole thing on one line. Like this
and then reload the page in the browser?

```
Welcome to the Spaceship Operator!<br>Following this series of articles you'll learn programming.
```

Try it yourself!

<div class="spoiler" text="Click for Explanation">
<p>
It will show as in the previous case. The newline we've just removed did not have any impact earlier. It can be removed.
The `br` is the important. Of course having one really long line in the HTML file is quite hard to edit so I 
don't recommend that practice, but it is good to remember the newlines don't have an impact on how the HTML
file is displayed in the browser.
</p>
</div>

We can now remove the `br` tag and add an `&lt;h1&gt;`-pair.
We are supposed to have only a single `h1` pair in any document. They are expected to enclose the main title of the page.
By default most browsers will show the content of the h1-elements with large letters and will insert a line-break after the closing
tag of the h1-pair.

{% include file="examples/tso/4/index.html" %}

[view](examples/tso/4/index.html)

It looks like this:

![](static/img/html_h1.png)

## HTML5 Skeleton

Before we continue, let's add a few more HTML tags and create a skeleton for an HTML page.
As many other things, HTML also has version and the requirements change from version to version.
This skeleton matches the HTML5 requirements:

{% include file="examples/tso/5/index.html" %}

[view](examples/tso/5/index.html)

You won't see any difference how this and the preious version looks in the browser.
The whole page is wrapped in `html` tags and it has two parts. `head` and `body`.
The `head` is traditionally used load other files such as CSS and JavaScript files, but
we don't really have to put those entries in the head any more. The `meta` tag still needs to go there,
as well as the `title` which will set what is shown on the "tab", on the border of the window holding the browser.

The code we had in the previous example goes into the `body`.


Now you can visit the [HTML reference guide](https://developer.mozilla.org/en/docs/Web/HTML/Element) and try playing with
the various HTML elements.
