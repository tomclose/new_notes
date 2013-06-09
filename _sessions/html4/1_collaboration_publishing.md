---
title: Getting code from Github
---

In previous sessions we've used git to pull code down from github. We're going to start this session by doing the same again:

{% exercise %}
1. Go to the command line and navigate to your `coding_course` folder
2. Clone the project [https://github.com/TomClose/first_site2]():

     	 git clone git://github.com/TomClose/first_site2.git toms_site

{% endexercise %}

You should now see a new file called `toms_site` in your `coding_course` folder, and be able to open `toms_site/index.html` in your browser. The clone operation has copied a local version of the repository onto your computer.

Git will help you keep this local copy updated. If I've made some changes and pushed them up to github, you just need to run

    git pull

to pull them down onto your laptop.

{% exercise %}
1. Wait for me to make a change and push it to gihub
2. Pull down the changes and make sure you can see them in your browser:

		git pull
{% endexercise %}