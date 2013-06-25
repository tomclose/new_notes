---
title: Teaching Ruby Plan
layout: default
---

# Teaching Ruby

## Ruby 1: files, irb, sums, variables, strings, puts

- idea of program as a file that you run
- comments
- hello.rb, run, change to make it print their name
- a more complicated but readable example ?
- introduce to irb
- +, -, *, /, % (inc dividing integers), expressions, numbers evaluate to themselves
- what does % do?
- numbers are objects - even?, odd?, methods 
- variables, x = x + 1
- strings, methods, interpolating strings, "tom"*3
- interactive hello (print vs puts), sanitizing name, entering other details
- enter a pair of numbers (5, 2) and print 5 = 2*2 + 1


## Ruby 2: methods and scopes, ifs, booleans, case?

- rewriting sanitize into a method (use return), loading file into console
- get them to write a double method
- talk about scope - show example
- method with an if: how_big? -> "x is bigger than three"
- modify how_big using elsif, else
- boolean operations - what do they think the expressions will give, truthy/falsy
- method to print out truth table e.g. truth_table('and')
- challenge what does & do? 

## Ruby 3: iterating, each, array, blocks

- (1..4).each { |n| puts n }, talk about iterator and block
- get them to print the square numbers from 1..4, put into a function
- get them to print a triangle of stars, put into a function
- introduce other form of block
- ['pizza', 'pasta'].each { | |  } , to introduce arrays
- look at other methods on arrays a[1..-1].each
- investigating array sums, differences, methods, etc
- iterating and summing, counting number of values
- filtering arrays
- sorting arrays (meeting blocks again)
- extension hmwk two_of_each (meet yield)

## Ruby 4: hashes, converting to hashes, CSV
- introduce hash
- write function: display({'name' => "Bart", 'father' => "Homer", 'age' => 11})
- adding property to hash
- iterating over hash, to print out details
- iterating over array and putting into a hash
- using hash to find the frequency of letters in a passage of text, using this to break a cipher?
- compiling student results? 

## Ruby 5: advanced things
- functions without return
- function calling without brackets
- yield



## Ruby 5: classes
- classes as data and methods
- characters, setting bart.father= homer, could also set homer.children << bart



## Still to do
- modules
- yield
- begin/rescue
- eigenclass stuff?



