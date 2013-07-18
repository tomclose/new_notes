---
title: Functions of no return
---


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