## where to start?

You can download [Postman](https://www.postman.com/downloads/) to see how the tests are structured. Also, is where you can maintain the tests and run them manually if you wish.
Just import these files:
 - globals.postman_globals.json
 - API Automation.postman_collection.json
 - postman_environment.json

Now to run Newman, ensure that you have Node.js >= v10. [Install Node.js via package manager](https://nodejs.org/en/download/package-manager/).

Newman is a powerful command-line collection runner for Postman. It allows you to run and test a Postman collection directly from the command-line. It is built with extensibility in mind so that you can easily integrate it with your continuous integration servers and build systems.
Newman maintains feature parity with Postman and allows you to run collections the way they are executed inside the collection runner in Postman.

### Installation
The easiest way to install Newman is using NPM. If you already have Node.js installed, go foward!

```console
$ npm install -g newman
```
This installs Newman globally on your system allowing you to run it from anywhere. If you want to install it locally, Just remove the `-g` flag.

### Using Newman CLI
The `newman run` command allows you to specify a collection to be run. You can easily export your Postman
Collection as a json file from the Postman App and run it using Newman.

```console
$ newman run examples/sample-collection.json
```
In the case of this project, it is necessary to specify not only the collection, but also which environment and the globals file, which contains the libs of assertions and other functions used in the tests.

```console
$ newman run ./tests/Invitation.postman_collection.json -e ./config/Inv-OHID-Non-RP89372.postman_environment.json -r htmlextra
```

### HTML Reporter
An external reporter, maintained by Postman, which can be installed via npm install -g newman-reporter-html. This reporter was part of the Newman project but was separated out into its own project in V4.

The complete installation and usage guide is available at newman-reporter-html. Once the HTML reporter is installed you can provide --reporters html as a CLI option.

### And that's all!!
