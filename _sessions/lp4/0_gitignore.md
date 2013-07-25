---
title: gitignore
---

A few of you have been having problems with your `.DS_Store` when you merge different git branches. The `.DS_Store` is a hidden file that OS X adds to folders, apparently to help the way that Finder works. The `.DS_Store` file doesn't really have anything to do with the website you're building at all. Because of this it shouldn't really be in the git repository.

There are other situations where you don't want to put everything in a folder into the git repository. To cover these situations git has way of excluding certain files from a git repo: the `.gitignore` file.

### Setting up a .gitignore

The `.gitignore` file sits inside a folder and tells git which files/folders not to version control.

To set up a `.gitignore` file to ignore the `.DS_Store` files do the following

1. Open Sublime Text. In a new file write the line

        .DS_Store

2. Save that file in your `landing_page` folder.
3. Remove the version of the `.DS_Store` currently in your repository by doing:

        git rm --cached .DS_Store

4. Do a `git add --all` and a `git commit`.

### Using a global gitignore

It is also possible to set up a global `.gitignore` file on your computer. This is useful for excluding things like the `.DS_Store`, which you will never want in your repository. To do this:

1. Go to your home directory:

        cd ~

    (This might not work on windows. If not, you could put your .gitignore in `/Sites` instead. You will need to replace `~` with `/Sites` throughout these instructions).

2. Open Sublime Text. In a new file put the [standard OS X gitignore](https://github.com/github/gitignore/blob/master/Global/OSX.gitignore) if you're on a mac, or the [standard Windows gitignore](https://github.com/github/gitignore/blob/master/Global/Windows.gitignore) if you're on windows. Save the file in your home directory as `.gitignore`.
3. Configure git to use this gitinore file:

        git config --global core.excludesfile '~/.gitignore'


{% exercise %}
1. Set up a `.gitignore` to ignore `.DS_Store` in your `landing_page` folder.
2. Set up a global gitignore for your operating system.
{% endexercise %}
