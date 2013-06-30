---
title: Symbols
---

Symbols save space

{% highlight ruby %}
"hello"
:hello
{% endhighlight %}

{% highlight ruby %}
:hello.to_s
"hello".to_sym


"hello" << " world"
:hello << :" world"

"hello".object_id

:hello.object_id

{% endhighlight %}

{% exercise %}
1. Do `ruby4/symbolize_keys.rb`.
2. Test your answers using `test_symbolize_keys.rb`
{% endexercise %}