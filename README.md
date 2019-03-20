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

