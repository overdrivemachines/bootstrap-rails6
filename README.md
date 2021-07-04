# README

Sample app to add Bootstrap 5, JavaScript and Images to Rails 6.1 App

## Version

- ruby 3.0.1p64 (2021-04-05 revision 0fb782ee38) [x86_64-linux]
- Rails 6.1.4
- Bootstrap 5.0.2

## Instructions

1. In `application.html.erb` change to stylesheet_pack_tag as shown:
```ruby
<%= stylesheet_pack_tag 'application', media: 'all', 'data-turbolinks-track': 'reload' %>
```
2. Create new files/folders in `app/javascript`:
  ```
  app/javascript
  └───images
  │       test.jpg
  │
  └───packs
  │       application.js # already exists
  │       application.scss
  │
  └───src
  │       my_script.js
  │
  └───stylesheets
          my_styles.scss
  ```

  ```bash
  $ touch packs/application.scss
  $ mkdir -p src && touch src/my_script.js
  $ mkdir -p stylesheets && touch stylesheets/my_styles.scss
  $ mkdir -p images && wget -O images/test.jpg http://lorempixel.com/640/480/

  ```
