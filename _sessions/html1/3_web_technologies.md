---
title: Web technologies
---

Once the address of the web server has been found your request is forwarded on to it. The web server will interpret your request and send back one or more files. We now look at the technology involved in this process.

When talking about web technology it is useful to split things up into server-side technology and client-side technology. Server-side relates to anything that happens on the web server. Client-side is anything the server sends back to your browser.

The main three client-side technologies are HTML, CSS and Javascript. Client-side stuff has to be interpreted by your browser, so there are relatively few possibilities.

HTML (_HyperText Markup Language_) encodes the information that is sent back from the server. CSS (_Cascading Style Sheets_) tell your browser how to display that information. Javascript is a programming language that can be used to provide client-side interactivity. We'll look at these in more detail later in the course.

There are two main possibilities server-side: either your site is static or dynamic. In a static site all the pages are pre-prepared and the web server just sends them to the browser. In a dynamic site the pages are prepared on-the-fly pulling information out of a database depending on what the user asked for. Most of the sites you can think of will be dynamic sites (e.g. [facebook.com], [reddit.com], [amazon.com], ..).

There are many options for building a dynamic server-side site - you're pretty much free to do what you like. Some common choices are:
- Ruby on Rails
- php
- python
- Node.js
- Wordpress

We will now look in more detail at HTML