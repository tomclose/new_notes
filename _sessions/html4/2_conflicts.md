---
title: Conflicts
---

The version on your laptop is stored in a fully functional git repository: you can make changes to the site and commit it if you want. What happens if we both make changes at the same time?

Open `toms_site/index.html` in your code editor, and change the page heading (inside `<h1>`) to something of your choosing. (At the same time I'll also make a change). When you're done, commit your change to the local repository:

    git add .
    git commit -m "Changed heading"

I'll push my change up and you pull it down:

    git pull

You should now have a message telling you that you have a merge conflict. This is because our two changes have been made at the same time, so git is unabled to work out which is the up-to-date one to keep. If you look in your file you should see things that look like


    <<<<<<< HEAD
        <h1 class="special">My Page</h1>
    =======
        <h1 class="special">Tom C's page</h1>
    >>>>>>> d76d5a62894057f9c5a4dce0fe5f25110eddd24f


To fix the merge conflict you need to edit this by hand, picking the version you want and then do:

    git add .
    git commit -m "Fixed conflicts"