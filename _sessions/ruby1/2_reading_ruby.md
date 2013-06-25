---
title: Reading ruby
---

{% exercise %}
1. Open the file `ruby1/times.rb` in Sublime Text.
2. What do you think this program does?
3. Run the program to see if you're right:

		$ ruby times.rb

{% endexercise %}

`times.rb` contains the single line:
{% highlight ruby %} 
(1..12).each { |number| puts 3 * number }
{% endhighlight %}

We're not going to worry about precisely how the instruction works at the moment - we'll learn about this in detail over the next few sessions. The point of this exercise was to begin to show you why ruby is great.

It is often possible to write ruby in a way that reads a lot like English. Hopefully you found this with the above example - even though you've only just met ruby you were probably able to have a reasonably guess at what the above code did.

Ruby is an incredibly powerful and flexible language. It is a modern language - created in the 1990s by Yukihiro Matsumoto (Matz). A large part of his design philosophy is centered around optimizing for developer happiness - making a language that is a pleasure to program in. If you haven't already programmed in another language, you might not fully appreciate this, but - take it from me - ruby is awesome!