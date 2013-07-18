---
title: More about hashes
---

In the last exercise you will have learnt a number of things about hashes. Here is a summary of the important points:

### Accessing and setting elements

{% highlight ruby %}
h = {'one' => 1, 'two' => 2, 'three' => 3}

h['one'] #=> 1
h['four'] #=> nil

h['five'] = 5
h['one'] = 1.0

h #=> {'one' => 1.0, 'two' => 2, 'three' => 3, 'five' => 5}
{% endhighlight %}

* You access an element via its key: `h['one']`
* If the key isn't in the hash this will give `nil`
* You add new elements by setting their key
* If the key already exists its value will be updated

### Methods

Hashes have a number of methods, which behave as you would expect e.g.

* `length`
* `empty?`
* `keys`, `values`
* `has_key?`, `has_value?`

### Iterating

Just like an Array, you can iterate over a Hash using the `each` method. Unlike array iteration, in hash iteration the block accepts two parameters: the key and the value:

{% highlight ruby %}
h = {'one' => 1, 'two' => 2, 'three' => 3}

h.each do |key, value|
	puts "#{key} = #{value}"
end
{% endhighlight %}

### Combining hashes

Combining hashes is done by using the `merge` method. The values from the second hash are added to the first, replacing them if they already exist. You will often see this used in rails for specifying default options to a function:

{% highlight ruby %}
def print_names(opts)
	default_opts = {'fancy_format' => true, 'max_length' => 20}

	# replace the defaults with options supplied
	my_opts = default_opts.merge(opts) 

	if my_opts['fancy_format']
		# ....
	end

	#...
end
{% endhighlight %}

### Hashes with defaults

It is possible to specify a default value (or even a default block) which will be used when the key doesn't exist, by creating a hash using `Hash.new`

{% highlight ruby %}
player_levels = Hash.new('Beginner')

player_levels['Tom'] #=> 'Beginner'

player_levels #=> {'Tom' => 'Beginner'}
{% endhighlight %}

Note how the new value is added to the hash.

You can also specify a default block, which will be called on each missing value:

{% highlight ruby %}
square_numbers = Hash.new {|hash, key| hash[key] = key**2 }

square_numbers[5] #=> 25
square_numbers[6] #=> 36

square_numbers #=> {5 => 25, 6 => 36}
{% endhighlight %}

The above could be used to save the results of an expensive calculation: if you do `square_numbers[5]` again it doesn't need to work it out - it just looks up the result.



{% exercise %}
1. Complete the three functions in `ruby4/character.rb`
2. Test your solutions using `test_character.rb`
{% endexercise %}