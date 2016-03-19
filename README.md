# ti-ionic-dev-app

This app is an example of an ionic project that is set up to be used to develop the [ti-ionic](https://github.com/toru-interactive/ti-ionic) repo.

to set up an app to develop ti-cms...
-------------------------------------
-------------------------------------

*set your app up for sass*

	ionic setup sass

*make sure your bower includes the following devDependencies and resolutions.*

	{
		"name": "my-app-name",
		"devDependencies": {
			"angular-animate": "1.5.*",
			"angular-dynamic-locale": "0.1.*",
			"angular-mandrill": "^0.0.2",
			"angular-resource": "1.5.*",
			"angular-sanitize": "1.5.*",
			"angular-translate-loader-static-files": "^2.9.0",
			"angular-translate": "2.10.*",
			"angular-ui-router": "0.2.*",
			"angular": "1.5.*",
			"ionic": "driftyco/ionic-bower#1.2.4",
			"jquery": "~2.1.4",
			"ng-cordova-oauth": "^0.2.3",
			"ngCordova": "^0.1.24-alpha",
			"platform.js": "platform#~1.3.1"
		},
		"resolutions": {
			"angular": "1.5.*",
			"angular-animate": "1.5.*",
			"angular-sanitize": "1.5.*"
		}
	}

*after running `bower-update` clone the ti-ionic repo into `www/lib` and choose your
branch. note: make suer there's a www/lib folder there before installing*

*add node packages*

	npm install babel-preset-es2015 --save;
	npm install gulp --save;
	npm install gulp-babel --save;
	npm install gulp-concat --save;
	npm install gulp-if --save;
	npm install gulp-jshint --save;
	npm install gulp-minify-css --save;
	npm install gulp-ng-html2js --save;
	npm install gulp-notify --save;
	npm install gulp-rename --save;
	npm install gulp-sass --save;
	npm install gulp-sort --save;
	npm install gulp-strip-debug --save;
	npm install gulp-tape --save;
	npm install gulp-uglify --save;
	npm install gulp-util --save;
	npm install jshint --save;
	npm install jshint-stylish --save;
	npm install tap-colorize --save;
	npm install tape --save;
	npm install yargs --save;

*add cordova in app broswer plugin*

	cordova plugin add cordova-plugin-inappbrowser

*replace the contents of scss.app.scss with this*

	@import "../www/lib/ti-ionic/src/scss/ti-ionic";

*in your gulpfile, require the ti-ionic tasks and pass argv to them*

	require ('./www/lib/ti-ionic/gulp-tasks/scripts')(gulp, yargs);

*Add the 'ti-wacth task to your gulp watch task'*

	gulp.task (
	  'watch',
	  ['ti-watch'],

	  ...
	);

*set your ionic.project watch patterns to...*

	{
	  ...

	  "watchPatterns": [
		"www/**/*",
		"!www/css/**/*",
		"www/css/**/*.min.css",
		"!www/lib/**/*",
		"www/lib/ti-ionic/tmp/ti-ionic.js"
	  ]
	}

*import the script into www/index.html*

  `<script src="lib/ti-ionic/tmp/ti-ionic.js"></script>`

*import the following scripts (note no ionic.bundle.js - so we can use ajs v1.5)*

	<!-- scripts -->
	<script src="cordova.js"></script>
	<script src="lib/angular/angular.min.js"></script>
	<script src="lib/ionic/js/ionic.js"></script>
	<script src="lib/ionic/js/ionic-angular.js"></script>
	<script src="lib/angular-animate/angular-animate.min.js"></script>
	<script src="lib/angular-dynamic-locale/dist/tmhDynamicLocale.min.js"></script>
	<script src="lib/angular-mandrill/dist/angular-mandrill.js"></script>
	<script src="lib/angular-resource/angular-resource.min.js"></script>
	<script src="lib/angular-sanitize/angular-sanitize.min.js"></script>
	<script src="lib/angular-translate/angular-translate.min.js"></script>
	<script src="lib/angular-translate-loader-static-files/angular-translate-loader-static-files.min.js"></script>
	<script src="lib/angular-ui-router/release/angular-ui-router.min.js"></script>
	<script src="lib/ng-cordova-oauth/dist/ng-cordova-oauth.min.js"></script>
	<script src="lib/ngCordova/dist/ng-cordova.min.js"></script>
	<script src="lib/ti-ionic/tmp/ti-ionic.js"></script>
	<!-- // -->
	<script src="js/ti-ionic-app.min.js"></script>
