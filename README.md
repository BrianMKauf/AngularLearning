# AngularLearning

These notes were taken, starting July 25th, and most recently updated on the latest revision date, to better understand the Angular framework.

Resources used for these notes:
* [https://angular.io/guide/quickstart](https://angular.io/guide/quickstart)
* [https://en.wikipedia.org/wiki/Angular_(application_platform)](https://en.wikipedia.org/wiki/Angular_(application_platform))

## Angular vs AngularJS
AngularJS was the first version of Angular. Angular 2 was a rewrite of AngularJS, currently, Angular 6.X.X is available. When speaking about Angular, it is common to refer to the newer Angular as "Angular" while the older version 1 of Angular is referred to as "AngularJS"

## System Setup
To run Angular applications on your machine you will need a few applications. (These steps were completed on a Mac) :

1. Install [homebrew](https://brew.sh/) a package manager and installer for Mac OS
1. Then, in a terminal window, install npm and node using the command `brew install npm` (node should be installed as well with this command)
1. Then, ensure node and npm were installed properly by checking their version, use the command `npm -v` and `node -v` and verify their versions
1. Finally, install Angular-CLI using the command `brew install angular-cli`. You can verify the version of angular by typing `ng -v`
     
This should complete the system requirements needed to run an angular application on your Mac. 

## Hello World

1. To create your first project, type `ng new my-app`. This will create a new project and default app called "my-app"
1. After the process is finished, navigate into my-app directory (`cd my-app`), and type the command `ng serve -o`(This command starts the server, watches your files, and rebuilds the app if it detects changes. The -o command opens the app in your default browser. You can always open the app at the default port `http://localhost:4200
1. Now that you have an app that displays text, let's change up the text. The first thing we should do is update the unit test to validate the new text. Navigate to the file **app.component.spec.ts** within *src/app*. To run the tests within IntelliJ, follow the guide [here](https://www.jetbrains.com/help/idea/run-debug-configuration-karma.html)

In the spec(specification) file, we will see two tests validating the text that is displayed. The first test we need to update is the test with the expectation: `should have as title app`. Let's change the text to say `my First Angular App`. Run the test and it should fail. Now, go and update the file **app.component.ts** to have the text `my First Angular App`. The test should pass! 

However, if we run all of the tests, we will see we have broken another test, (`should render title in a h1 tag`). Update this test as well to make it pass. 

Congratulations!! You have successfully updated the unit tests! These tests typically test functionality of a specific component within Angular. Angular also uses end to end (E2E) tests that validate, you guessed it, end to end functionality! Since this is a simple app, your E2E test is not much different then the unit test. However, it does startup and instance of the app and validate some text! Run the E2E tests through the npm plugin and see what happens. The E2E test should fail as the text you changed is no longer what the test is expecting. In a TDD shop, you normally would first, "update" an E2E test to fail with the new output or functionality you would like. Then, you would update the unit tests with the functionality you would like. Once you have a unit test that is failing for your updated functionality, you would go into the code (i.e. app.component.ts or app.component.html) and update the file to pass the unit test. Once the unit test passes you then want to have the E2E test pass. Then repeat the whole process over again with new functionality!


Finally, if you want to change the style of the text, open the `app.component.css` file and add the following stype:

~~~
h1 {
  color: #369;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 250%;
}
~~~


There it is, your first Hello World Angular App!!

## Angular File Structure

To better understand what each file does, see below:

app/app.component.{ts,html,css,spec.ts} - Defines the AppComponent along with the HTML template, CSS stylesheet, and a unit test. This is the root component, which will turn into the tree of nested components as the project evolves.

app/app.module.ts - Defines AppModule, the root module that tells Angular how to assemble the application. Currently, it only has the app component.

assets/* - A place to put images and other files you want to be copied wholesale when you build your application

environments/* - A place to put one file for each environment your apps live in. These contain the configuration for rest endpoints, tokens, etc...

index.html - The main HTML page that is served when someone visits your site. Most of the time you'll never need to edit it. The CLI automatically adds all js and css files when building your app so you never need to add any <script> or <link> tags here manually
     
karma.conf.js - Unit test configuration for the Karma test runner, used when running ng test

For more information on the files, see the documentation [here](https://angular.io/guide/quickstart)
