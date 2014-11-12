# Embedding JavaScript in a Web Page

JavaScript was originally written to be the language that web developers could
use to program web pages in a browser. It has since evolved and moved into other
environments (like node.js, for example), but its primary purpose is still as
the scripting language for the web. All modern web browsers support JavaScript.

You may be wondering _how_ to use JavaScript on a web page. Good question! That
is exactly what we are going to focus on in these exercises: the various ways to
add JavaScript to a page.

As you move through these exercises, you may want to keep these pages open for
reference and learning:

- [Douglas Crawford's explanation of script tags](http://javascript.crockford.com/script.html)
- [MDN Documentation on the script tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)

## Exercises

**Note**: to complete these exercises, you will need to create an HTML file
(which we will refer to here by the name `page.html`). Once you have created the
file, copy the following default content into it and open the file in your
browser.

`page.html`:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>JavaScript is fun</h1>
    <p>Did you know that JavaScript is the <em>lingua franca</em> of the web?</p>
  </body>
</html>
```

### In the beginning, there is <script>

Can you complete the following code so that the JavaScript runs? If it works, it
will display an alert window.

```html
<!DOCTYPE html>
<html>
  <body>
    <__>
      alert("ITS ALIVE!!");
    </__>
    <h1>JavaScript is fun</h1>
    <p>Did you know that JavaScript is the <em>lingua franca</em> of the web?</p>
  </body>
</html>
```

Search suggestion: `embed javascript in html`

> To tell the browser to "execute this JavaScript", you must use the `<script>`
> tag. Otherwise, the browser expects to find normal HTML and it won't run the
> JavaScript.

### Best practice: define the script type

Can you assign the appropriate value to the tag in this example?

```html
<!DOCTYPE html>
<html>
  <body>
    <__ type="__/__">
      alert("ITS ALIVE!!");
    </__>
    <h1>JavaScript is fun</h1>
    <p>Did you know that JavaScript is the <em>lingua franca</em> of the web?</p>
  </body>
</html>
```

Search suggestion: `define type attribute javascript script tag`

> While browsers will default to using JavaScript even if you don't define the
> `type` attribute of the `script` tag, it is a good idea to be explicit so that
> the browser knows what to expect.

### Everything must wait its turn

Can you edit the code below so that it executes the JavaScript? What can you
learn about how the browser loads a page from this example?

```html
<!DOCTYPE html>
<html>
  <body>
    <h2>This should appear first</h2>

    <__ type="__/__">
      confirm("Shall we keep going?");
    </__>

    <h2>...then finally we get to here.</h2>
  </body>
</html>
```

> Browsers load HTML from top to bottom, left to right. When you put a
> `<script>` tag in the page, the browser will stop loading the rest of the HTML
> page to run the JavaScript, and then it will continue loading the page only
> after the JavaScript has finished executing.

### Inline scripts can print text to the page

Can you figure out how to make the code below print the current time onto the
HTML page?

```html
<!DOCTYPE html>
<html>
  <body>
    <h2>What time is it?</h2>

    <p>
      The time is <strong><script type="text/javascript">document.__( new Date().toString() );</script></strong> where you are.
    </p>
  </body>
</html>
```

Search suggestion: `javascript write text to document`

> What's that `new Date().toString()` code? That is a how, in JavaScript, we can
> say "get me the current date and time, and then convert it to a String".

### Think global, act local

So that last example left us with a lot of JavaScript in one `<script>` tag.
What if we wanted to break it up, so that one script created the time string
while the other wrote it to the page?

Can you modify the code below so that it renders the same time as before, but
using a variable instead to store the time string?

```html
<!DOCTYPE html>
<html>
  <script type="text/javascript">
    var __ = new Date().toString();
  </script>

  <body>
    <h2>What time is it?</h2>

    <p>
      The time is <strong><script type="text/javascript">document.__(__)</script></strong> where you are.
    </p>
  </body>
</html>
```

Search suggestion: `javascript store value in variable`

> Even though the JavaScript in this example is split between two `<script>`
> tags, it all runs in the same context. Variables declared in one script will
> be accessible to all other scripts on the same page.