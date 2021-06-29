---
theme: uncover
_class: lead
paginate: true
---

# **Rails trainings**

Advanced concepts

---

# **Part 1** - Where to write logic

---

## Models

- Represent the data
- Interact with the database (postgreSQL)
- Check for validity of data 
- Relations between models
- Validation
- Before filters
- Scopes
- Creator and updater

---

## Controllers 

- Find the correct view 
- Check permissions
- Instance variables
- Concerns 

---

## API 

- [public API](https://app.podigee.com/api-docs) stored in `app/controllers/api/v1` 
- private API stored in `app/controllers/api/` 
- how to find endpoints

--- 

## Decorators, helpers and cells

---

## lib folder

extended modules for your application.

---

## Service object pattern

`app/service` folder

---

# **Part 2** - Concepts

---

## Environments

`RAILS_ENV=`
- production
- development
- test

---

## When to use inheritance

- example with hubspot lib

---

## Everyting is synchronous in Rails

---

## Namespaces

---

## [Caching](https://guides.rubyonrails.org/caching_with_rails.html)

low-level caching `Rails.cache` : `write`, `fetch`, `delete`, `clean`

---

## Memoization

```ruby
def user
  @user ||= episode.user
end
```

---

## [Engine](https://guides.rubyonrails.org/engines.html) and [middleware](https://guides.rubyonrails.org/rails_on_rack.html)

- rack: interface for developing web applications
- `rails middleware`

--- 

# **Part 3** - tools

---

## [Migrations](https://guides.rubyonrails.org/v3.2/migrations.html#creating-a-migration)

- `rails generate migration AddColumnNameToModel column_name:string`
- `rails db:migrate`
- `rails db:rollback`
- change block
- reversible block
- `foreign_key: true` `null: false` `default: false`
- schema configured in `db/schema.rb`
<!-- ~/work/podigee/db/migrate/20201012125213_change_podcasts_notification_method_default_to_email.rb -->

---

## [Routing](https://guides.rubyonrails.org/routing.html)

- configured in `config/routes.rb`
- namespaces and scopes
- constraints
```ruby
resources :networks, only: %i[index show create destroy]
```
<!-- show `~/work/podigee/app/controllers/networks_controller.rb` -->

---

## Rake tasks

- stored in `lib/tasks`
- `rails g task namespace task_name`
- `rake -T`
- `one_off` folder
- used under the hood to run migration or tests 

---

## Log

- levels : debug, info, warn, error [fatal, unknown]
- `Rails.logger.info "Addon #{addon['id']} already exists. Skipping"`
- stored in `log/`
- Sentry 

```ruby
begin
  # something is failing here
rescue SomeException => e
  ErrorTracker.exception(e)
end
```

---

## Debugging

```ruby
binding.pry
```

---

## [Asset pipeline](https://guides.rubyonrails.org/asset_pipeline.html)

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

## [ActionMailer](https://guides.rubyonrails.org/action_mailer_basics.html)

- `rails generate mailer UserMailer welcome_email`
- `app/views/layouts/email.html.haml`

### ActionMailer::Preview

- [mailer preview index](https://app.podigee.local:3000/rails/mailers/)
- [app/mailer_previews/user_mailer_preview.rb](https://app.podigee.local:3000/rails/mailers/user_mailer/email_verification)

---

## Sidekiq

- run jobs in the background
- `config/sidekiq_schedule.yml`
- how to debug a job ?
- [web overview](https://admin.podigee.dev/analytics/sidekiq/)

---

## Credentials

```shell
rails credentials:edit --environment development
```

---

## Serializers

- filter attributes of models
- used for response from api

```ruby
response 200 do
  key :description, 'listener deactivated'
  schema do
    key :'$ref', :Listener
  end
end
```

`serializers/api/v1/listener_serializer.rb`

---

## Gems

- gems and bundler
- gemfile

---

## Specs

- VCR (HTTP interactions)
- fixtures (test data)
- factory (initializer with default values)
- unit test vs feature test

---

https://app.podigee.com/analytics/pghero/space

<!-- feed xml generator -->
<!-- rails admin -->
