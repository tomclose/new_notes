---
title: Blocks
---

Blocks are a really useful and powerful feature of the ruby language. They allow you to pass an extra bit of code into an operation. Consider the following example:

{% highlight ruby %}
['pizza', 'pasta'].each { |food| puts "I love #{food}" }
{% endhighlight %}

Let's split this up into its different pieces:
* `['pizza', 'pasta']` is an `Array` containing two words
* `.each` is a method on that `Array` that pulls out the numbers one-by-one
* `{ |food| puts "I love #{food}" }` is a **block**. After pulling a word out of the array the `each` method gives it to the block, which executes the code inside on that word.

Blocks are a very powerful tool in ruby. A different way of thinking about the above example is, instead of considering `each` as passing values to the block, to consider the block as passing code into the `each` to change its behaviour. Blocks allow you to write functions that accept code to be executed later.

### Ways of writing blocks

There are two ways of writing blocks in Ruby:

{% highlight ruby %} 
['pizza', 'pasta'].each { |food| puts "I love #{food}" }

# or 

['pizza', 'pasta'].each do |food|
    puts "I love #{food}"
end
{% endhighlight %}

The two ways are completely equivalent. The second is useful when your code inside the block becomes more complicated (more than a couple of lines). 

Both of them declare the block parameters inside vertical bars `|food|`. Just like function parameters, when a value is passed to the block it is set to be this variable.


