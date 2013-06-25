---
title: Numbers in ruby
---

Over the course of the last exercise you learnt a few things about numbers in ruby.

### Brackets

Ruby follows the standard laws of arithmetic when it comes to brackets:
{% highlight irb %}
> 2 + 5 * 3
=> 17
> (2 + 5) * 3
=> 21
{% endhighlight %}

### Division

If you divide integers (whole numbers) in ruby you might not get the answer you expected:
{% highlight irb %}
> 5 / 2
=> 2
{% endhighlight %}

This is pretty standard in a lot of programming languages. The sum is interpreted to mean 'how many times will 2 go into 5', i.e. two whole times, with a remainder of one. You can use `%` to find the remainder:
{% highlight irb %}
> 5 % 2
=> 1
{% endhighlight %}

If you want your answer to be a decimal at least one of the numbers in the division must be a decimal:
{% highlight irb %}
> 5.0 / 2
=> 2.5
> 5 / 2.0
=> 2.5
{% endhighlight %}

### Numbers as objects

Ruby is a 'true object orientated' language - pretty much everything is an *object*. We will talk more about object orientated programming in later sessions, but for now you should accept that this is (a) slightly unusual for a programming langauge and (b) lots of fun!

Numbers are no exception: they are objects and therefore have *methods* that you can call on them. Whereas in other languages you might have to do `Math.even?(5)`, in ruby you can essentially ask the number itself whether it is even or not:
{% highlight irb %}
> 5.even?
=> false
> 5.odd?
=> true
{% endhighlight %}

{% exercise %}
In irb,
1. Try `5.class`, to see what sort of object `5` is.
2. Compare this to `5.0.class`.
3. Try `5.methods`, to see what other methods you can call on `5`.
4. Try out a few of these methods (e.g. `5.abs`, `5.real?`, `5.between?(3,6)`)
{% endexercise %}