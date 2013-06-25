---
title: Arrays
---

Sometimes we don't just want to iterate over numbers:

{% highlight ruby %}
['pizza', 'pasta'].each do |food|
	puts "I love #{food}"
end
{% endhighlight %}

Ruby provides a collection called an array, which can hold a list of objects. Unlike in some other languages in ruby you don't need to specify which sort of object the array will hold - it can even hold objects of different types.

Arrays are written with square brackets.
{% highlight ruby %}
my_array = [1,2,3]

empty_array = []    # an array with no elements
{% endhighlight %}


{% exercise %}
With your partner work through the file `array_ops.rb`. See if you can guess what each line does, then check in irb.
{% endexercise %}