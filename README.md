docopt.R
========================================================

`docopt` helps you:

- define interface for your command-line app, and
- automatically generate parser for it.

For more information see [docopt.org](http://docopt.org)

docopt.R is an implementation of [docopt](http://docopt.org) in the R language.

Install
-------

`docopt.R` is currently in heavy development and not available on CRAN.
To test it out use
```
library(devtools)
install_github("docopt.R", "edwindj")
```

It is tested against the tests defined for the reference implementation.
Currently it fails many tests. 
The tests can be run using devtools `test()` and can be found in "inst/tests"

Usage
-----

docopt uses the description of the commandline interface to parse command line
arguments.


```S
'usage: prog [-a -r -m <msg>]

options:
 -a        Add
 -r        Remote
 -m <msg>  Message' -> doc

# load the docopt library
library(docopt)

# retrieve the command line arguments
opts <- docopt(doc)
str(opts)
```

```
## List of 3
##  $ -a: logi FALSE
##  $ -r: logi FALSE
##  $ -m: NULL
```

```S

# or set them manually
opts <- docopt(doc, "-m Hello")
str(opts)
```

```
## List of 3
##  $ -a: logi FALSE
##  $ -r: logi FALSE
##  $ -m: chr "Hello"
```
