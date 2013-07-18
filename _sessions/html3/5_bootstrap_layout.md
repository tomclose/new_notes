---
title: Bootstrap layout
---

Bootstrap gives you several options on how to layout your page. To find out more take a look at the [Scaffold docs](http://twitter.github.io/bootstrap/scaffolding.html) on the Bootstrap site. Some of these options will work out-of-the-box with *responsive design* - so that you can create a single html page which will look good whether viewed on a laptop, tablet or phone.

We'll just look at a few of the most important layout options here:

### Page margins

Bootstrap makes it easy to center content on your page and provide sensible page margins. To do this make use of the `container` class:

{% highlight html %}
<body>
  <div class="container">

    <!-- page content goes here -->

  </div>
</body>
{% endhighlight %}

### Columns

Bootstrap works on a grid layout, with 12 columns (by default). You can create a column layout with the `row` and `span` classes:

{% highlight html %}
<div class='row'>
    <div class='span3'>
        <!-- First column content -->
    </div>
    <div class='span5'>
        <!-- Second column content -->
    </div>
    <div class='span4'>
        <!-- Third column content -->
    </div>
</div>
{% endhighlight %}

The number after the `span` determines how many of the 12 grid columns that page column takes up.

{% exercise %}
1. Add a `&lt; div class="container" &gt;` around the page content.
2. Set the page up as two columns (ratio 1:2), with the `profile_details` div on the left and everything else on the right.
3. Check your solution matches `step2.png`.
{% endexercise %}