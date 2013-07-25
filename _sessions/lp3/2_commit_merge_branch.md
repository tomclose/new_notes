---
title: Committing and merging
---

We've seen how to create a branch and how to move between branches. In this section we look at how to add code to a branch and how to combine two branches.

### Committing to a branch

You've actually done this loads of times before. What you before thought of as 'committing to the repository' was actually 'committing to a branch in the repository'. In particular, you were committing to the default `master` branch.

    $ git add --all
    $ git commit -m "Made commits to new design"

You use `gitk` to view the new state of the repository.

### Merging branches

Merging is the process by which you take the changes you've made on one branch and incorporate them into another. To merge:

1. You need to be on the branch that you want to incorporate the changes into.
2. Use the `git merge` command specifying the branch that you want to bring in.

For example to merge `redesign` into `master`:

    $ git checkout master
    $ git merge redesign

This might work straight away or you might have a merge conflict to fix. You do this just like when using `git pull`:

* First fix the files, taking out the `<<<<` bits. 
* Add and commit the changes.

### Deleting branches

After you've merged in a branch you might want to delete that branch, to keep things tidy. To do this do

    $ git branch -d redesign

If you haven't already merged the branch it won't let you delete it. If you really want to get rid of it you can use `-D` instead of `-d`, but this will remove the work in the branch for good!

{% exercise %}
1. Make a new folder called `branching_test` in your `coding_course` folder.
2. Set it up as a git repository: in the `branching_test` folder run

        $ git init

3. Add an `index.html` with some simple text in it. Save, add and commit:

        $ git add --all
        $ git commit -m "Initial commit"

4. Create a new branch called `redesign`:

        $ git checkout -b redesign

5. Add a new file called `about.html` with some simple text in it. Save and and commit (on the redesign branch):

        $ git add --all
        $ git commit -m "Added about.html"

6. Checkout `master`. Notice how `about.html` has gone.

        $ git checkout master

    You might also want to try `gitk` at this point.
7. Merge `redesign` into `master`. Notice that you should now see `about.html` in the same folder.
8. Delete the `redesign` branch.
{% endexercise %}
