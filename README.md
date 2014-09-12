ember-cli-bootstrap-sass
========================

###ember-cli-bootstrap-sass requires ember-cli version '0.0.41' or later

###You will need to have bower installed globablly to use this addon.
If you don't have bower installed, install it with:
`npm install -g bower`

This is an ember-cli addon that includes styles from [official Sass port](http://getbootstrap.com/css/#sass) of [Twitter Bootstrap](http://getbootstrap.com/) into your ember-cli project.

This addon utilizes the [bootstrap_for_ember](https://github.com/ember-addons/bootstrap-for-ember) library, which provides a collection of Ember components based on Twitter Bootstrap V3.
You can find documentation for usage [here](https://github.com/ember-addons/bootstrap-for-ember).

#Usage

In the root of your ember-cli project directory, run:
```bash
npm install --save-dev ember-cli-bootstrap-sass
```

You should now have access to bootstrap styles and the components
provided by [bootstrap_for_ember](https://github.com/ember-addons/bootstrap-for-ember). Enjoy!

#Configuration

Import Bootstrap styles in `app/styles/app.scss`

```javascript
@import "bootstrap";
```

By default all of Bootstrap is imported.

You can also import components explicitly. To start with a full list of modules copy [bootstrap.scss](https://github.com/twbs/bootstrap-sass/blob/master/assets/stylesheets/bootstrap.scss) file into your `app/styles` folder as `_bootstrap-custom.scss`. Then comment out components you do not want from bootstrap-custom. In the application Sass file, replace `@import 'bootstrap'` with:

```javascript
@import 'bootstrap-custom';
```

##Importing specific bootstrap_for_ember components
By default, all of the bootstrap_for_ember components will be imported
into the project. You can optionally specify exactly which components
should be imported into the project via the `component` option, which
accepts an array of component names:


```javascript
//your-bootstrap-app/Brocfile.js

/* global require, module */

var EmberApp = require('ember-cli/lib/broccoli/ember-app');

var app = new EmberApp({
  'ember-cli-bootstrap-sass': {
    'components': ['bs-alert', 'bs-notifications', 'bs-nav']
  }
});

module.exports = app.toTree();
```


## Importing javascript from Twitter Bootstrap
The goal of this addon is to utilize the bootstrap_for_ember library to
be able to implement Twitter Bootstrap's styles and components in a more
'Embery' way. As such, the addon *does not* include the javascript from
Twitter Bootstrap by default.

In situations where you need functionality that is not provided by
bootstrap_for_ember, you can optionally import the Twitter Bootstrap
javascript into your ember-cli project by setting the
`importBootstrapJS` option to true in your `Brocfile.js`:

```javascript
//your-bootstrap-app/Brocfile.js

/* global require, module */

var EmberApp = require('ember-cli/lib/broccoli/ember-app');

var app = new EmberApp({
  'ember-cli-bootstrap-sass': {
    'importBootstrapJS': true
  }
});

module.exports = app.toTree();
```
