---
title: A few checks
---

### Ruby installation

{% exercise %}
In the terminal type:

    ruby --version

If it says you have ruby 1.9 (for example ruby 1.9.3-p387 - the stuff after the 9 doesn't matter) then you're fine. If not, post to the forum.
{% endexercise %}

### Folder structure

This has caused a bit of confusion. Some where on your computer you should have a folder called `coding_course`. The contents should currently look like this:

    coding_course
        |
        |-- first_site 
        |
        |-- learning_html
        |
        |-- html2

A lot of instructions are going to be something like 'go to your `coding_course` folder ...', so it would be best if everyone had the same structure. If your files aren't like this at the moment, let me know and we can sort it out in office hours.

Each of the folders `first_site`, `learning_html` and `html2` should be a git repository. Check this by moving into them and doing

    $ ls -a

you should see a `.git` folder. [The `first_site` one you made into a git repository. The other two you aquired via `git clone`.]

The `coding_course` folder should **not** be a git repository. Check that too. 