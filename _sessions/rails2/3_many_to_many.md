---
title: Many-to-many relationship
---

We're now going to look at adding tags to the tasks. Since a task can be tagged with many things and each tag can be applied to many tasks, this is a many-to-many relationship. We will be dealing with the following tables:

* **Task**: id, name, due_date, description, project_id, completed
* **Tag**: id, name
* **TaskTag**: id, task_id, tag_id

The `TaskTag` table will be a join table, which will keep track of which tags each task has been tagged with. Note that, unlike adding a project, we won't have to modify the `Task` table.

To begin with we set up the `Tags` models, views and controllers using `rails generate scaffold`:

    $ rails generate scaffold tag name:string

We then set up the `TaskTag` model. Note that here we do `rails generate model`. This will just set up the model and database migration, skipping the controllers and views. This makes sense: we'll be adding tags through the tasks page - we don't need separate pages just for this.

    $ rails generate model task_tag task_id:integer tag_id:integer

We then need to create these new tables in the database:

    $ rake db:migrate

With the database now set up, we need to tell the code about this new relationship. You do this as follows in `app/models/task.rb`, `app/models/task_tag.rb` and `app/models/tag.rb`:

{% highlight ruby %}
class Task < ActiveRecord::Base
  has_many :task_tags
  has_many :tags, :through => :task_tags

  ## Rest of contents of Task class ...

  # ...

end

class TaskTag < ActiveRecord::Base
  belongs_to :task 
  belongs_to :tag
end

class Tag < ActiveRecord::Base
  has_many :task_tags
  has_many :tasks, :through => :task_tags
end
{% endhighlight %}

You can now test out the new relationship in the `rails console`:

{% highlight ruby %}
# create some tags
tags = %w(urgent important tomorrow bug feature).map {|t| Tag.create(:name => t) }

# find a task
t = Task.last
t.tags # => []

# add a tag to a task
urgent = tags[0]
t.tags << urgent
t.tags
urgent.tasks
{% endhighlight %}

{% exercise %}
Follow the steps above to allow tasks to be tagged.
{% endexercise %}

### Adding tags to the user interface

We're going to add the ability to add tags to the task on the task form. To do this we're going to use a feature that's new to Rails 4.0: the `collection_check_boxes`.

To `app/views/tasks/_form.erb` add the following lines:

{% highlight html %}
<div class="field">
  <%= f.collection_check_boxes :tag_ids, Tag.all, :id, :name %>
</div>
{% endhighlight %}

As we've now added a new element to our form we need to allow it through in the controller:

{% highlight ruby %}
# Never trust parameters from the scary internet, only allow the white list through.
def task_params
  params.require(:task).permit(:name, :due_date, :description, :project_id, :completed, :tag_ids => [])
end
{% endhighlight %}

We need the `:tag_ids => []` as tag_ids is an array of values. (This bit is new in Rails 4.0 and has been added to improve security. You can find out more about it at on the [strong parameters github site](https://github.com/rails/strong_parameters). To work out what to do here I used the following [stackoverflow post](http://stackoverflow.com/questions/16549382/how-to-permit-an-array-with-strong-parameters).)

{% exercise %}
Follow the instructions above to add tags to your tasks.
{% endexercise %}

