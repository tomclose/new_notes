---
title: Sorting and Filtering
---

### Sorting

{% highlight ruby %}
[3, 2, 1].sort

['apple', 'banana', 'pear'].sort

['apple', 'banana', 'pear'].sort {|a, b| a.length <=> b.length }
{% endhighlight %}

### Filtering

{% highlight ruby %}
[3, 2, 1].select {|x| x < 2}

['apple', 'banana', 'pear'].select { |w| w.length <= 5 }
{% endhighlight %}


{% exercise %}
1. Go back to the file `marks.rb`
2. Write two more functions:
	1. a function `display_sorted` which displays the marks with the top mark first
	2. a function `display_selected` which displays only those who passed (got more than an 'f')
3. Check your answers with `test_sort_select_marks.rb`
{% endexercise %}