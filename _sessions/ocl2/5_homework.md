---
title: Homework
---

{% exercise %}
Read through [Git Immersion](http://gitimmersion.com/lab_01.html) exercises 1 to 11.
{% endexercise %}


## Get your site online with GitHub Pages

We're now going to use GitHub Pages to publish your `first_site` folder as a webpage.

Github will host an html site for free for you, through a service called [GitHub Pages](http://pages.github.com/). There are two possibilities for telling github to make your code into a website:

1. Call your repo `yourusername.github.io` when you create it on GitHub
2. Push your site to a branch called `gh-pages`

If you do either of these things GitHub will interpret you repo as a static website and serve it online.

We'll do the second option, even though you don't know what branches are. For the moment, most of this won't make much sense - hopefully it will at some point in the future!

To do this we need to set some configuration options for the repository:

    $ git config remote.origin.push +refs/heads/master:refs/heads/master --add
    $ git config remote.origin.push +refs/heads/master:refs/heads/gh-pages --add

You will then need to

1. Make any change to your file
2. Add that change:

        $ git commit --all
        $ git commit -m "Small change"

3. Push it to GitHub:

        $ git push

it should say that it pushed both to origin/master and origin/gh-pages. After waiting a few minutes for github to get ready, you should be able to see your site at `yourusername.github.io/first_site`.

{% exercise %}
Follow these instructions for your `first_site` folder. That is:

1. Set your repository up to push to the gh-pages branch. In your `first_site` folder run:

        $ git config remote.origin.push +refs/heads/master:refs/heads/master --add
        $ git config remote.origin.push +refs/heads/master:refs/heads/gh-pages --add

2. In Sublime Text, make any change to `first_site/index.html` and save. 
3. Commit that change:

        $ git add --all
        $ git commit -m "Made a small change."

4. Push it to GitHub.

        $ git push

{% endexercise %}


