---
title: Calling functions
---

Have you ever wondered how `puts` works?

{% highlight ruby %}
puts "Hello Everyone!"
{% endhighlight %}

`puts` is just a *function* that prints to the screen. But if we're calling a function why don't we use `()`?

**In ruby the `()` are optional when calling functions.**

So the `puts` example above is actually just a different way of writing

{% highlight ruby %}
puts("Hello Everyone!")
{% endhighlight %}

This is a nice feature, as it allows you to build expressive interfaces in ruby without the visual clutter of other languages. As a very simple example consider the following:

{% highlight ruby %}
def say_hello_to(name)
    "Hello #{name}"
end

say_hello_to "Tom" #=> "Hello Tom"
{% endhighlight %}

### More lies

There are a few occasions where the two ways aren't equivalent and you do actually need the brackets. As an example take the following function for displaying some information about a hash:

{% highlight ruby %}
def summary(character)
    "#{character[:name]} #{character[:surname]} is #{character[:age]} years old."
end

summary {:name => 'Bart', :surname => 'Simpson', :age => 10}
#=> SyntaxError: (irb):24: syntax error, unexpected tASSOC, expecting '}'

summary({:name => 'Bart', :surname => 'Simpson', :age => 10})
#=> "Bart Simpson is 10 years old."

b = {:name => 'Bart', :surname => 'Simpson', :age => 10}
summary b
#=> "Bart Simpson is 10 years old."
{% endhighlight %}

The reason that it doesn't work without the round brackets is that the function sees the `{}` and thinks you're passing it a block. This really is an edge-case though - don't worry about it until you have a problem! The no-brackets function calling is something that you'll probably use a lot when writing ruby.
