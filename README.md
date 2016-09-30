# Introduction

Building a REST API using Swagger

## Windows Users

This tutorial expects a Unix-like system, however where possible alternatives have been identified for Windows-based systems.  The Windows paths are less tested than the Unix-like paths.

# Prerequisites

* Nodejs (installed with nvm)
* swagger-node project
* Docker
* Basic knowledge of `git`

[item]: # (slide)
# Objectives of Project

* Learn about how to quickly build a REST API
* Package the REST API as a container
* Understand environment variables

[item]: # (/slide)

# Step 0: Installing Prerequisites

We're going to use the [NodeJS](https://nodejs.org) environment to build our project.  However, we're not going to build the application from scratch, but instead use a few frameworks to speed up the process.  Frameworks are common in application development to remove a lot of the boilerplate code that you might write over-and-over again.  In particular, this project will leverage the [swagger-node](https://github.com/swagger-api/swagger-node) project, which itself uses a web application framework called [expressjs](https://expressjs.com).

* Install NodeJS using [nvm (node version manager)](https://github.com/creationix/nvm).  Windows users can use: [nvm-windows](https://github.com/coreybutler/nvm-windows)
* Install [swagger-node](https://github.com/swagger-api/swagger-node)
* Install [Docker for Mac](https://docs.docker.com/engine/installation/mac/) or [Docker for Windows](https://docs.docker.com/engine/installation/windows/)

[item]: # (slide)
# Step 1: Create swagger-node project
[item]: # (/slide)

* `$ npm install -g swagger`: Installs the swagger framework globally
* `$ swagger project create rest-api-swagger`: Scaffolds the entire project in a newly created `rest-api-swagger` directory
* `$ cd rest-api-swagger`
* `$ git init`: Initialize the git repo for this project

[item]: # (slide)
# Step 2: Exploring the project layout
[item]: # (/slide)

Swagger-node will create a template project for you to fill in the gaps.  Observe that there is an `api` directory, that contains folders for `controllers`, `helpers`, `mocks`, `swagger`, and others.

Focusing our attention on `controllers` and `swagger`:

[item]: # (slide)

* `controllers`: ExpressJS is a Model-View-Controller web framework.  The Controller is basically the business logic for the app, where the View is what you ultimately consume as a web page, and Model defines the objects that would be referenced in your View and Controller.  In short, the Controller is somewhat like the glue between the Model and View.

* `swagger`: This directory holds the `swagger.yaml` file, which provides the definition for your REST API.  We will manipulate this file quite a bit using the Swagger Editor.

[item]: # (/slide)

```
├── README.md
├── api
│   ├── controllers
│   │   ├── README.md
│   │   └── hello_world.js
│   ├── helpers
│   │   └── README.md
│   ├── mocks
│   │   └── README.md
│   └── swagger
│       └── swagger.yaml
├── app.js
├── config
│   ├── README.md
│   └── default.yaml
├── package.json
└── test
    └── api
        ├── controllers
        │   ├── README.md
        │   └── hello_world.js
        └── helpers
            └── README.md
```

[item]: # (slide)
# Step 3: Run the project


Swagger-node provides convenient CLI commands to help you run the project, edit the Swagger file using swagger editor, and test your API.

```
    create [options] [name]              Create a folder containing a Swagger project
    start [options] [directory]          Start the project in this or the specified directory
    verify [options] [directory]         Verify that the project is correct (swagger, config, etc)
    edit [options] [directory]           open Swagger editor for this project or the specified project directory
    open [directory]                     open browser as client to the project
    test [options] [directory_or_file]   Run project tests
    generate-test [options] [directory]  Generate the test template
```

[item]: # (/slide)

## Exercise

* Open another terminal windows or tab
* In the new terminal, change to the project directory
* Execute the command `swagger project start`
* In the first terminal window, execute the command `swagger project edit`

In the window where you entered the command `swagger project start`, you should see console output:

```
Starting: /Users/<username>/src/rest-api-swagger/app.js...
  project started here: http://localhost:10010/
  project will restart on changes.
  to restart at any time, enter `rs`
try this:
curl http://127.0.0.1:10010/hello?name=Scott

```

In the window where you entered the command `swagger project edit`, you should see this console output, and your browser should have loaded the editor.

```
Starting Swagger Editor.
Opening browser to: http://127.0.0.1:50391/#/edit
Do not terminate this process or close this window until finished editing.
```

![Editor](docs/editor.png)

[item]: # (slide)
# Step 4: Understand the project and development process
[item]: # (/slide)

[item]: # (slide)
![](https://github.com/swagger-api/swagger-node/raw/master/docs/images/overview2.png)
(Source: Swagger-node project)
[item]: # (/slide)

# Step 5: Creating a new API

# Step 6: Wiring up the controller

# Step 7: Deploying into Docker

# Step 8: Bonus: Docker Makefile



# Links to Explore

* https://swaggerhub.com