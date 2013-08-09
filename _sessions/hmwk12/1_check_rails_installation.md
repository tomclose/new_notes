---
title: Check your rails
---

Most of you should already have rails set up on your laptops from the intial installation instructions. It's worth doing a check though to make sure everything is in order for next session.

{% exercise %}
1. Download the `rails_test` code:

        $ git clone https://github.com/code61/rails_test.git

2. Install the gems:

        $ bundle install

3. Migrate your database:

        $ rake db:migrate

4. Start the server:

        $ rails server

5. Go to [localhost:3000](http://localhost:3000/) in your browser. If you see "Listing posts", everything is ok! You can now experiment with creating/editing/deleting a post.
{% endexercise %}

You might also want to have a browse through the [Rails tutorial book](http://ruby.railstutorial.org/ruby-on-rails-tutorial-book). In particular, have a read through Section 1.2.6 and Chapter 2.