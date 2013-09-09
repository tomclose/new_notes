---
title: One-to-many relationship
---

In this session we're going to be looking at relationships between models. All this is explained pretty clearly in the [Active Record Associations](http://guides.rubyonrails.org/association_basics.html) RailsGuide. You may want to refer to this during/after the session.

In our application so far we have a single Model, corresponding to a single table in the database. We can view the fields of this table by looking at a new `Task` in the `rails console`:

    > Task.new
    => #<Task id: nil, name: nil, due_date: nil, description: nil, project: nil, completed: nil, created_at: nil, updated_at: nil>

The `id` field was added by rails and will be used as the *primary key* for the row. (This isn't 'pure' in database design terms, but sidesteps a lot of the complexity caused by composite primary keys.) Rails also added the `created_at` and `updated_at` fields, which it sets and maintains on its own. The other columns: `name`, `due_date`, `description`, `project` and `completed` are the fields we specified with `rails generate scaffold`.

There's currently a problem with the `project` column: at the moment you have to write the project in each time as a string. It would make far more sense if you could select the project from a list of existing projects, or alternatively, create a new project and add tasks to them. In other words it would make more sense if there was also a `Project` model, with a one-to-many relationship between projects and tasks (a project can have many tasks, a task belongs to a single project).

To do this we're going to change the structure of the tables in our database to something like this (ignoring the created_at/updated_at fields):

* **Task**: id, name, due_date, description, project_id, completed
* **Project**: id, name

The projects table will contain only the rails-generated `id` and a `name`. The tasks table will now contain a `project_id` integer field (instead of a `project` string field). This `project_id` field will store the `id` of the relevant project from the projects table.

We will now go through how to set this up.

### Creating the project model

Creating the project model is very similar to how we created the task model in the first place. In the `project_manager` folder we will run a new `rails generate scaffold` command:

    $ rails generate scaffold project name:string

Here we specify only one attribute - the name, which we want to be a string. We now need to migrate the database to create the new table:

    $ rake db:migrate

If you restart your server, you should now be able to view the new project pages in your browser at [localhost:3000/projects](http://localhost:3000/projects). You have a working project model, but it isn't connected to the task model in any way.

### Modifying the tasks table

The next step we need to do is change the `project` string column to a `project_id` integer column in the databse. In rails it is important to call the column `project_id` - if you do this rails will know that its the column for specifying a relationship with the tasks and projects table. (It is possible to call it something else, but this will require more work later. You should embrace rails' philosophy of convention over configuration!) To change the column we need to generate a database migration:

    $ rails generate migration change_product_to_product_id
    invoke  active_record
    create    db/migrate/20130814112241_change_product_to_product_id.rb

Rails has created an empty database migration file in `db/migrate/20130814112241_change_product_to_product_id.rb`:

{% highlight ruby %}
class ChangeProductToProductId < ActiveRecord::Migration
  def change
  end
end
{% endhighlight %}

In this we need to write the code to

* remove the project column
* add the project_id column

I found out what these command were by reading the [Rails migrations guide](http://edgeguides.rubyonrails.org/migrations.html#changing-tables):

{% highlight ruby %}
class ChangeProductToProductId < ActiveRecord::Migration
  def change
    remove_column :tasks, :project, :string
    add_column :tasks, :project_id, :integer
  end
end
{% endhighlight %}

Notice how in the `remove_column` line we specify that the column we're removing is a `:string`. This isn't strictly necessary for the removal, but will make our migration *reversible* - after migrating we will be able to undo it by running `rake db:rollback` if needed.

We now need to run this migration to update the table:

    $ rake db:migrate

### Telling the models about each other

Our database tables are now correctly set up. The final thing we have to do is let the models in the code know that they are related to one another. To do this you need to make changes to the `app/models/task.rb` and `app/models/project.rb`:

{% highlight ruby %}
# in task.rb
class Task < ActiveRecord::Base
  belongs_to :project

  def overdue?
    due_date < Date.today && !completed?
  end
end

# in project.rb
class Project < ActiveRecord::Base
  has_many :tasks
end
{% endhighlight %}

These statements add some methods to the `Task` and `Project` models to do with the relationship. You can try out the following in the `rails console`:

{% highlight ruby %}
# first set up some models to play with
p = Project.new(:name => "Housework")
p.save

t1 = Task.new(:name => "Washing up")
t2 = Task.new(:name => "Ironing")

# set t1's project, notice how the project_id has been updated on t1
t1.project = p
t1.save

# look at p's tasks
p.tasks

# set t2's project (and save it) by adding it to p's tasks
p.tasks << t2
{% endhighlight %}

{% exercise %}
1. Create the project model and migrate the database:

        $ rails generate scaffold project name:string
        $ rake db:migrate

2. Change the `project` column in the `tasks` table to `project_id`:

        $ rails generate migration change_product_to_product_id

    and then change the generated migration file to:

        class ChangeProductToProductId &lt; ActiveRecord::Migration
          def change
            remove_column :tasks, :project, :string
            add_column :tasks, :project_id, :integer
          end
        end

    and then migrate the database:

        $ rake db:migrate

3. Make the changes to app/models/task.rb and app/models/project.rb:

        # in task.rb
        class Task &lt; ActiveRecord::Base
          belongs_to :project

          def overdue?
            due_date &lt; Date.today &amp;&amp; !completed?
          end
        end

        # in project.rb
        class Project &lt; ActiveRecord::Base
          has_many :tasks
        end

4. Try out the methods given above in the `rails console`.
{% endexercise %}