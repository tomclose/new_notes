---
title: Functions
---

Quite often when writing code you find that you have some operation that you have to do over and over again. As an example consider a simple interactive command line program:

{% highlight console %}
Enter your name: homer
Enter your guest's name: margE
Welcome Homer and Marge!
{% endhighlight %}

One way of doing this would be to write the following code:

{% highlight ruby %}
print "Enter your name: "
name = gets.chomp

print "Enter your guest's name: "
guest = gets.chomp

puts "Welcome #{name.downcase.capitalize} and #{guest.downcase.capitalize}!"
{% endhighlight %}

You'll notice that we call `.downcase.capitalize` on each input to prepare it for displaying - we do the exact same action in two different places. As it is, this is almost ok, as what we're doing is very simple. If this action got much more complicated (for example if we wanted to cope with names like 'Mary-Jane') it would be good to separate it out into a different bit of code. Like most languages, Ruby allows you to do this by writing a *function*.

### Writing a function

Writing a function in ruby goes something like this:

{% highlight ruby %}
def prepare_name(name)
	return name.downcase.capitalize
end
{% endhighlight %}

The `def` and `end` keywords are used to tell the interpreter where the function starts and finishes. Here `prepare_name` is the name of the function and `name` is a *parameter*, which represents the value that we'll pass in to the function. The `return` value tells the function what to give back when it is called.

Notice that, unlike in some other languages, in ruby you don't have to tell the function what type of object to expect the parameter to be. All that matters is that the object you pass in has the methods you want to call on it. This idea is called **duck-typing** - it doesn't matter what an object is, all that matters is how it behaves: *"When I see a bird that walks like a duck and swims like a duck and quacks like a duck, I call that bird a duck."[(James Whitcomb Riley)](http://books.google.co.uk/books?id=j7zds6xx7S0C&pg=PA68&dq=%22james+Riley%22+OR+%22James+Whitcomb+Riley%22+bird++duck&num=100&redir_esc=y#v=onepage&q=%22james%20Riley%22%20OR%20%22James%20Whitcomb%20Riley%22%20bird%20%20duck&f=false)*.

The above code can then be re-written:
{% highlight ruby %}
# define prepare_name
def prepare_name(name)
	return name.downcase.capitalize
end

print "Enter your name: "
name = gets.chomp

print "Enter your guest's name: "
guest = gets.chomp

puts "Welcome #{prepare_name(name)} and #{prepare_name(guest)}!"
{% endhighlight %}

Note that to call the function we pass it a value inside `()`: e.g. `prepare_name('tom')`.

{% exercise %}
Copy and paste the `prepare_name` function definition into irb. Try calling it on some strings.
{% endexercise %}

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
1. Grab the code for this session:

		git clone https://github.com/TomClose/ruby2.git

2. Open `double.rb` in Sublime Text
3. Run `test_double.rb` in the console:

		ruby test_double.rb

4. Complete the code in `double.rb` so that the test passes.
{% endexercise %}

{% exercise %}
1. Open `encode.rb` in Sublime Text
2. Run `test_encode.rb` in the console
3. Change the encode to use the bitwise_xor operation (`^`) for encoding
4. Write the decode function so that the tests pass
5. In the code you've been given, the `encode` function does a bitwise xor with the number 6. Get your partner to write an encode that uses a different (unknown) number and paste it into your irb. How can you find out which number they use? Can you write the `decode` function so that it will work no matter which function they give you?
{% endexercise %}