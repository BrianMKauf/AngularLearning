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


Finally, if you want to change the style of the text, open the `app.component.css` file and add the following stype:

~~~
h1 {
  color: #369;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 250%;
}
~~~
