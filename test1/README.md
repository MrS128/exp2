# \<simple-clock\>

A simple test element

## Install the Polymer-CLI

First, make sure you have the polymer-dev container running
```
$ docker run --name polymer-dev -it -d -p 8080:8080 -v /Users/Dmitri/projects/exp2/test1:/home/polymer/test1 dms/polymer-dev:latest
```


## Viewing Your Element

To run polymer server in polymer-dev containr run:

```
$ polymer serve --hostname 0.0.0.0 --port 8080
```

## Running Tests

```
$ polymer test
```

Your application is already set up to be tested via [web-component-tester](https://github.com/Polymer/web-component-tester). Run `polymer test` to run your application's test suite locally.
