---
title: A bit of magic
---

We're now going to use GitHub Pages to publish your `first_site` folder as a webpage.

Github will host an html site for free for you, through a service called [GitHub Pages](http://pages.github.com/). There are two possibilities for telling github to make your code into a website:

1. Call your repo `yourusername.github.io` when you create it on GitHub
2. Push your site to a branch called `gh-pages`

If you do either of these things GitHub will interpret you repo as a static website and serve it online.

We'll do the second option, even though you don't know what branches are. For the moment, most of this won't make much sense - hopefully it will at some point in the future!

To do the `gh-pages` approach first open the file `first_site/.git/config` in your code editor. This might be tricky, as it is a hidden folder and might not show up in the list when you do `File > Open`. To find out how to do this google "windows show hidden files" or see the trick at the bottom of the page.

It should look something like this:

    [core]
      repositoryformatversion = 0
      filemode = true
      bare = false
      logallrefupdates = true
      ignorecase = true
      precomposeunicode = false
    [remote "origin"]
      url = https://github.com/TomClose/first_site.git
      fetch = +refs/heads/*:refs/remotes/origin/*
    [branch "master"]
      remote = origin
      merge = refs/heads/master

You want to change it so that it looks like this:

    [core]
      repositoryformatversion = 0
      filemode = true
      bare = false
      logallrefupdates = true
      ignorecase = true
      precomposeunicode = false
    [remote "origin"]
      url = https://github.com/TomClose/first_site.git
      fetch = +refs/heads/*:refs/remotes/origin/*
      push = +refs/heads/master:refs/heads/gh-pages
      push = +refs/heads/master:refs/heads/master
    [branch "master"]
      remote = origin
      merge = refs/heads/master

If you're not very good at spot-the-difference you should just be adding the two lines

      push = +refs/heads/master:refs/heads/gh-pages
      push = +refs/heads/master:refs/heads/master

Then save the file. Don't worry about what this means right now.

You will then need to

1. Make any change to your file
2. Add that change:

        $ git commit -a -m "Small change"

3. Push it to GitHub:

        $ git push

it should say that it pushed both to origin/master and origin/gh-pages. After waiting a few minutes for github to get ready, you should be able to see your site at `yourusername.github.io/first_site`.

{% exercise %}
Follow these instructions for your `first_site` folder. That is:

1. Make the necessary changes to `first_site/.git/config`.
2. Make any change to `first_site/index.html` and save. 
3. Commit that change. 
4. Push it to GitHub.

{% endexercise %}

### A cheat to edit the hidden file

If you can't work out how to edit the hidden file in Sublime Text, you can cheat by moving it out of the hidden folder:

1. Navigation to `first_site` on the command line.
2. Move the `config` file out of the `.git` directory:

        mv .git/config ./config

3. Edit the file in Sublime Text, as normal, then save.
4. Move the `config` file back:

        mv ./config .git/config

