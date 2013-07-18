---
title: External stylesheets
---

So far you have written your CSS rules directly in the `head` section of your html page:

{% highlight html %}
<!DOCTYPE html>
<html>
  <head>
  	<title>My page</title>
  	<style type="text/css">
  	  h1 { color: red; }
  	</style>
  </head>

  <!-- body goes here -->

</html>
{% endhighlight %}

We did this to make your first experiments with CSS quick an easy. In a live site it is considered bad practice to put your CSS inside the `head` section: Typically a site will have one set of styles that apply to all the pages. By separating these CSS rules into their own file you (a) reduce repetition in your code and (b) reduce the amount of information that has to be sent to the browser for each page - if the CSS file applies to the whole site, it only needs to be sent to the visitor once.

To link to an external CSS file you can do the following:
{% highlight html %}
<!DOCTYPE html>
<html>
  <head>
  	<title>My page</title>
  	<link rel='stylesheet' type='text/css' href='path/to/my_css_file.css'>
  </head>

  <!-- body goes here -->

</html>
{% endhighlight %}

{% exercise %}
1. Move to your `coding_course` folder and clone the repository for this session:

         git clone https://github.com/code61/html3.git

2. Open `exercise1.html` in Sublime Text and Chrome.
3. Link in the external stylesheet `exercise1.css`. Save, add and commit. Make sure the results show up in Chrome when you refresh.
4. Open `exercise2.html` in Sublime Text and Chrome.
5. Move the css from the `head` into a separate stylesheet, which you should call `exercise2.css`. Link to this stylesheet in the head.
6. Create another stylesheet called `exercise2-custom.css`.
7. In this stylesheet write:

        .color-info { border: 5px dotted purple; }

8. Link in this stylesheet too, so that the changes take effect.
9. If you have time, move any styles you have added to your `first_site` into a separate stylesheet.
{% endexercise %}
