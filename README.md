
![bash](./assets/bash.png)

#  Bash Library

![build]()

A  Core library for bash Bourne

## Setup

```bash
git clone https://github.com/chehabz/bash-lib && \
cd bash-lib && \ 
export BASH__PATH=~/develop/lib-bash && \
source ${BASH__PATH}/core/init.sh
```

## Importing a Module

```bash
import console # this will load up the console module
```

### Using the Module


Once the module is loaded into the terminal you can start using the `methods`

```bash
console.log Hello world!

#output
03/03/2021 11:25:33 - Mohammads-MacBook-Pro.local - bash - [LOG]: Hello world!
```

another example in one shot

```bash
import http && \
http.get http://stash.compciv.org/congress-twitter/json/joni-ernst.json
```

You can simple de-register the module using the `unset` command

```bash
unset console;
```

### Available Modules

You can query the available modules using

```bash
engine.modules
```


## Configuration


| Variable | Description |
|:--- | :--- |
| `BASH__PATH`| This is the root location of the library |
| `BASH__VERBOSE`| You can set it to one of the log levels `TRACE`, `DEBUG`, `INFO`, `WARN` or `ERROR` to change the verbosity of the logs. `TRACE` is the most verbose and it is the default  |


## Naming Conventions


| Convention | Description |
|:--- | :--- |
|Class level variables in modules| Variables in modules will be named as such `BASHLIB__MODULENAME__VARIABLE__NAME` |
|Environment Scope| Variables with environment scope will be as `VARIABLE__NAME` |


## Debugging

At the end of the day this is pure `bash`. To turn on debugging simple use

```bash
set -x
```

Once done you can simply switch it off using the following command.

```bash
set +x
```

Check the `BASH` environment variables that are loaded

```bash
env | sed "s/=.*//" | grep BASH
# example output
BASH__PATH
BASH__VERBOSE
```

## Unit Testing

`Lib Bash` uses [shellspec](https://github.com/shellspec/shellspec) to perform unit tests.
all the test cases are stored under the `spec` directory. to run the tests simply use `make`

## Change log
see here for the complete [chanelog](CHANGELOG.md)