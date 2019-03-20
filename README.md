# VUEJS ON RUBY ON RAILS

## Getting Started

I. Create a Rails application

`rails new vueapp --skip-turbolinks --webpack=vue`

1. We create an Rails app with version 5.2.2.1. Turbolinks work well with Vue but I want to skip it beacuse I'm not use it.

2. Pass `--webpack=vue` option to use Webpack to manage Javascript code. Webpack has been adopted by Rails starting 5.1 to have better support for JavaScript frameworks.

3. When using Asset Pipeline, you put your Javascript code on `app/assets/javascript` . With Webpack, you'll use `app/javascript/packs` instead.

II. Hello Vue

1. Create pagescontroller with welcome action.
`rails generate controller Pages welcome`

2. Set the welcome action as the root of the page.

In `routes.rb`, define: `root 'pages#welcome'`

3. Hello Vue

When using Webpack with Rails, Rails add `app/javascript/packs/hello_vue.js`, this file contains some code. We can customize this file by comment or delete and add some bellow code:

```
import Vue from 'vue/dist/vue.esm'

document.addEventListener('DOMContentLoaded', () => {
  var app = new Vue({
    el: '#app',
    data: {
      message: 'Hello Vue!'
    }
  })
})
```

This code create a object belongs to Vue and we pass `el` and `data` options.

`el` this is element, which seen by Vue.

In `welcome.html.erb` :

```
<h1>Welcome Page</h1>

<div id="app">
  {{ message }}
</div>
```

The `message` in `data` block on the Vue app will appear on `{{ message }}`

Because we use Webpack to manage Javascript code, so in `application.html.erb`, we change `<%= javascript_include_tag 'application' %>` to `<%= javascript_pack_tag 'hello_vue' %>`

Final, `rails server` to see result!

III. Discover Vue

1. v-bind: Bind element/attribute.

2. v-if: Toggle the presence of an element depending on its value.

3. v-for: Through each item on an Array.

4. v-on: Attaches a method to event listeners.
