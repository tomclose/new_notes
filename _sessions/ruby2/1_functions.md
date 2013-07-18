---
title: Functions
---

Quite often when writing code you find that you have some operation that you have to do over and over again. As an example consider a simple interactive command line program:

{% highlight console %}
Enter your name: margE
Enter your guest's name: homer
Welcome Marge and Homer!
{% endhighlight %}

One way of doing this would be to write the following code:

{% highlight ruby %}
print "Enter your name: "
# Wait for user input:
main_name = gets
# Remove the 'newline' caused by pressing enter:
main_name = main_name.chomp
# Capitalize the string:
main_name = main_name.capitalize

print "Enter your guest's name: "
# Wait for user input:
guest_name = gets
# Remove the 'newline' caused by pressing enter:
guest_name = guest_name.chomp
# Capitalize the string:
guest_name = guest.capitalize

puts "Welcome #{main_name} and #{guest_name}!"
{% endhighlight %}

You'll notice that we're basically doing the same stuff to `main_name` and `guest_name`. It would be nice to not have to duplicate this logic in our code. This will be especially important when our code examples become longer and more complicated.

Like most languages, Ruby allows you to reuse bits of code by writing a *function*. For the case above we're going to write a function called `get_name`, which will (a) wait until the user inputs a string and (b) prepare that string using `chomp` and `capitalize`.

### Writing a function

Writing a function in ruby goes something like this:

{% highlight ruby %}
def get_name
    # Wait for user input:
    name = gets
    # Remove the 'newline' caused by pressing enter:
    name = name.chomp
    # Capitalize the string:
    name = name.capitalize
    return name
end
{% endhighlight %}

The `def` and `end` keywords are used to tell the interpreter where the function starts and finishes. Here `get_name` is the name of the function. The `return` value tells the function what to give back when it is called.

The above code can then be re-written:
{% highlight ruby %}
# Define get_name
def get_name
    # Wait for user input:
    name = gets
    # Remove the 'newline' caused by pressing enter:
    name = name.chomp
    # Capitalize the string:
    name = name.capitalize
    return name
end

print "Enter your name: "
main_name = get_name

print "Enter your guest's name: "
guest_name = get_name

puts "Welcome #{main_name} and #{guest_name}!"
{% endhighlight %}

{% exercise %}
1. Grab the code for this session:

		git clone https://github.com/TomClose/ruby2.git

2. Open the file `function_example.rb`.
3. Write the `get_name` function and modify the code to use it.
4. Copy and paste the function into `irb` and try it on a few strings.
{% endexercise %}

### A note on scope

In the `get_name` function, we defined a variable called `name`. Because it was defined inside the function the variable won't exist outside the function:

{% highlight ruby %}
def get_name
    # Wait for user input:
    name = gets
    # Remove the 'newline' caused by pressing enter:
    name = name.chomp
    # Capitalize the string:
    name = name.capitalize
    return name
end

# the variable 'name' only exists inside the function get_name

name #=> NameError: undefined local variable or method `name' for main:Object
{% endhighlight %}

We say that the *scope* of the variable `name` is the function `get_name`. Outside that function the variable is *out of scope* and can't be called.

So **variables defined inside functions can't be seen outside**.

