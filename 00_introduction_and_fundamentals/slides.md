---
theme: uncover
_class: lead
---

# **Rails trainings**

Introduction & fundamentals

---

## Where to get informations

- [Rails guide](https://guides.rubyonrails.org/)
- [Rails API](https://api.rubyonrails.org/)
- [Gist with common commands](https://github.com/girardof/rails_trainings/blob/main/rails_gist.md)

---

## What is Rails ?

**Philosophy**

- [Don't Repeat Yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
- [Convention Over Configuration](https://en.wikipedia.org/wiki/Convention_over_configuration)
- [MVC pattern](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)

---

## MVC pattern

![mvc pattern diagram](images/mvc.png)
<!-- divides the responsibilities of an application to make it easier to understand -->

---

## Views 
- Present data to user
- Allow user to interact with the data

**Tools and library**

- Haml
- Angular 1
- Helpers
- [Internationalization](https://guides.rubyonrails.org/i18n.html)
- [Coffee script](https://coffeescript.org/)
- Cells
<!-- helpers are available in all views 
     example : `network_episode_permalink_url` in `app/helpers/blog_helper.rb` 
     specify they should not create new cells -->

---

## Views - [Angular 1](https://devdocs.io/angularjs~1.5/) 

- difference `ngShow`/`ngHide` and `ngIf`
<!-- ngIf include or not the section in the DOM while ngShow and ngHide uses css to display or hide -->
 
 ```yaml
 %span{ng: {mouseenter: 'showEdit = true', mouseleave: 'showEdit = false'}}
   %span{ng: {click: 'edit()', hide: 'editMode'}}
   %a{ng: {click: 'edit()', show: 'showEdit'}}
   
.widget-box.transparent{ng: {if: 'open_invoice.id && should_show_open_invoice_details()'}}
 ```
---

### Views - [Haml](https://haml.info/)

<!-- indentation matters
     quick word on the syntax -->
**Syntax** 

```haml
%section.container
  %h1= post.title
  %strong.code#message Hello, World!
```

**Partials**

```haml
= render 'sidebar'
```

**Ruby variables**

```haml
.content
  = @podcast.name
```

---

### Views - Internationalization

- Uses locales files
- Syntax :
```
t('reset_password.reset_page.password_changed')
I18n.t('forgot_password.reset_cannot_be_delivered')
```

---

## Models

- Represent the data
- Interact with the database (postgreSQL)
- Check for validity of data 
- Relations between models
- Validation
- Before filters
- Scopes
<!-- scope user : with_domain -->

---

## Controllers 

- Find the correct view 
- Check permissions
- Instance variables
- Concerns 

---

## [Active record](https://guides.rubyonrails.org/active_record_basics.html) 

**database manager**

- Schema configured in `db/schema.rb`
- Uses migrations files stored in `db/migrate`
<!-- contain the current schema of the database
     automatically updated with migrations 
     fire a rails console and show how to quickly CRUD in the db
     run a migration file -->

--- 

## Environments

`RAILS_ENV=`
- production
- development
- test
<!-- in console `RAILS_ENV=test bundle exec rails c` uses a different database than development
     dev is the default 
     same for running migrations -->

---

## [Routing](https://guides.rubyonrails.org/routing.html)

Configured in `config/routes.rb`

```ruby
resources :networks, only: %i[index show create destroy]
```
<!-- show `~/work/podigee/app/controllers/networks_controller.rb` -->

---

## Asset pipeline

- Sprockets 
- Webpack
- [Why Rails uses both](https://rossta.net/blog/why-does-rails-install-both-webpacker-and-sprockets.html)

```js
// Sprockets
//= require jquery

// Webpack
import '../application.css'
```

<!-- for sprockets show `application.js` and `application.css` 
     sprockets : written in ruby, legacy -->
---

## Rake tasks

- Small script to perform specific action
- Stored in `lib/tasks`
- Used to run migrations
- `one_off` folder
<!-- show that rails migrate command uses rake underneath -->

---

## API 

- [public API](https://app.podigee.com/api-docs) stored in `app/controllers/api/v1` 
- private API stored in `app/controllers/api/` 
- how to find endpoints
<!-- ideally they should not create anything in the private as we want to get ride of it -->

--- 

## Dependencies

- ruby gems
- bundler 
- gemfile

---

## Sidekiq

- run tasks in the background
- scheduler

---

## Services folder

- creator and updator files 
<!-- if enough time -->
