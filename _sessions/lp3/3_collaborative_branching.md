---
title: Collaborative branching
---

### About remotes

A git remote stores the location of another repository. It is possible to have mutiple remotes for a single repositry. You can see a list of the remotes by running the command

    $ git remote -v
    origin  git@github.com:tomclose/git_test.git (fetch)
    origin  git@github.com:tomclose/git_test.git (push)

The default remote is called `origin`. When you clone a repository it will automatically set up the `origin` to point to the repository (e.g. on GitHub) that you cloned it from and will use this for future `pull` operations.

You can add a remote by using the `git remote add` command:

    $ git remote add origin git@github.com:my_username/my_repo.git

You might recognise this - it's the first of the two lines you use when you push an existing repository up to github!

### Pushing up a branch

Once you have a remote you can push your branches up. The following command will push the `master` branch up to the `origin` (**for the first time**):

    $ git push -u origin master
    Counting objects: 3, done.
    Writing objects: 100% (3/3), 216 bytes, done.
    Total 3 (delta 0), reused 0 (delta 0)
    To git@github.com:tomclose/git_test.git
     * [new branch]      master -> master

We will say more about the `-u` bit on the next page - it basically sets things up so that `git pull` and `git push` will work automatically. If you make some changes and want to push them up (after the first time) you just need to do

    $ git push

and it will know what to do.

### Working on someone else's branch

In this section we will be talking about three different types of branches:

* **remote branches**: these exist in the remote repository.
* **remote-tracking branches**: these exist on your local machine. They mirror the states of the remote branches exactly.
* **local branches**: these exist on your local machine. They are the branches that you can work on directly.

Before you work on someone else's (remote) branch you have to get it from the remote repository. To do this you need to use the `git fetch` command. By default this will fetch all the remote branches from the `origin` remote.

    $ git fetch

All the remote branches will be pulled down into 'remote-tracking' branches. You can see these by doing:

    $ git branch --all
    * master
      remotes/origin/HEAD -> origin/redesign
      remotes/origin/master
      remotes/origin/redesign

The remote-tracking branches are the ones that start `remotes/origin`. Remote-tracking branches are special - they exist only to store the branches from the remote repository. You can't do any work on them directly. If you want to work on one of these branches you first need to create a local branch. To do this use the `git checkout` command:

    $ git checkout redesign
    Branch master set up to track remote branch redesign from origin.
    Switched to a new branch 'redesign'

Normally this would switch to the local `redesign` branch. As you don't have a local `redesign` branch, git does a clever thing: it sees you have a `remote/origin/redesign` and so creates a local branch from that instead. You can see this by doing a `git branch --all`:

    $ git branch --all
      master
    * redesign
      remotes/origin/HEAD -> origin/redesign
      remotes/origin/master
      remotes/origin/redesign

You can then work on this branch. To push your changes to the branch back to the repository just do

    $ git push

(with the `redesign` branch open).

{% exercise %}
1. In your `landing_page` folder, try the following commands:

        $ git remote -v
        $ git branch --all

2. Choose one person in your team. Everyone in the team watch while they create a branch called `gh-pages` and push it to GitHub:

        # (starting on the master branch)
        $ git checkout -b gh-pages
        $ git push -u origin gh-pages

3. Everyone else in the team should then pull this branch down and check it out:

        $ git fetch
        $ git checkout gh-pages

4. Get someone on your team to check out the `master` branch and do some work on it. They should then add, commit and push their work.
5. Get another member of your team to pull their changes, merge them into `gh-pages` and then push the `gh-pages` branch up.
{% endexercise %}

