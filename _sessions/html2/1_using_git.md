---
title:  "Intro to Git"
---

Git is a version control system. It allows you to keep the entire history of your code, and makes it easy to share and collaborate with others.

### Setting up a git repo

Git works on a folder level. To set up a folder to work with git you need to navigate to that folder in the command line and run.

    $ git init

To see what this has done do:

    $ ls -a

The `-a` is a flag which tells the `ls` command to show hidden files and folders. You should see a folder called `.git` in the results. If you want you could move into this folder, and have a look around (and then move out again).

    $ cd .git
    $ ls
    $ cd ..

All the data to allow git to version control your code will be stored inside this hidden folder. If you ever want to 'un-version-control' your code all you have to do is delete this folder.

### Adding files to the repository

Suppose we've now created a file called `index.html` in the folder. It's in the folder but currently isn't being tracked by git. You can see this by doing `git status`:

    $ git status

    # On branch master
    #
    # Initial commit
    #
    # Untracked files:
    #   (use "git add <file>..." to include in what will be committed)
    #
    #   index.html
    nothing added to commit but untracked files present (use "git add" to track)

Adding files to a git repository is actually a two-stage process: you have to **add** them and then **commit** them. This is useful when you get more advanced, but we'll usually do those things together for the time being. To add the changes to the repository do:

    $ git add --all
    $ git status

    # On branch master
    #
    # Initial commit
    #
    # Changes to be committed:
    #   (use "git rm --cached <file>..." to unstage)
    #
    #   new file:   index.html
    #

It is possible to add files one at a time - again, useful when you get more advanced. For the time being the `--all` flag tells git to add everything to the folder. In other tutorials you might see `git add .`. This also adds everything in the folder **but doesn't remove files you have deleted**. I'd encourage you to stick with `git add --all` for the time being.

We will now commit these changes to our repository, along with a description of the changes we have made.

    $ git commit -m "Created index.html"

    [master (root-commit) e91b6be] Created index.html
    0 files changed
    create mode 100644 index.html

Warning: if you forget to supply a message with the `-m` tag git will drop you into a text editor (probably vim) so that you can write one. If this happens you will need to do the following:
* Press `i` to get into insert mode, so you can write.
* Write your message.
* Press `esc` then `:` then `wq` then `Enter`.
* Never forget your message again.

You can check that the commit worked with git status:

    $ git status

    # On branch master
    nothing to commit (working directory clean)

You can see your commit by doing 

    $ git log

    commit c63f9bbea211a0240fa1b13287a2aaf5a6d8d81a
    Author: Tom Close <tom.close@example.com>
    Date:   Tue Jul 2 14:19:30 2013 +0100

        Created index.html

or you can get a nice diagram showing your repo by doing

    $ gitk --all

{% exercise %}
Enable your `first_site` folder as a git repository:
1. Navigate to the `first_site` folder in the command line
2. Type 

        $ git init

3. Do a git status to see what it says

        $ git status

4. Commit your changes to the repository:

        $ git add --all
        $ git commit -m "Created index.html"

5. Do a git status and then a git log to see what has happened:

        $ git status
        $ git log

6. Make some change to index.html (in Sublime Text)        
7. Go back to the command line and do a git status:

        $ git status

8. Commit your changes but forget the `-m`:

        $ git commit

9. Use the warning above to add you commit message and escape from vim

{% endexercise %}