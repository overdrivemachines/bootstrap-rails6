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

  ```console
  $ touch packs/application.scss
  $ mkdir -p src && touch src/my_script.js
  $ mkdir -p stylesheets && touch stylesheets/my_styles.scss
  $ mkdir -p images && wget -O images/test.jpg http://lorempixel.com/640/480/

  ```

3. Add Bootstrap and Popper JS to app
```shell
$ yarn add bootstrap
$ yarn add @popperjs/core

```

4. Include Bootstrap in `application.js` file:
```javascript
require.context("../images", true)
import "bootstrap"
import "@popperjs/core"
import "../src/my_script.js"
```
Include Bootstrap in `application.scss` file:
```scss
@import "~bootstrap/scss/bootstrap.scss";
@import "../stylesheets/my_styles.scss"

```

5. Create home controller with index action
```bash
$ rails g controller home index
```

6. Add Bootstrap modal component in `app/views/home/index.html.erb`
```html
<!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
  Launch demo modal
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
```

7. Add Image tag in `app/views/home/index.html.erb`
```html+erb
<br>
<%= image_pack_tag("media/images/test.jpg") %>

```
