---
title: One-to-many views
---

Having changed the structure of the models, we now need to update the views. The first think you might notice is the [tasks list](http://localhost:3000/tasks) (`:index`) now looks a bit weird - you might see things like `#<Project:0x007f9dfb03f228>` on your page. This is due to the following line:

{% highlight html %}
<td><%= task.project %></td>
{% endhighlight %}

and is because `task.project` is now a `Project` object instead of a string. What we really want instead is to display the name of the `task.project` `Project` object:

{% highlight html %}
<td><%= task.project.name %></td>
{% endhighlight %}

This might work for you, but it might not - it isn't very robust. In particular, if you have a task which you haven't yet set a project for, you'll end up with an error:

    undefined method `name' for nil:NilClass

This is because if a `task` doesn't have a project, `task.project` returns `nil` and `nil` doesn't have a `name` method. We need to check whether the `project` exists before we call name. The best thing to do here is to create a new method on the `Task` model to sort this out for us:

{% highlight ruby %}
# in models/task.rb
class Task < ActiveRecord::Base
  # other methods
  # ....

  def project_name
    if project
      project.name 
    else
      ""
    end
  end
end
{% endhighlight %}

If the project exists (remember that `nil` is falsey) it will return the project's name, if not it will return the empty string. We can now use this method in the index template:

{% highlight html %}
<td><%= task.project_name %></td>
{% endhighlight %}

You might want to do something similar in `app/views/tasks/show.html.erb`.

### One-to-many form using collection_select

We also need to change our forms a bit to reflect the new relationship. There's a design decision to be made here: do you want to be able to add tasks to a project (i.e. on the project form) or do you want to be able to assign a task to a project (i.e. on the task form) (or both)? We're going to go for the second option here, as it's the easier of the two. If you want to have a go at the former you should have a look at these [two](http://railscasts.com/episodes/196-nested-model-form-part-1) [railscasts](http://railscasts.com/episodes/196-nested-model-form-part-2).

We're now going to look at how to select an existing `Project` on the new/edit `Task` form. Currently the project field in `app/views/task/_form.html.erb` looks like this:

{%highlight html%}
<div class="field">
  <%= f.label :project %><br>
  <%= f.text_field :project %>
</div>
{% endhighlight %}

This was fine when project was just a string, but there are better options now. We're going to use a `collection_select` form element to let the user pick an existing project from a list:

{% highlight html %}
<div class="field">
  <%= f.label :project %><br>
  <%= f.collection_select :project_id, Project.all, :id, :name %>
</div>
{% endhighlight %}

As we're now setting the `project_id` instead of the `project` we also need to make a small change in `app/controllers/task_controller.rb`:

{% highlight ruby %}
def task_params
  params.require(:task).permit(:name, :due_date, :description, :project_id, :completed)
end
{% endhighlight %}

You can find out more about collection select from the [Rails docs](http://api.rubyonrails.org/classes/ActionView/Helpers/FormOptionsHelper.html#method-i-collection_select) (which I found by googling 'rails collection_select').

{% exercise %}
1. Update `app/views/tasks/index.html.erb` as above.
2. Update `app/views/tasks/_form.html.erb` as above.
{% endexercise %}


