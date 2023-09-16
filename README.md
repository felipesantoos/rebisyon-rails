# rebisyon-rails

Uma plataforma para o gerenciamento de estudos e revisões feita com Ruby on Rails.

# Ruby on Rails

- Rails is a full-stack framework.
- Render templates.
- Update databases.
- Send and receive e-mails.
- Maintain live pages via WebSockets.
- Enqueue jobs for assincronous work.
- Store uploads in the cloud.
- Provide solid security protections for common attacks.
- Rails is a opinionated software.
- Don't Repeat Yourself.
- Convention Over Configuration.
- ruby --version
- sqlite3 --version
- gem install rails
- rails --version
- rails new blog
- rails new --version
- app - Contains the controllers, models, views, helpers, mailers, channels, jobs, and assets for your application.
- bin - Contains the rails script that starts your app and can contain other scripts you use to set up, update, deploy, or run your application.
- config - Contains configuration for your application's routes, database, and more.
- config.ru - Rack configuration for Rack-based servers used to start the application.
- db - Contains your current database schema, as well as the database migrations.
- Gemfile & Gemfile.lock - These files allow you to specify what gem dependencies are needed for your Rails application. These files are used by the Bundler gem.
- lib - Extended modules for your application.
- log - Application log files.
- public - Contains static files and compiled assets. When your app is running, this directory will be exposed as-is.
- Rakefile - This file locates and loads tasks that can be run from the command line. The task definitions are defined throughout the components of Rails. Rather than changing Rakefile, you should add your own tasks by adding files to the lib/tasks directory of your application.
- README.md - This is a brief instruction manual for your application. You should edit this file to tell others what your application does, how to set it up, and so on.
- storage - Active Storage files for Disk Service.
- test - Unit tests, fixtures, and other test apparatus.
- tmp - Temporary files (like cache and pid files).
- vendor - A place for all third-party code. In a typical Rails application this includes vendored gems.
- .gitattributes - This file defines metadata for specific paths in a git repository. This metadata can be used by git and other tools to enhance their behavior.
- .gitignore - This file tells git which files (or patterns) it should ignore.
- .ruby-version	- This file contains the default Ruby version.
- bin/rails server
- In the development environment, Rails does not generally require you to restart the server; changes you make in files will be automatically picked up by the server.

```ruby
get "/articles", to "articles#index"
```

- bin/rails generate controller Articles index --skip-routes
- When an action does not explicitly render a view (or otherwise trigger an HTTP response), Rails will automatically render a view that matches the name of the controller and action.
- Rails applications do not use require to load application code.
- Application classes and modules are available everywhere, you do not need and should not load anything under `app` with `require`. This feature is called autoloading.
- You only need require calls for two use cases:
  - To load files under the `lib directory.
  - To load gem dependencies that have `require: false` in the `Gemfile`.
- Rails uses the MVC (Model-View-Controller) design pattern by convention.
- A model is a Ruby class that is used to represent data.
- Models can interact with the application's database through a feature of Rails called Active Record.
- bin/rails generate model Article title:string body:text
- Model names are singular, because an instantiated model represents a single data record.
- Migrations are used to alter the structure of an application's database.
- In Rails applications, migrations are written in Ruby so that they can be database-agnostic.
- By default, the create_table method adds an id column as an auto-incrementing primary key.
- The method t.timestamps defines two additional columns named created_at and updated_at. As we will see, Rails will manage these for us, setting the values when we create or update a model object.
- bin/rails db:migrate
- The console is an interactive coding environment just like irb, but it also automatically loads Rails and our application code.
- bin/rails console
- Controller instance variables can be accessed by the view. That means we can reference @articles in app/views/articles/index.html.erb.
- ERB is a templating system that evaluates Ruby code embedded in a document.
- The `<% %>` tag means "evaluate the enclosed Ruby code."
- The `<%= %>` tag means "evaluate the enclosed Ruby code, and output the value it returns."
- Anything you could write in a regular Ruby program can go inside these ERB tags, though it's usually best to keep the contents of ERB tags short, for readability.
- Rails flow:
  - The browser makes a request: GET http://localhost:3000.
  - Our Rails application receives this request.
  - The Rails router maps the root route to the index action of ArticlesController.
  - The index action uses the Article model to fetch all articles in the database.
  - Rails automatically renders the app/views/articles/index.html.erb view.
  - The ERB code in the view is evaluated to output HTML.
  - The server sends a response containing the HTML back to the browser.
- https://guides.rubyonrails.org/getting_started.html#crudit-where-crudit-is-due
