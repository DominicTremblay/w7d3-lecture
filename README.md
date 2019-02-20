# W7D3 - Lecture

## Ruby on Rails

- Started as a project at Basecamp

- Developed by

- Rails is composed of several libraries

- Ideal for rapid development and CRUD operations (not so for real time app)

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
- Vews -> Rendering of the UI with the data
- Controllers -> respond to ressources

### Convention over configurations

#### rails command-line

- generate
- console
- new
- api
- server (s)
- db

### Jungle

- First experience working with existing code

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

#### Readme

- config/database.yml
- config/secrets.yml
- .env

#### Schema

- schema.rb is a representation of the db
- you cannot modify it, this is managed by rails

  ** Rails has a lot of files. Use shortcuts such as CMD|CTRL-P **

#### Demo of Jungle

- Running the app

`rails s -b 0.0.0.0`

- Go through the logs

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

#### Controllers

- Go over the controllers

#### Models

- Go over the models

#### Views

- Go over the views
  - layout
  - partials

#### Other subjects

- params
- debugging
  - pry
  - console in views
  - rails console
  - error screen
