---
title: Variables
---

Like most progamming languages, ruby allows you to store values in within program by assigning them to *variables*.

{% highlight ruby %}
x = 1

y = 2*x

x = 2
{% endhighlight %}

In ruby you don't need to declare your variables anywhere (unlike in some other languages) - by assigning a value to them you bring them into existence. If the variable already holds a value and you reassign it the new value will overwrite the old.

You also don't need to say what sort of object they will hold. This can change over the 'lifetime' of the variable:
{% highlight ruby %}
x = 1
puts x
x = "fish"
puts x
{% endhighlight %}

{% exercise %}
Type the above examples into irb. Note that all the numeric operations and methods work exactly as before. For example, try `y.odd?`.
{% endexercise %}

### An impossible equation

Assignment works by setting the variable on the left to the expression on the right.

{% highlight ruby %}
x = x + 1
{% endhighlight %}

At first the above statement might appear confusing. It looks like it might be an impossible mathematical equation. The equals **isn't like = in maths** - it is an assignment. The statement means 'set the new value of x to be one more than the old value of x'.

### Variable names

Local variables start with a lower case letter. That's all we'll be dealing with for now. They must not have any spaces.

Usual in ruby to use underscored names, e.g. `user_name` or `this_is_a_stupidly_long_variable_name`.

{% exercise %}
    a = 1
    b = 10
    a = b
Which of the following is correct?:
1. The value of a is 1. The value of b is 10.
2. The value of a is 10. The value of b is 10.
3. The value of a is 1. The value of b is 1.
4. None of the above.

If you're not sure, try it out in `irb`!
{% endexercise %}

<hr>

{% exercise %}
[Note: this exercise has a lot more to do with maths than programming. If you don't get it don't worry!]

Consider the expression

	 x = (2 + 5*x - x**2)/5

1. Let `x = 1.1`
2. Write `x = (2 + 5*x - x**2)/5` and then evaluate this multiple times (using the up arrow in irb)
3. What happens? Can you explain why?
4. Let `x = 1` and do the same thing. What happens and why? 
5. (Pointless extension.) Can you find other examples of parts 3 and 4? Can you prove you have all of them?
{% endexercise %}