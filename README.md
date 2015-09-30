![](https://raw.githubusercontent.com/ics-software-engineering/meteor-application-template/master/doc/meteor-application-template-home.png)

Meteor-application-template is a sample Meteor application that illustrates:

  * A standard directory layout.
  * A standard set of Meteor plugins and example usage (Iron Router, AutoForm, Accounts, Bootstrap, etc.)
  * Simple authorization/authentication and use of settings files for initialization.
  * Simple quality assurance

The goal of this template is to help you get quickly started into simple application development.

## Usage

First, create a new GitHub repository, and clone it into your local workspace.

Second, change directories into your local repo directory, and type the following:

```
% git remote add template https://github.com/ics-software-engineering/meteor-application-template.git
% git fetch template
% git merge -m "merge template into master" template/master
```

Now your repo should contain the contents of the template. To test that everything is OK, run the application:

```
% meteor --settings config/settings.development.json
```

If all goes well, the template application will appear at [http://localhost:3000](http://localhost:3000).  You can login using the credentials in [settings.development.json](https://github.com/ics-software-engineering/meteor-application-template/blob/master/config/settings.development.json), or else register a new account.

## Walkthrough

The following sections describe the major features of this template.

### Directory structure

The top-level structure is:

```
app/        # holds the Meteor application sources
doc/        # holds screenshots and other documentation files.
config/     # holds configuration files, such as settings.development.json
.gitignore  # don't commit IntelliJ project files and config/settings.production.json
.jshintrc   # standards for JSHint.
```

This structure separates documentation files (such as screenshots) and configuration files (such as the settings files) from the actual Meteor application.

The app/ directory contains this structure:

```
client/
  stylesheets/
  templates/
    application/
    home/
    stuff/
lib/
  accounts/
  collections/
  router/
  accounts/
server/
   seeds/
```


## Packages

This application requires a number of additional packages useful for development. Here is the output of `meteor list`, with the built-in Meteor packages removed and some comments elided.

```
aldeed:autoform              5.5.1  Create forms with automatic insert and update
aldeed:collection2           2.5.0  Validation of insert and update operations on the client and server.
accounts-password            1.1.3  Password support for accounts
ian:accounts-ui-bootstrap-3  1.2.80  Bootstrap-styled accounts-ui with multi-language support.
iron:router                  1.0.9  Routing specifically designed for Meteor
sacha:spin                   2.3.1  Simple spinner package for Meteor
twbs:bootstrap               3.3.5  Front-end framework for responsive, mobile first projects.
underscore                   1.0.4  Collection of small helpers: _.map, _.each, ...
ejson                        1.0.7  Extended and Extensible JSON library
check                        1.0.6  Check whether a value matches a pattern
```

Basically, we add support for:

  * Forms (AutoForm, Collection2, Check)
  * Accounts (accounts-password and accounts-ui-bootstrap-3)
  * Routing (iron:router)
  * Presentation (Bootstrap, Spin)
  * Coding (underscore, ejson)

**Notes:**

  * The template removes the AutoPublish and Insecure packages. By default, applications built using this template should explicitly publish/subscribe and use Meteor Methods.

  * At the time of writing:

     * Iron:Router did not correctly require the ejson package, leading to the error `Exception in callback of async function: ReferenceError: EJSON is not defined`. If you get this error, then `meteor add ejson` will fix it.

     * AutoForm did not require the check package, leading to the error `ReferenceError: check is not defined`. If you get this error, `meteor add check` will fix it.








