# flux-rails-assets

[Flux](https://github.com/facebook/flux) and [Node EventEmitter](https://github.com/joyent/node) for Rails Asset Pipeline for use with [react-rails gem](https://github.com/reactjs/react-rails)

- Flux version: [2.0.2](https://github.com/facebook/flux/releases/tag/2.0.2)


## Installation

Add this line to your application's Gemfile:

  ```ruby
  gem 'flux-rails-assets'
  ```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install flux-rails-assets


## Usage

Require flux and the eventemitter in your application.js:

  ```js
  //= require flux
  //= require eventemitter
  ```

This will create two globals you can use to create your application's dispatcher ans stores:

  ```js
  var AppDispatcher = new FluxDispatcher();

  var ExampleStore = new EventEmitter();

  ExampleStore.dispatchToken = AppDispatcher.register(function (payload) {
    var action = payload.action;

    switch(action.type) {
      
      case 'EXAMPLE_ACTION':
        ExampleStore.emitChange();
        break;

      default:
        // do nothing
    }
  });

  ```


## Credits

[Flux](https://github.com/facebook/flux) by [Facebook](http://www.facebook.com)
[Node EventEmitter](https://github.com/joyent/node) by [Joyent](https://www.joyent.com/)

Written by [Stefan Ritter](https://github.com/stefanitter), released under the [MIT license](https://github.com/mariopeixoto/flux-rails/LICENSE).
