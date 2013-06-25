---
title: Iterators
---

The following bit of ruby code will print out the numbers 3, 6, ... , 36:
{% highlight ruby %} 
(1..12).each { |number| puts 3 * number }
{% endhighlight %}

Let's split this up into its different pieces:
* `(1..12)` is a `Range` representing the numbers 1 to 12
* `.each` is a method on that `Range` that pulls out the numbers one-by-one
* `{ |number| puts 3 * number }` is a **block**. After pulling a number out of the range the `each` method gives it to the block, which executes the code inside on that number.

Blocks are a very powerful tool in ruby. A different way of thinking about the above example is, instead of considering `each` as passing values to the block, to consider the block as passing code into the `each` to change its behaviour. Blocks allow you to write functions that accept code to be executed later.

### Blocks

There are two ways of writing blocks in Ruby:

{% highlight ruby %} 
(1..12).each { |number| puts 3 * number }

# or 

(1..12).each do |number|
	puts 3 * number
end
{% endhighlight %}

The two ways are completely equivalent. The second is useful when your code inside the block becomes more complicated (more than a couple of lines). 

Both of them declare the block parameters inside vertical bars `|number|`. Just like function parameters, when a value is passed to the block it is set to be this variable.

{% exercise %}
1. Grab the code for this session:

		git clone https://github.com/TomClose/ruby3.git

2. Open `squares.rb` in Sublime Text
3. Rewrite the function to use the `do .. end` block syntax
4. Change the function to accept a parameter i.e so `display_squares(3)` displays 1, 4, 9.
5. Check the function by running `test_squares` in the console.
{% endexercise %}

{% exercise %}
1. Open `triangles.rb` in Sublime Text
2. Complete the function `display_triangles`
3. Check the function by running `test_triangles`

{% endexercise %}
