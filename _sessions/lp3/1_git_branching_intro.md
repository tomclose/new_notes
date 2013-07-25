---
title: Git branching
---

Quick and easy branching is one of Git's top features. You've already seen some examples of branches (e.g. the solutions branch for the class exercises and the gh-pages branch trick). In this session we'll learn more about branching and when it should be used.

### Why branch?

Branching is a way of holding several different versions of your code in the same repository at one time. It allows you to work on the different versions independently and then merge them back together at a later date.

As a concrete example, suppose you are working on a static website as a team. One member of your team (Bob) wants to try out a different site design, while the rest of you want to continue to work on the site content.

* Bob creates a new branch to try out the new design.
* When he is finished he pushes the new branch up to GitHub.
* Everyone else can then pull down the new branch to have a look.
* If the team like Bob's new design they can merge his branch into the main branch. If not they can discard it or ask him to do some more work.

Branches allow you to quickly try out and share new ideas, without affecting the main version of your code. They allow you to pick and choose which of these experiments you want to use and which to discard. Branches are an invaluable tool when it comes to developing, both in teams and alone.

### Creating a branch

To create a branch you use the `git checkout -b` command. 

    $ git checkout -b redesign

This will create a new branch starting from the current version of your code. You can see this new branch by running

    $ git branch
      master
    * redesign

You will see that you have two branches: `master` and `redesign`. The `*` tells you that you are currently on the `redesign` branch.

The `master` branch is the default branch that is set up when you create the repository. So far all the work you have done has been on your repo's `master` branch.

Another useful tool for viewing the different branches is `gitk`:

    $ gitk --all

This will show you the current state of your repository, including all the different branches. (If you are on a Mac, you should consider downloading [gitx](http://gitx.frim.nl/), which is basically a much nicer version of `gitk`.)

### Switching back and forth

To switch between branches use the `git checkout` command (**without** the `-b`). If you've made any changes to the branch you were on, you will need to add and commit them before you move.

    $ git checkout master
    $ git checkout redesign

{% exercise %}
1. Navigate to the `ruby4` folder on the command line.
2. Add and commit any changes you have made:

        $ git add --all
        $ git commit -m "Work on exercises."

3. Check out the solutions branch and do another `git branch` to check it has worked.

        $ git checkout solutions
        $ git branch

4. Run the `i_have_a_dream` solution

        $ ruby `i_have_a_dream.rb`

    and have a look at `index.html` in your browser.
5. Move back to the master branch.

        $ git checkout master

{% endexercise %}

