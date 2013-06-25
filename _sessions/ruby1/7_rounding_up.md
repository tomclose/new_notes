---
title: Rounding up
---

You should have learn a few things about strings from the last exercise:

### String methods

Ruby strings come with a lot of useful methods, e.g. `upcase`, `downcase`, `reverse`, `capitalize`. These methods return a new copy of the string with the action applied. The underlying string is unchanged.

These methods also exist in a `!` form: `upcase!`, `downcase!`, `reverse!`, `capitalize!`. These are applied to the actual version of the string that you call them on. **They will change the string permanently.** In ruby, the `!` on the end of a method is often a sign that that method could make lasting changes to the object you're calling it on. Sometimes this is what you want, othertimes it isn't. Be warned!

### Multiplying strings

You can multiply strings by numbers:
{% highlight ruby %}
"Tom" * 3
#=> "TomTomTom"
{% endhighlight %}
This is nice but, in my experience, largely useless.

What is interesting is that the multiplication is not commutative:
{% highlight ruby %}
3 * "Tom"
# => Error
{% endhighlight %}
Actually, it probably isn't that interesting. You'll probably never multiply any strings anyway.

### Final exercises

{% exercise %}
1. Open the file `ruby1/advanced_hello.rb` in Sublime Text.
2. Read the desired output and modify the program to make it work.
3. When you're done check your solution by running `ruby test_advanced_hello.rb`
{% endexercise %}

{% exercise %}
1. Open the file `ruby1/divide_cake.rb` in Sublime Text.
2. Read the desired output and modify the program to make it work.
3. When you're done check your solution by running `ruby test_divide_cake.rb`
{% endexercise %}
