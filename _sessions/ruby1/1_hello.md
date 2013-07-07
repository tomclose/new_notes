---
title: Hello!
---

### What is ruby?

Ruby is a programming language. It is different to HTML and CSS, which are just *markup* languages: in ruby you can do calculations. We'll start off with a demonstration: 

{% exercise %}
1. Navigate to your `coding_course` folder in the command line.
2. Clone the repo for this session:

		$ git clone https://github.com/code61/ruby1.git

3. Open the file `coding_course/ruby1/hello.rb` in Sublime Text 
4. In the command line move into the `ruby1` folder and run the `hello.rb` file:

		$ cd ruby1
		$ ruby hello.rb

{% endexercise %}

You should see the word 'Hello' displayed in the terminal.

### What just happened?

The first few steps were just to pull the code down from the online repository (using git). We'll focus on steps 3 and 4. The file `hello.rb` contained some code in a language called ruby:

{% highlight ruby %}
# print 'Hello' to the screen
puts "Hello"
{% endhighlight %}

#### Comments

The first line is a comment - it doesn't do anything. You should always comment your code, as it helps you (and others) understand what is going on when you come back to look at it later. Any text on a line that comes after a `#` is a comment:

{% highlight ruby %}
# this whole line is a comment

puts "hello"  # this is a comment too

=begin
Any lines between a line beginning =begin and
a line beginning =end are also treated as a comment.
This style of commenting doesn't seem to be used that
much in The Wild.
=end
{% endhighlight %}

#### Puts and strings

The second line is where the magic is. `puts` stands for "put string". A *string* is a programming term that is used to describe what you would probably call a piece of text. The second line displays the string "Hello" in the command line.

#### Running the program

For the program to run we needed to call it using `ruby hello.rb`. `ruby` is a command line program that interprets and runs ruby files. When the ruby program gets to the end of the file it exits, giving you control of the command line again.

We say that ruby is an *interpreted* language - the ruby file is read in and executed in real time. Python, matlab and lisp are other interpreted languages that you might have heard of. You might also have come across *compiled* languages such as c, c++ and (to some extent) java. These languages require a pre-processing stage (called *compiling*) in order to turn the code into a program that the computer can run.


{% exercise %}
Modify `hello.rb`, so that the program will display "Hello, your-name". Run the program from the command line to check that it works.
{% endexercise %}


