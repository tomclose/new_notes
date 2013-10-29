---
title: Homework
---

### Finishing off

{% exercise %}
Finish off both CSS exercises from class. Check your solutions online:
* Find the HTML2 repository on Code61's github page.
* In the `branch` dropdown (just above the list of files) select the `solution` branch.
* Click on the files below to see the solution
{% endexercise %}

### Revisiting git

{% exercise %}
Read through [Git Immersion](http://gitimmersion.com/lab_01.html) exercises 1 to 11. You don't need to do anything - just check you vaguely understand what they're talking about.
{% endexercise %}

### More HTML/CSS

{% exercise %}
1. Complete the whole of Project 3 on the [General Assembly Dash](https://dash.generalassemb.ly/projects) site.
2. Make some changes to your `first_site` based on what you've learnt. Make sure you add them to git at each stage, and push them up to github:

        $ git add --all
        $ git commit -m "Message to describe the change you made"
        $ git push
        
3. (Optional) Do the projects from the [Codecademy Web Track](http://www.codecademy.com/tracks/web) Sections 7, 8 &amp; 9.
{% endexercise %}

### Get your site online with GitHub Pages

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

    Make sure you only run this command once. To see if it worked you can run `git remote show origin` and check you get something similar to the following

        $ git remote show origin
        * remote origin
        Fetch URL: git@github.com:tomclose/first_site.git
        Push  URL: git@github.com:tomclose/first_site.git
        HEAD branch (remote HEAD is ambiguous, may be one of the following):
          gh-pages
          master
        Remote branches:
          gh-pages tracked
          master   tracked
        Local branch configured for 'git pull':
          master merges with remote master
        Local refs configured for 'git push':
           master forces to gh-pages (up to date)
           master forces to master   (up to date)

    The important bit is the final two lines. 

2. In Sublime Text, make any change to `first_site/index.html` and save. 
3. Commit that change:

        $ git add --all
        $ git commit -m "Made a small change."

4. Push it to GitHub.

        $ git push

5. Check whether it worked:
    1. Go to your `first_site` repository on `GitHub.com`. Under the repo name, above the code, you'll see a box that says `branch: master`. Click on the dropdown and check that you have a `branch: gh-pages` too.
    2. Try to visit your site: go to the settings section (bottom icon on RHS of page), there should be a `GitHub Pages` box where it will tell you where your site is published.
{% endexercise %}


