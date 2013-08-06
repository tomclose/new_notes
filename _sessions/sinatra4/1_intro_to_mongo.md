---
title: Using a database
---

In this session we will be using a database - a specialised piece of software for storing and retrieving data. Databases become important when you have large amounts of data, which you want to be able to access quickly and which you want to keep consistent.

In the session we will be using two different, but related, pieces of software:

* [MongoDB]() the database.
* [Mongoid]() a ruby library that we will use to interface with MongoDB.

MongoDB is one of many different databases that we could have chosen. We went with MongoDB because it is fairly straight-forward to configure and quick to get going with. It is also fairly popular in the web community at the moment.

MongoDB is a *NOSQL*, or *document-based*, database. In the past, the more traditional style *SQL*, or *relational*, databases were used in most applications. NOSQL databases have risen in popularity in the last year or two, in part due to their ability to offer increased performance in certain common scenarios, by allowing developers to bend the rigid SQL database structures. We will go into this in slightly more depth later in the course. For the time being, with data we're storing in the next few sessions it won't make much difference whether our db is SQL or NOSQL.



So far in ruby we have met several different types of object e.g. `String`, `FixNum`, `Array` and `Hash`. To interact with the database we will define our own type of object using a `class`:

{% highlight ruby %}
class Person
    include Mongoid::Document

    field :name
    field :age

end
{% endhighlight %}