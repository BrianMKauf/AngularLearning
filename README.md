# AngularLearning

These notes were taken, starting July 25th, and most recently updated on the latest revision date, to better understand the Angular framework.

## Angular vs AngularJS
AngularJS was the first version of Angular. Angular 2 was a rewrite of AngularJS, currently, Angular 6.X.X is available.

## System Setup
To run Angular applications you will need a few dependencies. (These steps were completed on a Mac) 
     1. Install [homebrew](https://brew.sh/) a package manager and installer for Mac OS
     1. Then, in a terminal window, install npm and node using the command `brew install npm` (node should be installed as well)
     1. Then, ensure node and npm were installed properly by checking their version, use the command `npm -v` and `node -v`
     1. Finally, install Angular-CLI using the command `brew install angular-cli`
     
This should complete the system requirements needed to run an angular application on your Mac. 

## Hello World

1. To create your first project, type `ng new my-app`. This will create a new project and default app called "my-app"
1. After the process is finished, navigate into my-app directory (`cd my-app`), and type the command `ng serve -o`(This command starts the server, watches your files, and rebuilds the app if it detects changes. The -o command opens the app in your default browser. You can always open the app at the default port `http://localhost:4200
