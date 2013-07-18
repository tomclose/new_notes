---
title: Twitter Bootstrap
---

Last time we looked at how you can use CSS to change the appearance of your site. Making things look good with CSS is a bit of an art, which is only really acquired over time (or not, in my case!). Thankfully there are pre-existing solutions out there to make your life easier.

[Twitter Bootstrap](http://twitter.github.com/bootstrap/) is set of CSS (& Javascript) files, released by the makers of Twitter. It makes a lot easier to produce websites that won't make you want to sick up into your mouth everytime you look at them. We'll now look at adding Twitter Bootstrap to a page.

{% exercise %}
1. Go to the [Bootstrap](http://twitter.github.io/bootstrap) website (notice that it's hosted at github, like your `first_site`) and click the download button.
2. Unzip and copy the `bootstrap` folder into the `html3` folder.
3. Open `profile.html` in Sublime Text and Chrome.
4. Add a link to the twitter bootstrap stylesheet into `profile.html`

         &lt;link href='bootstrap/css/bootstrap.css' rel='stylesheet'&gt;
         

    Note that you're using a relative link to a file two subfolders down.
5. Refresh the page in Chrome. Notice how the fonts have changed.
6. Check your answer against `step1.png`.
{% endexercise %}