---
title: Blocks with arrays
---

There are four important array methods that you should know that accept blocks: `each`, `map`, `select` and `sort`.

### Each

Each is a way of *iterating* over an array: it pulls values out of the array one-by-one and passes them to the block.

{% highlight ruby %}
[1,2,3].each do |number|
    puts "#{number} x 12 = #{number * 12}"
end
{% endhighlight %}

### Map

Map is very like each, with one key difference:

* `each` returns the original array.
* `map` returns a new array with the values replaced by the value of the block execution.

{% highlight ruby %}
[1,2,3].each {|n| 2 * n }  #=> [1,2,3]

[1,2,3].map {|n| 2 * n }  #=> [2,4,6]
{% endhighlight %}

**Map maps the array onto a new array.**

### Select

Select is a way of selecting certain values from an array. It keeps only those values for which the block evaluates to `true`.

{% highlight ruby %}
[3, 2, 1].select {|x| x < 2} #=> [1]

['apple', 'banana', 'pear'].select { |w| w.length <= 5 } #=> ['apple', 'pear']
{% endhighlight %}

### Sort

Sort is used to sort an array. It is probably the most complicated method of the 4.

{% highlight ruby %}
# sort by size
[3, 2, 1].sort #=> [1,2,3]

# sort alphabetically
['apple', 'pear', 'banana'].sort #=> ['apple', 'banana', 'pear']

# sort by length, by providing a block
['apple', 'pear', 'banana'].sort do |a, b|
    if a.length > b.length
        1
    elsif a.length == b.length
        0
    else
        -1
    end
end
{% endhighlight %}

Sort has some sensible defaults for numbers and words. If you want to do a custom sort you need to provide a block that takes two parameters. The block you pass to sort should return:

* `1` if the first parameter is bigger than the second
* `0` if the first parameter is equal to the second
* `-1` if the first parameter is smaller than the second

There's a special operator that will help you do this: `<=>`. For example, the final example can be rewritten:

{% highlight ruby %}
# sort by length, by providing a block
['apple', 'pear', 'banana'].sort { |a, b| a <=> b }
{% endhighlight %}

{% exercise %}
1. Open `array_block_exercises.rb` in Sublime Text.
2. Complete as many of the functions as you can.
3. Check the function by running `test_array_block_exercises`.

{% endexercise %}