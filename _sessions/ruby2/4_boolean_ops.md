---
title: Logical operations
---

It's often useful to combine various conditions:

{% highlight ruby %}
if age < 12 || height < 1.2
	puts "You are allowed on the ride."
else
	puts "Try a different helter-skelter. There's nothing for you here."
end
{% endhighlight %}

It the above snippet of code the `||` means or. If the person is under 12 or is smaller than 1.2m they are allowed on the ride.

### Logical operations

Ruby has three ways of combining conditions:

#### and (`&&`)

If you use an `&&` the output is true only if both inputs are true. You can write this in terms of a *truth table*:


x  |  y  | x && y
-- | --  | -----
false | false | false
false | true | false
true  | false | false
true  | true  | true


#### or (`||`)

If you use the `||` the output is true if at least one of the inputs is true. `||` means one or the other **or both**:

<table class="table">
	<thead>
		<tr><th>x</th><th>y</th><th>x || y</th></tr>
	</thead>
	<tbody>
		<tr><td>false</td><td>false</td><td>false</td></tr>
		<tr><td>false</td><td>true</td><td>true</td></tr>
		<tr><td>true</td><td>false</td><td>true</td></tr>
		<tr><td>true</td><td>true</td><td>true</td></tr>
	</tbody>
</table>


### not (`!`)

The `!` is not. It is a quick way of reversing the truth of the condition:

x | !x
-- | --
false | true
true  | false


{% exercise %}
Open the file `boolean_ops.rb` in Sublime Text. For each of the expressions discuss with your partner what you think the expression will evaluate to. Check by pasting them in to irb.
{% endexercise %}