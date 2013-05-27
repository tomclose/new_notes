---
title: Twitter Bootstrap
---

Last time we looked at how you can use CSS to change the appearance of your site. Making things look good with CSS is a bit of an art, which is only really acquired over time (or not, in my case!). Thankfully there are pre-existing solutions out there to make your life easier.

[Twitter bootstrap](http://twitter.github.com/bootstrap/) is set of CSS (& Javascript) files, released by the makers of twitter. It makes a lot easier to produce websites that won't make you want to sick up into your mouth everytime you look at them. We'll now look at adding twitter bootstrap to your `first_site/index.html` page (you should have renamed your page to this as part of the homework).

To start with go to the [twitter bootstrap](http://twitter.github.com/bootstrap) website (notice that it's hosted at github, like ours is!) and click the download button. When you've downloaded and unzipped the file, copy the `bootstrap` folder into your `first_site` folder.

When we covered CSS last time I mentioned that there are a few different ways of including it in your webpage. We did it by putting the css inside a `<style>..</style>` tags in the `<head>` of your page. This time we're going to do it by linking to a separate css file. This is more efficient, as it means that when someone's browsing your site they don't have to download the css file for each new page. In the head section of your `first_site/index.html` put the following line:

{% highlight html %}
<link href='bootstrap/css/bootstrap.css' rel='stylesheet'>
{% endhighlight %}

You can also remove the `<style>..</style>` tags and delete your css from last time if you want.

When you go to your browser and press refresh, things should look slightly better - bootstrap chooses slightly nicer fonts than the browser does by default. To get the full effects of bootstrap we need to tweak our html.