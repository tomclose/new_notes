---
title: More on remote branches
---

The material on this page is purely to explain remote branches in slightly more detail. Feel free to ignore it if you've heard enough already!

### Pulling and upstream branches

We've essentially seen two ways of getting information from one branch into another:

* `git pull` incorporates the contents of a remote branch into your current branch.
* `git merge` incorporates the contents of a local branch into your current branch.

In fact, `git pull` is really built using `git merge`. The following two things are (roughly) equivalent:

    (on branch master)
    $ git pull

    $ git fetch
    $ git merge origin/master

A `pull` is just a `fetch` followed by a `merge` with a remote-tracking branch.

Unfortunately this doesn't quite make sense: when we do the `fetch`+`merge` we specify which branch to merge; when we do the git pull we don't. How does git know which branch to fetch and merge when you do the pull?

When doing a pull, git will automatically fetch and merge your current branch's *upstream branch*. Consider the following chain of events:

    (in an existing git repository)
    $ git remote add origin git@github.com:tomclose/git_test.git
    $ git push -u origin master
    $ git push origin redesign

First we set up the remote repository `origin`. We then push master to the origin with the `-u` flag. This sets the upstream of our `master` to be `origin/master`. We then push `redesign` to the `origin`. This doesn't set the upstream. You can see what this has done with the `git remote show` command:

    $ git remote show origin
    * remote origin
      Fetch URL: git@github.com:tomclose/git_test.git
      Push  URL: git@github.com:tomclose/git_test.git
      HEAD branch: master
      Remote branches:
        master   tracked
        redesign tracked
      Local branch configured for 'git pull':
        master merges with remote master
      Local refs configured for 'git push':
        master   pushes to master   (up to date)
        redesign pushes to redesign (up to date)

There are two remote branches on the `origin`. We're tracking both of them (i.e. we have remote-tracking branches for each). Our local `master` branch knows to push to the remote `master` and merge from the remote `master`. The local `redesign` branch only knows to push to the remote `redesign`. It doesn't know about merging.

Let's see what happens when we try to pull:

    (after checking out redesign)
    $ git pull
    There is no tracking information for the current branch.
    Please specify which branch you want to merge with.
    See git-pull(1) for details

        git pull <remote> <branch>

    If you wish to set tracking information for this branch you can do so with:

        git branch --set-upstream redesign origin/<branch>

It doesn't know what to do.

We can fix this using the command:

    $ git branch -u redesign origin/redesign

In summary, the following two things are equivalent:

    $ git push -u origin redesign

    $ git push origin redesign
    $ git branch -u redesign origin/redesign

### Checking out remote branches

Another thing that set the upstream on the branch was using `git checkout` to get a local version of a remote branch.

Say we're in the following state:

    $ git branch --all
    * master
      remotes/origin/HEAD -> origin/redesign
      remotes/origin/master
      remotes/origin/redesign

we have a local and remote `master` branch, but only a remote `redesign` branch. The following three sets of commands are then equivalent:

    $ git checkout redesign

    $ git checkout --track redesign origin/redesign

    $ git checkout redesign origin/redesign
    $ git branch -u redesign origin/redesign

This is useful to know because it allows you to call your local branches something different e.g.

    $ git checkout --track bobs_redesign origin/redesign

which you wouldn't be able to do with the first version. This becomes most useful if you have several remotes - if you only have `origin` it makes most sense to keep the names the same.