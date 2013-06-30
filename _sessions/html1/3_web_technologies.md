---
title: Web technologies
---

Once the address of the web server has been found your request is forwarded on to it. The web server will interpret your request and send back one or more files. We now look at the technology involved in this process.

When talking about web technology it is useful to split things up into server-side technology and client-side technology. Server-side relates to anything that happens on the web server. Client-side is anything the server sends back to your browser.

### Client-side

The main three client-side technologies are HTML, CSS and Javascript. Client-side stuff has to be interpreted by your browser, so there are relatively few possibilities.

<ul class="thumbnails">
  <li class="span3">
    <div class="thumbnail">
      <img src="/assets/html5_logo_128.png" style="height: 128px;" alt="">
      <h3>HTML</h3>
      <p><em>HyperText Markup Language</em> encodes the information that is sent back from the server.</p>
    </div>
  </li>
  <li class="span3">
    <div class="thumbnail">
      <img src="/assets/css.jpeg"  style="height: 128px;" alt="">
      <h3>CSS</h3>
      <p><em>Cascading Style Sheets</em> tell your browser how to display that information.</p>
    </div>
  </li>
  <li class="span3">
    <div class="thumbnail">
      <img src="/assets/js.jpeg"  style="height: 128px;" alt="">
      <h3>Javascript</h3>
      <p>Javascript is a programming language that can be used to provide client-side interactivity.</p>
    </div>
</li>
</ul>

We'll look at these in more detail later in the course.

### Server-side

There are two main possibilities server-side: either your site is static or dynamic. In a static site all the pages are pre-prepared and the web server just sends them to the browser. In a dynamic site the pages are prepared on-the-fly pulling information out of a database depending on what the user asked for. Most of the sites you can think of will be dynamic sites (e.g. [facebook.com], [reddit.com], [amazon.com], ..).

There are many options for building a dynamic server-side site - you're pretty much free to do what you like. Some common choices are:

<ul class="thumbnails">
  <li class="span3">
    <div class="thumbnail">
      <img src="/assets/rails.jpeg" alt="">
      <h3>Ruby on Rails</h3>
      <p>A web development framework written in the Ruby programming language.</p>
    </div>
  </li>
  <li class="span3">
    <div class="thumbnail">
      <img src="/assets/php_logo.gif"  style="height: 90px;" alt="">
      <h3>php</h3>
      <p>A programming language that formed the basis of most dynamic websites in the early 2000s.</p>
    </div>
  </li>
  <li class="span3">
    <div class="thumbnail">
      <img src="/assets/django_logo.png" style="height: 128px;" alt="">
      <h3>django</h3>
      <p>A web development framework written in the Python programming language.</p>
    </div>
  </li>
  <li class="span3">
    <div class="thumbnail">
      <img src="/assets/nodejs_logo.png" alt="">
      <h3>Node.js</h3>
      <p>A web development framework written in javascript.</p>
    </div>
  </li>
  <li class="span3">
    <div class="thumbnail">
      <img src="/assets/wordpress_logo.png" alt="">
      <h3>Wordpress</h3>
      <p>A blogging platform (now capable of much more) written in php.</p>
    </div>
  </li>
</ul>

