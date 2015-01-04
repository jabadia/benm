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
* sometimes `App` is accessed and sometimes `window.App`... why?

### model & collection
* in `collections/contacts.js`, configures the back-end API url
* in `models/contact.js`, configures the `_id` field and back-end API url

### controller
* create views and renders them
* main view (contacts) is cached in App.views

### views
* associated with handlebars templates

##Part 4 - Publish to Heroku
	$ heroku login
	$ echo "web: node server.js" > Procfile
	$ heroku create
	$ heroku addons:add mongohq
	
	change in server.js url of mongodb to use process.env.MONGOHQ_URL

	$ ... add and commit changes ...	

	$ git push heroku master
	$ heroku ps:scale web=1


# refactoring tasks
1. move server files into single `server` folder
2. add contact form validation on front and back end
3. ...
	