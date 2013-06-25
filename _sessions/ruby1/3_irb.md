---
title: Interactive ruby
---

One of the great things about an interpreted language is that it's often possible to interact with the interpreter in real time.

{% exercise %}
On the command line type `irb` to enter an interactive ruby session.
{% endexercise %}

Irb stands for **i**nteractive **r**u**b**y. You can write ruby code in it and it will evaluate it.

{% exercise %}
Write `2 + 2` into irb and press enter.
{% endexercise %}

You should see something like the following:

{% highlight irb %}
001: > 2 + 2
 => 4 
002: > 
{% endhighlight %}

`2 + 2` is a ruby *expression*. The `=>` symbol tells you what this expression evaluates to. If you try just typing `4` at the irb prompt, you will see that `4` is an expression that evaluates to itself.

{% exercise %}
1. Open the file `ruby1/arithmetic.rb` in Sublime Text
2. For each expression:
	1. See if you guess what it will evaluate to.
	2. Try it in irb to check.
3. If you have time, move on to the challenge at the end of the file.
{% endexercise %}

