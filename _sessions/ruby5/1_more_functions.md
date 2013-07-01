---
title: Functions again
---

### Functions of no return

In ruby the return statement is optional. If no return statement is given the function returns the last statement executed.

{% highlight ruby %}
def welcome_message(name)
    "Hello #{name}"
end

welcome_message("Tom") #=> "Hello Tom"

def is_even(n)
    if n.even?
        "#{n} is even"
    else
        "#{n} is odd"
    end
end

is_even(2) #=> "2 is even"
{% endhighlight %}

### Default values

As in other languages, it is possible to specify default values in ruby which will be used if no argument is provided:

{% highlight ruby %}
def welcome_message2(name="World")
    "Hello #{name}"
end

welcome_message2 #=> "Hello World"
welcome_message2("Tom") #=> "Hello Tom"
{% endhighlight %}


### Optional variables

You can also provide optional variables like this:

{% highlight ruby %} 
def say_goodbye(opts={})
    if opts[:grumpily]
        "Oh, you're going. Thank goodness for that."
    else
        "Goodbye. Come again soon!"
    end
end
{% endhighlight %}

{% exercise %}
1. Grab the code for this session:

    git clone https://github.com/TomClose/ruby5.git

2. Er.
{% endexercise %}




