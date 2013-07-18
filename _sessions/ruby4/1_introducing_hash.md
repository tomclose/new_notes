---
title: Introducing the Hash
---

You've already met one of ruby's common collection objects: the `Array`. In this session we're going to have a look at the other basic type of collection: the `Hash`.

In an array the objects were ordered, and referenced by their index:

{% highlight ruby %}
a = ['zero', 'one', 'two']

a[0] #=> 'zero'
{% endhighlight %}

In a hash the objects are stored in any particular order, but instead are stored with a key. The key can then be used to retrieve or modify the object.

{% highlight ruby %}
character = {'name'=>'Bart', 'surname'=>'Simpson', 'age'=> 10, 'catchphrase' => 'Eat my shorts'}

character['name'] #=> 'Bart'
character['catchphrase'] #=> 'Eat my shorts'
{% endhighlight %}

The above code creates a hash using the curly brackets `{ }`. Each element of the hash has a key e.g. `'name'` and a value e.g. `'Bart'`. 

{% exercise %}
1. Grab the code for the session:

		git clone https://github.com/code61/ruby4.git

2. With your partner work through `ruby4/hash_examples.rb`. See if you can guess what each expression will do, then test by pasting into irb.
{% endexercise %}