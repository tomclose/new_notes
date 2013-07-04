---
title: Introducing the URL
---

Many of our web interactions begin with a URL (*uniform resource locator*) being typed into our web browser address bar. Let's look at an example: `http://www.bbc.co.uk/news/`.

This URL has several different parts to it:
- `http` : the _protocol_ or *how* to fetch the information
- `www.bbc.co.uk` : the _host_ or *where* to fetch it from
- `/news` : the _path_ or precisely *what* information to fetch

When we type the URL into the address bar a request is sent over the internet and some information is returned to us.

The protocol describes how the information is transmitted. Other possibilities include `https` for secured communication, `ftp` for file transfer and `git` which we'll learn about later.

The host describes where the information should come from and the path tells that location precisely what information to send. 

In general a URL can be more complicated than this. URLs can also contain _query parameters_, _fragments_ and _port information_. We will leave these for now but will point them out when we meet them later. Instead we will focus on exactly what information is being sent and who is sending it.