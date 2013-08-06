---
title: Install MongoDB
---

Next session we will begin looking at databases. In particular we will be using a database called [MongoDB](http://www.mongodb.org/). It is vital that you get MongoDB installed before the start of the session on Tuesday, or you won't be able to participate.

<div class='alert alert-warning' markdown='1'>
To use MongoDB you will need to be running ruby 1.9. If you aren't, you need to try and sort that out first. (To check your version, follow instructions [here](http://code61.org/hmwk2/#!3_diagnostics)).
</div>

### What you need to do

To use mongodb you need to have it running on your laptop. The database will run on one of your localhost ports (like sinatra), so that other processes can connect to it.

The preparation falls into four parts:

1. Install MongoDB.
2. Start running the database.
3. Install the gems to allow ruby to connect to MongoDB.
4. Test your installation.

We will look at these parts separately.

### Install MongoDB

If you installed `homebrew` ("The Hard Way"), your task is now easy. At the command line write:

    brew install mongo

If you didn't install homebrew (i.e. try doing the above and it doens't work), you will need to [download MongoDB](http://www.mongodb.org/downloads) from the site and follow the installation instructions for your system.

{% exercise %}
Install MongoDB either via

    $ brew install mongo

or by downloading and installing from the [MongoDB website](http://www.mongodb.org/downloads).
{% endexercise %}

### Start MongoDB running

You can start MongoDB running from the command line:

    $ mongod

You will need to keep this command line there and open a new one to continue the instructions.

By default mongo will run on [localhost:28017](http://localhost:28017/). If you visit that link in your browser you should see a mongo stats page.

{% exercise %}
1. Start MongoDB:

        $ mongod

2. Check the service is running at [localhost:28017](http://localhost:28017/).
{% endexercise %}

### Install the gems and test

I've set up a project with the gems you need, so this should be straightforward:

{% exercise %}
1. Clone the project:

        $ git clone https://github.com/code61/mongo_test.git

2. Move into that folder and install the gems:

        $ cd mongo_test
        $ bundle install

3. Test your installation:

        $ ruby main.rb

    If you see the text "Everything worked ok!", you're good to go!
{% endexercise %}