---
title: "Collaboration: Publishing model"
---

Last time we looked at pushing your code up to github. Push up the changes you've just made to your site:

    cd first_site
    git add .
    git commit -m "Added twitter bootstrap"
    git push

You can think of this code as being published on github for others to read. This brings us to our first way of collaborating with others: the publishing model.

In the publishing model one person pushes their work to github, and others pull it down and use it. To do this in practice you need to use the `git clone` command:

    cd coding_course
    git clone git://github.com/TomClose/first_site.git toms_site

You should now see a new file called `toms_site` in your `coding_course` folder, and be able to open `toms_site/index.html` in your browser. The clone operation has copied a local version of the repository onto your computer.

Git will help you keep this local copy updated. If I've made some changes and pushed them up to github, you just need to run

    git pull

to pull them down onto your laptop.