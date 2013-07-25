---
title: Basic app
---

We're now going to look at how to create a very simple web application using sinatra.

{% highlight ruby %}
# in app.rb:

require 'sinatra'

get '/' do
    "hello"
end
{% endhighlight %}

This file is very simple. The first line imports the `sinatra` library. The next bit tells sinatra how to respond to a certain type of request. In particular it says that if it receives a `GET` request to the root url it should send back the text "hello".

To run this app first `cd` into the `app1` directory and then ruby the `app.rb` file.

    $ cd app1
    $ ruby app.rb
    == Sinatra/1.3.3 has taken the stage on 4567 for development with backup from Thin
    >> Thin web server (v1.3.1 codename Triple Espresso)
    >> Maximum connections set to 1024
    >> Listening on 0.0.0.0:4567, CTRL+C to stop

Sinatra has started a webserver on your computer, which you can view in your browser. It will be displayed at the IP address `0.0.0.0` on port `4567`. `0.0.0.0` always points to the machine you are currently using. Another way of saying this is to use the word `localhost`. You will be able to view the site by typing one of the following into your browser address bar:

* `0.0.0.0:4567`
* `localhost:4567`

{% exercise %}
1. Run the app. In the `app1` directory:

        $ ruby app.rb

     Check you can see the page in your webbrowser at [localhost:4567](http://localhost:4567).
2. Make a change to `app1/app.rb` so that it instead says "Hello there!". Check you can see the change in your browser (you will have to stop the server with `Crtl-C` then restart it again with `ruby app.rb`).
3. Test your solution by running

        $ ruby test1.rb

4. Try visiting a different url (e.g. [localhost:4567/about](http://localhost:4567/about)). What happens?
{% endexercise %}

### Taking parameters from the url

Take a look at the following code:

{% highlight ruby %}
# in app.rb:

require 'sinatra'

get '/' do
    "hello"
end

get '/:name' do
    "hello #{params[:name]}"
end
{% endhighlight %}

The `/:name` is a URL matcher. It will match `/` followed by any word, for example `/tom`, `/gertrude` or `/this_isnt_a_name`. The value that is matched is made available in a hash called params as `params[:name]`.

{% exercise %}
1. Open `app1/app.rb` in Sublime text.
2. Change it so that visiting [localhost:4567/tom](http://localhost:4567/tom) shows "Hello Tom!" in the browser (and similarly for other names).
3. See if you can make it so that [localhost:4567/tom/bye](http://localhost:4567/tom/bye) shows "Goodbye Tom" in the browser (and similarly for other names).
4. Change the code by adding a `raise` right before `end` to:

        get '/:name' do
            # keep the stuff you've written here
            # ...

            # add a raise just before the end
            raise
        end

    What happens? 
{% endexercise %}