---
theme: uncover
_class: lead
paginate: true
---

# **Rails trainings**

Introduction and fundamentals

---

## Where to get informations

- [Rails guide](https://guides.rubyonrails.org/)
- [Gist with common commands](https://github.com/girardof/rails_trainings/blob/main/rails_gist.md)


---

## Rails philosophy 

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
- Coffee script
- Cells

---

## Views - [Angular 1](https://devdocs.io/angularjs~1.5/) 

- difference `ngShow`/`ngHide` and `ngIf`
<!-- ngIf include or not the section in the DOM while ngShow and ngHide uses css to display or hide -->
  
---

### Views - [Haml](https://haml.info/)

<!-- indentation matters; quick word on the syntax; -->
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

# Models

- Represent the data
- Interact with the database
- Schema (`db/schema.rb`)
<!-- contain the current schema of the database; automatically updated with migrations -->

---

# Controllers 

- Concerns 
- Instance variables

---

# Environments

---

# Routing

---

# Rake tasks

- how to run migrations

---

# Image server

--- 

# API 

- difference between public and private
- how to find endpoints

---

# active record

- console

--- 

# services fodler

- creator and updator files (if enough time)
