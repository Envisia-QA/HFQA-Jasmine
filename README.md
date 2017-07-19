# HFQA Jasmine js Testing Project

This document outlines the dependencies, configuration, and instructions for
setting up and using the HFQA Jasmine testing project.  This will not cover syntax or provide guidance for writing code, only for using the already included test specs.

## Dependencies
* [node.js](https://nodejs.org/en/)
* [Java dev kit (JDK)](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
* [Jasmine2.0 for node](https://jasmine.github.io/edge/node.html)
* [Protractor](http://www.protractortest.org/#/)
* [Selenium-Webdriver](http://www.seleniumhq.org/projects/webdriver/)
* Terminal/Dev kit of your choice- I prefer [console2](https://sourceforge.net/projects/console/files/) and [Visual Studio Code](https://code.visualstudio.com/)
    * NOTE: VS Code has it's own terminal extension built in.

## Setup

* First get your terminal and/or dev environment installed and set up how you'd like, install node.js, and install the latest JDK.
    * use `java -version` and `node --version` to confirm they're installed.  
* Next, create a folder for your new project to live, make sure it's easy to find, such as your documents or right on your desktop.
* In your terminal, navigate to the folder you created and execute the node initialization command: `npm init`.
    * This will prompt the terminal to ask multiple questions regarding the project, and then populate a package.json file with the data you provided.
* Once this is done, we'll need to install the modules needed by the project using NPM.  To do this run the following commands in your terminal.  The `--save` and `-dev` parameters will save these modules as dev dependencies in your package.json file.  Refer to the existing package.json file included with this project as an example.  `-g` will install the module and add it to your global variables.
```
    npm install selenium-webdriver --save-dev
    npm install jasmine --save-dev
    npm install jasmine-core --save-dev
    npm install jasmine-node --save-dev
    npm install requirejs --save-dev
    npm install protractor-jasmine2-screenshot-reporter --save-dev
    npm install -g protractor
```
* Once those are all installed, if you have not already, clone the contents of this project to the same folder you've been running all of these commands from, with the exception of the package.json and package-lock files; as you've created your own package.
* Next, add protractors webdriver by running `webmanager-update`.  Refer to the protractor documentation for installing/managing specific webdrivers and versions.
* That's it, you should be fully configured.

## Usage

Protractor tests are run through a configuration file.  default is conf.js.  You'll notice a conf.js as well as another conf-sauce.js file in this project.  conf.js will run tests locally, while conf-sauce.js will execute tests through Sauce Labs.  The former should work out of the box provided all steps have been followed, while the latter will require a SauceLabs account and additional conffiguration (will add steps later).

For now, we'll focus on local tests.  Open the conf.js file in your editor.  Each section will be commented to explain it's purpose.  The main areas to change will be `specs` and `multiCapabilities` which will determine what tests are run, and what browsers will be used.

## To Do

* [ ] Add project files
* [ ] Expand Usage instructions.
* [ ] Add SauceLabs specifics
* [ ] add comments to conf and conf-sauce js files
* [ ] add basic template tests
