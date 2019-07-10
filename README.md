# W7D3 - Lecture

## Ruby on Rails

- Started as a project at Basecamp

- Developed by David Heinemeier Hansson

- Rails is composed of several libraries

- Ideal for rapid development and CRUD operations (not so for real time app)

### Rails Opinions

- Optimize for programmers happiness
- Conventions over configuration
- Rails is omakase

[Learn more about Rails' doctrine](https://rubyonrails.org/doctrine/)

### Rails Libraries

- ActiveRecord -> ORM
- ActiveSupport -> a bunch of useful methods like:
  - changing words from singular to plural
  - changing camel case to snake case
  - better handling of time and date
- ActiveModel
- ActionMailer -> Send emails
- ActionPack -> Router
- ActionController -> Controllers
- ActionView -> Rendering of ERB files
- ActionCable -> WebSocket - Real-Time Communication
- Gems -> extend functionality

### MVC

These libraries all follow the same pattern in Rails

[Model View Controller](./MVC_pattern.png)

A way to distribute distinct responsabilities of a web a app:

- Models -> classes provide interface to the data
- Views -> Rendering of the UI with the data
- Controllers -> respond to ressources

#### Benefit

The main advantage of MVC is clear separation of concerns. We can more easily maintain our application.

#### Controllers

- Controllers are getting request from the router and pulling data from the model and trigger the rendering of the view

#### Models

- Provide an interface in object form between the app and the database

#### Views

- The UI part of the app. Using ERB templates to render HTML.

### Convention over configurations

- If you follow the established conventions, you can develop a Rails application in much less time and with many fewer lines of code.

- Freeing you up from all the small decisions

### rails command-line

- `rails g` - Allows you to generate components for your Rails application. You can generate models, controllers, views, migrations, mailers, etc.

- `rails c` - This is your IRB console, with all of your dependencies loaded in so that you can test methods and queries from the CLI. If they don't work here, they're not going to work in your application.

- `rails s` - This starts your server. You will need to restart the server if you change logic in models, controllers, but not views.

- `rails db` - This will put you into the CLI for your database. For example, if you are using PostgreSQL, it would put you into psql.

### Rake

Rake is a task-runner utility for Rails. We can have a list of Rake commands with `Rake -T`

- `rake routes` - This command gives you the output for what routes your app is configured for.

- `rake db:reset` - Reset the database

- `rake db:migrate` - running migration.

- `rake db:version` - latest migration ran.

- `rake db:rollback` - rollback migrations.

- `rake secret` - generate a secret key

### Generate A Rails App

With Rails you can generate an entirely new project scaffold:

`rails new myApp --database=postgresql -T --no-rdoc --no-ri`

For creating a resource (quotes for example):

`rails g scaffold Quote content:string`

### Jungle

- You first experience working with existing code. More often than not, you will have to work with an existing code base.

#### Gemfile

- Ruby 2.3.0
- Rails version 4.2.6
  **Be careful when reading the docs**

#### Installing Gems

```ruby
ruby --version
rvm use 2.3.0
bundle install
```

#### Schema

- schema.rb is a representation of the db
- you should not modify it, this is managed by rails

  ** Rails has a lot of files. Use shortcuts such as CMD|CTRL-P **

=

#### Router

- routes.rb

`bin/rake routes`

- Controller methods match CRUD operations and RESTful patterns
- Controller method syntax:

`controller_name#controller_method`

- Example:

`products#index`

| Controller Method | Corresponding Action  | REST Pattern              |
| :---------------- | :-------------------- | :------------------------ |
| index             | Get the list          | GET /resources            |
| create            | Create a new resource | POST /resources           |
| new               | Display New Form      | GET /resources/new        |
| edit              | Display Edit Form     | GET /resources/:id/update |
| show              | Display one resource  | GET /resources/:id        |
| update            | Update a resource     | PUT /resources/:id        |
| Destroy           | Delete a resource     | DELETE /resources/:id     |

#### Debugging

- debug variable in a view

`<%= debug product %>`

- place raise in your code
- byebug or pry
- console in views
- rails console
- error screen
