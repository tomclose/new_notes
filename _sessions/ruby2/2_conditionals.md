---
title: Conditionals
---

Often when writing code it is useful to test for certain conditions and respond accordingly.

{% highlight ruby %}
def old_enough?(age)
	if age >= 18
		puts "You can buy alcohol"
	end
	return nil
end
{% endhighlight %}

In the above code we use an `if` statement to write a function to tell us if someone can buy alcohol. The if statement starts with an `if` and ends with an `end`:

{% highlight ruby %}
if some_condition
	# do some stuff here ...
end
{% endhighlight %}

If the code within the `if` block will only be run if the statement is true.

### Comparisons

There are some basic comparisons that we will be useful when using if statments

Symbol | Meaning
---- | ----
`==` | Is equal to
`>`  | Greater than 
`<`  | Less than
`>=` | Greater than or equal to
`<=` | Less than or equal to
`!=` | Not equal to

Comparisons evaluate to `true` or `false`.

{% exercise %}
In irb try each of the above comparisons e.g. `4 != 5`.
{% endexercise %}

### If/else

It is often useful to have the ability to run some code only if the condition isn't true. Ruby allows you to do this with an `if .. else` statement:

{% highlight ruby %}
def old_enough?(age)
	if age >= 18
		puts "You can buy alcohol"
	else
		puts "No alcohol for you child. Move along please."
	end
	return nil
end
{% endhighlight %}

# TODO explain about `load 'pass_fail.rb'`

{% exercise %}
1. Open `pass_fail.rb` in Sublime Text
2. Run `test_pass_fail.rb` in the console
3. Complete the function `pass_fail` in `pass_fail.rb` using an `if` statement so that the tests pass
4. (extension) Complete the function `pass_fail2`, using `test_pass_fail2.rb` to test.
{% endexercise %}



