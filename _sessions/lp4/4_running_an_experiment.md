---
title: AB Testing
---

AB Testing is experimenting with different ideas on your site. You set up two versions of a page that you want to test and randomly send your users to one or the other. Over time you build up statistics about which version is best.

There are lots of tools available for AB testing e.g [Optimizely](https://www.optimizely.com) and [Visual Website Optimizer](http://visualwebsiteoptimizer.com/). These make it easy for non-technical marketing folk to run AB tests.

As you all know how to edit HTML you can run AB tests using Google Analytics for free! You basically provide two (or more) different HTML files to represent the variations you want to test. You then set up an 'Experiment' in Google Analytics pasting in the javascript code they give you. Google Analytics will set a cookie on the users machine, so that if they return to the page they will see the same version.

{% exercise %}
In the Reporting > Contents > Experiments section set up an experiment to test two slightly different versions of your `index.html`. It's best to only change one aspect at ta time (e.g. background picture/title text/button colour) so you can work out what is having an effect.
{% endexercise %}