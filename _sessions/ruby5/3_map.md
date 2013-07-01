---
title: Map & reduce
---


So now we know about functions returning the last thing they executed, what will the following code give?

{% highlight ruby %}
def to_stars_each(array)
    array.each {|n| "*" * n}
end

# what will happen here
to_stars_each([1, 2, 3]) #??=> ['*', '**', '***']
{% endhighlight %}

Unfortunately this doesn't happen. What we actually get is

{% highlight ruby %}
def to_stars_each(array)
    array.each {|n| "*" * n}
end

# this actually happens
to_stars_each([1, 2, 3]) #=> [1, 2, 3]
{% endhighlight %}

**Each returns the object you were interating over, not the result of the iteration.**

Thankfully, there is a way of doing what we want, using a different method called `map`:

{% highlight ruby %}
def to_stars(array)
    array.map {|n| "*" * n}
end

to_stars([1, 2, 3]) #=> ['*', '**', '***']
{% endhighlight %}

Map takes each element of a collection and 'maps' it to a new value, by running the block.

### Introducing reduce

We previously wrote a method to calculate the sum of an array:

{% highlight ruby %}
def sum(array)
    s = 0
    array.each {|n| s += n}
    s
end
{% endhighlight %}

In fact there is a neater way to do this using a function called `reduce`:

{% highlight ruby %}
def sum(array)
    array.reduce(0) {|running_total, n| running_total + n}
end
{% endhighlight %}

Reduce moves along the array calculating a running total. At each stage the block is passed in the current total and the new element, and the result of running the block becomes the new total. The starting total (in this case `0`) is passed in as an argument.

The function is called `reduce` as it moves along reducing the array to a value.

### Map and reduce

Map and reduce together is a very powerful idea. Many operations can be thought of as a map followed by a reduce and writing them in this way allows massive parallelisation across a distributed network of machines.

Google uses map-reduce operations to a huge extent as described in their [map-reduce paper](http://research.google.com/archive/mapreduce.html)

{% exercise %}
1. Open `map_reduce.rb` in Sublime Text
2. Complete the three functions, by using map and reduce as appropriate.
3. Test your solutions with `test_map_reduce.rb`
{% endexercise %}

