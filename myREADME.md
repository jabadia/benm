#Boilerplate web app using Backbone.js, ExpressJS, node.js, MongoDB
following tutorial from [here](http://kroltech.com/2013/12/boilerplate-web-app-using-backbone-js-expressjs-node-js-mongodb/#.VJdP9oAIA)

## benm = backbone, express, node, mongodb

Using:

* Backbone.js & Marionette
* node.js & ExpressJS
* MongoDB & Mongoose
* Handlebars
* Grunt.js
* Bower
* and Browserify!

##Part 0 - Project Setup and Dependencies
* node.js and npm `already installed`
* mongodb, installed with `brew install mongodb`
* npm install

##Part 1 - Backend with node.js and express.js
* express
* routes
* controllers
* handlebars
* tests? see [here](http://kroltech.com/2014/02/node-js-testing-with-mocha-chai-sinon-proxyquire/#.VJ3zAsB8)

##Part 2 - Development Tools - bower, grunt, browserify
* grunt plug-ins
* TDD see [here](http://kroltech.com/2013/11/javascript-tdd-with-jasmine-and-karma/)

##Part 3 - Front-end app with Backbone.js & Marionette.js
* uses browserify to manage module dependencies in front-end as in node.js
* everything ends up in `myapp.js`, because browserify follows the require() tree and puts everything (including handlebar templates) in the same app.js file, that ends up (together with `vendor.js`) in `myapp.js`

### main.js
* marionette events [doc here v1.4.1](http://marionettejs.com/docs/v1.4.1/marionette.application.html#application-event) ([current version doc](http://marionettejs.com/docs/marionette.application.html#application-events))
* looks like `app:start` is a custom event, not a Marionette event
* `App` is an empty `{}`object that contains a new `Marionette.Application()` in `App.core` attribute, instead of extending `Marionette.Application`... why?
* 