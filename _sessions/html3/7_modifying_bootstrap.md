---
title: Modifying Bootstrap
---

<div class='alert alert-error'>
<strong>Warning</strong>: Bootstrap has been designed and heavily tested for good cross-browser compatibility. Unless you know what you're doing or have a lot of time, it's probably best to stick with their layout and tweak small things e.g. fonts and colours. Just because it looks great in your browser doesn't mean it will look great in everyone's!
</div>

If you're going to modify Bootstrap **don't touch the Bootstrap files**. Instead create a new css file of your own to overwrite anything you don't want. This means when a new version of Bootstrap comes out you can upgrade by dragging the new version over the top of the old, without losing any modifications.


{% exercise %}
The red delete buttons make the `profile.html` page look a bit busy. Let's change them so that they only display when we hover over the list item.

1. Create a file called `main.css` and write the following CSS:

        li .btn {
            visibility: hidden;
        }
        li:hover .btn {
            visibility: visible;
        }

2. Link this file into the `head` of `profile.html`.
3. If this were a big project, the above rule might be picked up elsewhere with surprising consequences. What could you do to prevent this?
{% endexercise %} 

### Navbar

Read through the [navbar section](http://twitter.github.io/bootstrap/components.html#navbar) of the Bootstrap docs.

{% exercise %}
1. Add a navbar to `profile.html` with links to 'About' and 'Members'.
2. Make it a `navbar-fixed-top`. You will need to add

        body { padding-top: 40px; }

    to `main.css`.
3. Add a search box to the navbar. Use the `pull-right` class to put it on the right hand side.
4. Check your result against `step5.png`.
{% endexercise %}
