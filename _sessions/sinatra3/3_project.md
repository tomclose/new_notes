---
title: Project
---

The aim of this project is to create a course profiles site, similar to [this one](http://cfg-profiles.herokuapp.com/).

{% exercise %}
1. Fork the project at [https://github.com/code61/sinatra_project3](https://github.com/code61/sinatra_project3).
2. Clone your fork down onto your laptop.
3. You will need to work out how to read in the data from a CSV file. Take a look at the [ruby 3](/ruby3) session, or search for something like "ruby read csv".
4. Create a list of all the course members at the root url `/`.
5. Create a page for each member. You will need to decide which property of the user to put in the url, that you will later use to look them up. Link to these pages from the list you made in stap 4.
{% endexercise %}

### Displaying using if

You might find the following technique useful:

{% highlight ruby %}
<% if @user['Role']=='Teaching staff' %>
    <p>This person is on the course staff</p>
<% end %>
{% endhighlight %}

This the `<p>` block will only be displayed if `@user['Role']` is `'Teaching staff'`.