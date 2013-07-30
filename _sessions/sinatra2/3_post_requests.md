---
title: Post requests
---

Last time we looked at responding to `get` requests:

{% highlight ruby %}
get '/' do
    erb :index
end
{% endhighlight %}

As mentioned in [Landing Page 3](/lp3), `GET` is only one of several types of web requests. Another is the `POST` request, which is commonly used for submitting data from a web form.

Suppose we have the following HTML form:

{% highlight html %}
<form method="post" action='/'>
    <input type='text' name='user_name'>
    <input type='submit'>
</form>
{% endhighlight %}

The form will submit via a `POST` request to the root url, `/`. We can respond to this using the following sinatra block:

{% highlight ruby %}
post '/' do
    @name = params[:user_name]
    erb :page
end
{% endhighlight %}

Note that, like the words matched in the url, the value of the `user_name` field is made available in the `params` hash. If you want to have a look at the params hash you could put a `raise params.inspect` at the beginning of the method.

{% exercise %}
1. Clone the code for the session:

        $ git clone https://github.com/code61/sinatra2.git

2. Run the application. Check you understand what it does and how it does it.
3. Have a look at the [example solution](http://sheltered-oasis-6836.herokuapp.com). This is what you're trying to build!
3. Change the form so that it also asks for a user email (call it `user_email`), the user's operating system (windows/mac/linux) (`user_os`).
4. Make it so that after submitting the form the user is sent to a page that displays all the details they supplied.
{% endexercise %}