---
title: Parameters
---

So far the functions we've seen have just given us information. We haven't yet seen how to give information to functions. Let's do that now!

{% highlight ruby %}
def greet(name)
  return "Hello #{name}!"
end

greet("Tom") #=> "Hello Tom!"
{% endhighlight %}

The `greet` function accepts a *parameter* called `name`. It then inserts `name` into a string and returns that to the user. 

To *call* the function we have to pass in a value for the parameter. In this case we pass in the string `"Tom"`.

Notice that, unlike in some other languages, in ruby you don't have to tell the function what type of object to expect the parameter to be. All that matters is that the object you pass in has the methods you want to call on it. This idea is called **duck-typing** - it doesn't matter what an object is, all that matters is how it behaves: 

<blockquote>
<p>When I see a bird that walks like a duck and swims like a duck and quacks like a duck, I call that bird a duck.</p>
<small>James Whitcomb Riley</small>
</blockquote>

### Default parameters

Sometimes we want to specify a default value for a parameter. If the parameter is missing it will take this default value:

{% highlight ruby %}
def greet(name = "everyone")
  return "Hello #{name}!"
end

greet("Tom") #=> "Hello Tom!"
greet() #=> "Hello everyone!"
{% endhighlight %}

If we pass in `"Tom"` as the parameter, the function works as before. If we don't pass anything in, the function gets the default value `"everyone"`.

### Functions with irb

You'll often want to try out the functions you are working on in irb. There are two ways of doing this:
1. copy and paste the function into irb
2. load in the file that the function is written in

Option 2 is the better option when your functions become bigger and more complicated. To do this do
{% highlight irb %}
> load 'my_file.rb'
{% endhighlight %}

Irb will look for the file **in the folder that you started irb in** (and then on your path).

{% exercise %}
1. The file `functions.rb` contains several broken functions that need your help!
2. Open `functions.rb` in Sublime Text.
3. Fix all the functions in the file. 
3. Run `test_functions.rb` in the console to check your answers.

        ruby test_functions.rb


{% endexercise %}

<hr>

{% exercise %}
(Extension)
1. Open `encode.rb` in Sublime Text
2. Run `test_encode.rb` in the console
3. Change the encode to use the bitwise_xor operation (`^`) for encoding
4. Write the decode function so that the tests pass
5. In the code you've been given, the `encode` function does a bitwise xor with the number 6. Get your partner to write an encode that uses a different (unknown) number and paste it into your irb. How can you find out which number they use? Can you write the `decode` function so that it will work no matter which function they give you?
{% endexercise %}