---
title: Lists of data
---

So far we have only inserted single values and words into an already existing `erb` template. We will now look at using ruby to generate more of the template dynamically.

Suppose you have a ruby array that you want to turn into an html list:

{%highlight ruby%}
# in app.rb

get '/fruit' do
  @fruits = ["Bananas", "Apples", "Raspberries"]
  erb :fruits_view
end
{% endhighlight %}

We can do this by using the `@fruits` array's `each` method to interate over the elements and put them into the page one-by-one.

{% highlight html %}
<!-- in views/fruits_view.erb -->
<ul>
    <% @fruits.each do |fruit| %>
        <li><%= fruit %></li>
    <% end %>
</ul>
{% endhighlight %}

You might notice that we've used a different type of erb tag for the `do ... end` block: `<% %>` instead of `<%= %>`. This is really important:

* You need to use `<%= %>` if you want the result of executing that line of ruby to be added to the page.
* You need to use `<% %>` if you don't want the result of executing that line of ruby to be added to the page.

Here, the bits we want adding are the elements of the array, so only they have the `<%= %>` tags. The code will cause the following html to be generated:

{% highlight html %}
<ul>
    <li>Bananas</li>
    <li>Apples</li>
    <li>Raspberries</li>
</ul>
{% endhighlight %}

You can also use the same technique to generate tables and other html (lists of divs etc.).


{% exercise %}
1. Clone the code for this exercise:

        $ git clone https://github.com/code61/sinatra3.git

    Your aim for this exercise is to create the following [example site](http://code61-list-all-things.herokuapp.com/).
2. Have a look in `views/fruits_view.erb` and `app.rb` to check you understand what's going on.
3. Add some code to `views/oldest_dogs_view.erb` to create a list of dogs.
4. Add some code to `views/countries_view.erb` to create a *table* of countries and their capitals.
5. Add some code to `views/simpsons_view.erb` to create the Simpsons page like [the example](http://code61-list-all-things.herokuapp.com/simpsons).
6. (Optional extension) see if you can set up the individual pages dedicated to each Simpson e.g [Bart's page](http://code61-list-all-things.herokuapp.com/simpsons/bart). You will need a new routing block in `app.rb`, a new erb template in `views` and to think about how you will indentify the Simpson you want from the url.
{% endexercise %}