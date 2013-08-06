---
title: Sinatra layouts
---


One of the most important principles in software engineering is [DRY](http://en.wikipedia.org/wiki/Don't_repeat_yourself): **don't repeat yourself**.

The basic idea is that you don't want to be copying and pasting the same code into multiple places. If you're doing this, you're making a lot of work for yourself should you ever decide to change that code.

One way that we've already met of staying DRY is writing functions: if there's a task that you do repeatedly, write a function to put the logic for that task in one place and then call the function when you need to do the task.

Another way, that we'll be looking at today, is in the form of layouts.

### The Problem

So far you've been writing a lot of erb view templates. Here are some examples:

{% highlight html %}
<!-- in views/index.erb -->
<!DOCTYPE html>
<html>
<head>
    <title>Greetings</title>
    <!-- Latest compiled and minified CSS -->
    <link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.0.0-rc1/css/bootstrap.min.css">
</head>
<body>
    <div class='container'>
        <h1>Hello everyone!</h1>
    </div>
</body>
</html>
{% endhighlight %}

{% highlight html %}
<!-- in views/greet.erb -->
<!DOCTYPE html>
<html>
<head>
    <title>Greetings</title>
    <!-- Latest compiled and minified CSS -->
    <link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.0.0-rc1/css/bootstrap.min.css">
</head>
<body>
    <div class='container'>
        <h1>Hello <%= @name %>!</h1>
    </div>
</body>
</html>
{% endhighlight %}

Notice that these files are almost the same - a lot of copy and paste has gone on.

### The solution

Sinatra gets round this problem by allowing you to have a `layout.erb` file in your `views` folder:

{% highlight html %}
<!-- views/layout.erb -->
<!DOCTYPE html>
<html>
<head>
    <title>Greetings</title>
    <!-- Latest compiled and minified CSS -->
    <link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.0.0-rc1/css/bootstrap.min.css">
</head>
<body>
    <div class='container'>
        <%= yield %>
    </div>
</body>
</html>
{% endhighlight %}

You can then write only the bits that change in the other two views:

{% highlight html %}
<!-- in views/index.erb -->
<h1>Hello everyone!</h1>
{% endhighlight %}

{% highlight html %}
<!-- in views/greet.erb -->
<h1>Hello <%= @name %>!</h1>
{% endhighlight %}

Sinatra knows that if you have a file called `layout.erb` it should use that as a layout. If you call `erb :index`:

* It takes the `layout.erb` file.
* It finds the bit where it says `<%= yield %>`.
* It inserts `index.erb` at that point.

You can find more about Sinatra layouts on [the internet](http://lmgtfy.com/?q=sinatra+layouts).

