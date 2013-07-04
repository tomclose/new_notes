---
title: Domain Names and Servers
---

You can think of the internet as a massive network of computers that can send files to one another. The computers that hold web pages are called _servers_. In general they are large, specialised computers that are permanently connected to the internet.

Each computer on the internet has an address (an _IP address_) so that requests can be sent to it and files returned - much like a telephone number. The backbone of the internet is a network of _routers_ that are responsible for routing files from one IP address to another.

IP addresses are a sequence of numbers and '.'s such as `212.58.244.67`. These aren't very easy to remember. Instead the internet works on a domain name system, that matches domain names such as `bbc.co.uk` to IP addresses. 

{% exercise %}
Type `212.58.244.67` into your browser's address bar. What happens?
{% endexercise %}

One of the first things that happens when you type a URL into your browser is a _DNS lookup_: your computer contacts a DNS server (*Domain Name System server*), which is basically a massive address book of IP addresses. The DNS server converts the domain name from the URL (e.g. `bbc.co.uk`) into an address for a server (such as `212.57.244.67`).


### Putting up a website

If you want to put up your own website at your own domain name you need two things:

1. A web server to serve your site
2. A domain name to point towards it

There are many options for web servers - you don't have to physically have your own one. There are many companies that will offer web hosting, often providing you with space on a shared server. Later in the course we will use the free hosting offered by GitHub through GitHub Pages.

To buy a domain name you need to use a domain registrar. Examples include [123-reg.co.uk](http://www.123-reg.co.uk/), [godaddy.com](http://www.godaddy.com/) and [namecheap.com](http://www.namecheap.com/). You pay the registrar to contact the body who manages a TLD (e.g. .com, .org., .co.uk) and put your server's IP address in their DNS address book. If someone else already owns the domain you might be able to buy it off them, but this can be expensive!

Many domain registrars will try to sell you hosting and other site building tools when you buy a domain. It's important to remember that the domain name is completely separate from the hosting and you don't need to do them both through the same company - don't buy anything you're not going to use.