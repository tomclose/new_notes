---
title: More arrays
---

### Accessing elements

* Arrays start from 0, so that the first elements is `a[0]`
* Arrays also allow indexing from the back, giving the last element as `a[-1]`
* If try to access beyond the end of the array it gives `nil` (instead of an error in other languages)
* You can access multiple elements by specifying a range, e.g. `a[1..-1]` is everything but the first element


### Array methods

Arrays have many useful (and largely self-explanatory) methods, including:

* `empty?` - does the array have any elements, or is it the empty array `[]`
* `length`
* `include?(x)` - is `x` in the array
* `min`, `max`
* `reverse`, `reverse!` - as with strings the `!` permanenty changes the array
* `shuffle` - perform a random permutation

### Adding to an array

* You can add to an array by setting a given element explicitly `a[5] = 6`
* If the array isn't long enough the gaps are filled with `nil`:

		a = [1, 2]
		a[6] = 5
		a #=> [1, 2, nil, nil, nil, nil, 5]

* You can also add to the end of an array by doing `a << 5`. This is very 'rubyish' and you'll see it a lot.

### Strings to arrays to strings

* Strings have a `split` method which will convert a string into an array of words
* Arrays can be joined back into strings e.g. `a.join(',')` joins up the elements of `a` using `,`


{% exercise %}
Write a sum function that takes an array (of numbers) and returns the sum of its elements.
{% endexercise %}

{% exercise %}
1. Open the file `marks.rb` in Sublime Text
2. Fix the mistakes in the `display_marks` function. You'll probably want to try some bits out in irb to see what's going on.
3. Check your solution by running `test_marks.rb` in the console.
{% endexercise %}