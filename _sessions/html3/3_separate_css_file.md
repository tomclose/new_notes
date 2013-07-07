---
title: Linking to an external stylesheet
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
1. If you have previously made changes to the `learning_css` folder, save and commit them:

		git add .
		git commit -m "Description of changes"

2. Switch to the `ex3` branch:

		git checkout ex3

3. Check you can see where the CSS file is linked in.
4. Check that changes you make to the CSS file are reflected in the browser.

{% endexercise %}

{% exercise %}
Give a html page and two stylesheets in different locations. Get them to link them in. (Order matters.)
Give an html page with css in the head. Get them to separate it.
{% endexercise %}





