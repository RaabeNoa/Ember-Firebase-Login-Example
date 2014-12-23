# Ember-firebase-login-example

This is a work flow for web app authentication using [Firebase](https://www.firebase.com/) with Ember via [Ember-CLI.](http://www.ember-cli.com/) 

You will need to sign up for Firebase. Their documentation is good, and you can find out more about how it works [here.](https://www.firebase.com/how-it-works.html)

## Prerequisites

You will need the following things properly installed on your computer.

* [Git](http://git-scm.com/)
* [Node.js](http://nodejs.org/) (with NPM) and [Bower](http://bower.io/)

## Installation

* `git clone <repository-url>` this repository
* change into the new directory
* `npm install`
* `bower install`

###Once you have a link to your Firebase...

You will need to update the following files:
#####config/environment.js
In the first fucntion of the Environment.js file add the name of your Firbase instance to the ENV object. ***Just the name!*** You do not need the full url for this file.

	/* jshint node: true */

	module.exports = function(environment) {
  	var ENV = {
    	firebase_instance: '<THE NAME OF YOUR FIREBASE>',
    	modulePrefix: 'Ember-Firebase-Login-Example',
    	environment: environment,
    	baseURL: '/',
    	locationType: 'auto',
    	EmberENV: {
      	FEATURES: {
        	// Here you can enable experimental features on an ember canary build
        	// e.g. 'with-controller': true
      		}
    	},
    
#####App/adapters/application.js
In the application adapter file is where you wil implement Ember Data and direct it to use Firebase as your store. This file should not need updating, as it pulls its information from your config file.

	import DS from 'ember-data';
	import ENV from 'Ember-Firebase-Login-Example/config/environment';

	export default DS.FirebaseAdapter.extend({
  		firebase: new window.Firebase('https://' + ENV.firebase_instance + '.firebaseio.com')
	});




## Running / Development

* `ember server`
* Visit your app at [http://localhost:4200](http://localhost:4200).

### Code Generators

Make use of the many generators for code, try `ember help generate` for more details

### Running Tests

* `ember test`
* `ember test --server`

### Building

* `ember build` (development)
* `ember build --environment production` (production)

### Deploying

Specify what it takes to deploy your app.

## Further Reading / Useful Links

* [ember.js](http://emberjs.com/)
* [ember-cli](http://www.ember-cli.com/)
* Development Browser Extensions
  * [ember inspector for chrome](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi)
  * [ember inspector for firefox](https://addons.mozilla.org/en-US/firefox/addon/ember-inspector/)

