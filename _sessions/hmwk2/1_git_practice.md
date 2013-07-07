---
title: Git Practising!
---

{% exercise %}
Read through [Git Immersion](http://gitimmersion.com/lab_01.html) exercises 1 to 11.
{% endexercise %}

<hr>

{% exercise %}
**Every day this week** make a small change to your `first_site` folder, add, commit and push to GitHub. GitHub should show you as having a '5 day streak' on your homepage.
{% endexercise %}

### Recap on how to push to GitHub

1. Make a change to a file in SublimeText. Save it.
2. On the command line, in your `first_site` folder:

        $ git add --all
        $ git status
        $ git commit -m "Changed heading colours."
        $ git status

    This will add and commit the changes to your *local* repository - the one that lives in `first_site/.git`.
3. Also on the command line, in your `first_site` folder:

        $ git push

    This will take the committed changes and put them up onto the repository on GitHub.