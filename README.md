[![Crowdin](https://d322cqt584bo4o.cloudfront.net/translation-studio/localized.png)](https://crowdin.com/project/translation-studio)
[![Build Status](https://travis-ci.org/unfoldingWord-dev/ts-desktop.svg?branch=develop)](https://travis-ci.org/unfoldingWord-dev/ts-desktop)

translationStudio Desktop
--

A tool to translate the Bible and [Open Bible Stories](http://distantshores.org/openbiblestories) into your own language. You can read more about the purpose of this project at [unfoldingWord](https://unfoldingword.org/apps/#tS).

##Requirements
The official development requirements are available at
* [tS Requirements](https://github.com/unfoldingWord-dev/ts-requirements)

Additional documentation specific to the desktop platforms is available in the [wiki](https://github.com/unfoldingWord-dev/ts-desktop/wiki).

##Contributing
If you would like to contribute to this project please read the [Contributing](https://github.com/unfoldingWord-dev/ts-desktop/wiki/Contributing) article in the wiki.

##Quick Start
First make sure you have [NodeJS](https://nodejs.org/) installed (choose the Current, not LTS). Then, in your terminal/command line window:

	$ npm install -g bower
	$ npm install -g gulp

Then fork this repository and clone your fork.
After the repository has been cloned to your computer run the following command in the new directory to set up your environment

    $ npm install && bower install

##Communicating With Git Server
This application uses git version control to keep track of translations.  Collaboration between translators can be done through a git server.

In order to communicate with the git server, the application uses the urls given in src/config/giteaUrls.json.  Read Gitea's [documentation] (https://docs.gitea.io/en-us/) if you need to know more about how it works.

In order to test creation of new users and other operations that require api authentication, you can place a file named private.json in src/config/ containing the following:

```javascript
[
    {
        "name": "gogs-token",
        "value": "<api token goes here>",
        "meta": {
            "mutable": false,
            "type": "string"
        }
    }
]
```
The api token (application key) for gitea can be created by an administrator.

For more information please read the [wiki](https://github.com/unfoldingWord-dev/ts-desktop/wiki).

###Commands
The following commands are available from within the project directory:

* `$ gulp build --win` builds a windows distribution (other available flags are `--osx` and `--linux`)
* `$ gulp unittest` runs all Mocha unit tests
* `$ gulp unittest --grep [string]` runs the Mocha unit tests that match the string
* `$ gulp` runs the `unittest` task
* `$ gulp integrationtest` runs all Mocah integration tests
* `$ npm start` runs the application (without building it)

> Note: Installation of prince, needed for pdf export from the app, was added to the gulp build task.

> Note: You can open the Chrome Developer Tools while the app is running by pressing `Ctrl+Shift+I` on Windows/Linux or `Cmd-Shift-I` on macOS.
