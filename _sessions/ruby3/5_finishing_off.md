---
title: Rounding up
---

Today we learnt about arrays and blocks. Both are really important and we'll be using them heavily from now on. The following methods are the ones you will use the most. Make sure you know them by heart and how to use them:

* `[1,2,3] << 'cat'`
* `split` (on a string)
* `join`
* `each`
* `map`
* `select`
* `sort`

You can find out more about all the different array methods by browing the [ruby array docs](http://www.ruby-doc.org/core-1.9.3/Array.html) (to find this just Google 'ruby array').


{% exercise %}
1. Open the file `marks.rb`.
2. Fix the mistakes in the `display_marks` function. **Only the code below `TODO` needs changing.** You will probably need to experiment with the line 

        marks = CSV.read('marks.csv', :headers => true).to_a

    in `irb` to figure out what's going on. This line uses Ruby's `csv` library, used for dealing with csv (comma-separated value) files. You will need to load in this library by first running `require 'csv'` (as is done at the top of the file).
3. Test your solution with `test_marks.rb`.
{% endexercise %}

{% exercise %}
(extension)
1. Go back to the file `marks.rb`. 
2. Write two more functions:
    1. a function `display_sorted` which displays the marks with the top mark first
    2. a function `display_selected` which displays only those who passed (got more than an 'f')
3. Check your answers with `test_sort_select_marks.rb`
{% endexercise %}