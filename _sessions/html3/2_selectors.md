---
title: Selectors and Attributes
---

So far you have used html tags to specify CSS rules. For example,
{% highlight css %}
h2 { 
  fontsize: 40px;
  color: pink;
}
{% endhighlight %}
will turn all your `<h2>` massive and pink.

It is often useful to be able to make CSS rules more specific, so you can apply different styles to different parts of the page. One common way to do this is to target specific html attributes - in particular `id` and `class`.

### The `id` and `class` attributes

HTML tags can have *attributes* which provide additional information about the element. You've aready seen some examples of this:
{% highlight html %}
<a href="http://www.facebook.com">
<img src="cat_pic.png">
{% endhighlight %}
Both `href` and `src` are examples of html attributes. They are written in pairs with their values: `attribute="value"`.

There are some attributes that can be added to any tag. Two examples of these are `id` and `class`:
{% highlight html %}
<h2 id="products_title">Our scrumptious puddings</h2>

<ul id="products_list">
  <li class="product_item">Black forrest gateau</li>
  <li class="product_item">Rasberry lemon swirl cheesecake</li>
  <li class="product_item">Sticky toffee pudding</li>
  <li class="product_item">Death-by-chocolate cake</li>
</uk>
{% endhighlight %}
Both `id` and `class` are used to add some information to the HTML tags. The key difference is that `id` should specify a *unique element on the page*, whereas multiple elements can share the same `class`.

CSS lets you target the `id` and `class` attributes in special ways:
{% highlight css %}
/* make the h2 with id="products_title" purple */
h2#products_title { color: purple; }

/* remove the bullets from all li with class="product_item" */
li.product_item { list-style-type: none; }
{% endhighlight %}
The `id` is targeted by adding `#id_value` to the tag and the `class` is targeted by adding `.class_value` to the tag.

It is also possible to target any items with a given `class` or `id` by leaving out the HTML tag:
{% highlight css %}
/* make any element with id="products_title" purple */
#products_title { color: purple; }

/* make any element with class="product_item blue" */
.product_item { color: blue; }
{% endhighlight %}

<!-- <div class='exercise alert alert-info' markdown="1">
 -->
{% exercise %}
1. If you haven't already, clone the git repository [https://github.com/TomClose/learning_css](https://github.com/TomClose/learning_css) into your `coding_course` folder:

		git clone git://github.com/TomClose/learning_css.git
		
2. If you have previously made changes to the `learning_css` folder, save and commit them:

		git add .
		git commit -m "Description of changes"

3. Switch to the `ex2` branch:

		git checkout ex2

{% endexercise %}



