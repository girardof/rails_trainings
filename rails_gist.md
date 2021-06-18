# Commands
## Start rails server

`bundle exec rails server`

## Start rails console

`bundle exec rails console`

## Run migration

`bundle exec rails db:migrate`

## Show all routes

`bundle exec rails routes`

## Rspec
### Run all specs

`bundle exec rspec`

### Run all specs of a specific file

`bundle exec rspec spec/models/user_spec.rb`

### Run only failing specs from previous run

`bundle exec rspec --only-failing`

# Rails basics

From the rails console or inside a ruby file 

## Get all objects of a specific class stored in the database

`User.all`

## Get the number of object of a specific class stored in the database

`User.all.count`

## Get a specific object stored in the database
### .find

`User.find(1)` 1 in this example is the id of the user you wish to fetch

### .find_by

`User.find_by(email: 'test@podigee.com')` works with any attribute of the class; return only the first matching object

### .last

`User.last` retrieve the last User created in the database

### .where

`User.where("locale = :given_locale and id > :given_id", {given_locale: 'en', given_id: 1})` SQL statement directly; return all matching objects

## Change value of attribute in the database

```ruby
user_to_change = User.find(1)
user_to_change.hubspot_contact_id = '0000001'
user_to_change.save
```

## Delete 

```ruby
user_to_delete = User.find(1)
user_to_delete.delete
```
