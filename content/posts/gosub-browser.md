---
title: gosub-browser
date: 2023-09-28T12:14:53+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1686579809662-829e8374d0a8?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTU4NzQ0ODV8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1686579809662-829e8374d0a8?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTU4NzQ0ODV8&ixlib=rb-4.0.3
---

# [jaytaph/gosub-browser](https://github.com/jaytaph/gosub-browser)

# GoSub: Gateway to Optimized Searching and Unlimited Browsing

A feeble attempt on writing a browser and learning rust.

**Note: code in the main branch is currently not stable and might not even compile.**

```
                       _     
                      | |    
  __ _  ___  ___ _   _| |__  
 / _` |/ _ \/ __| | | | '_ \ 
| (_| | (_) \__ \ |_| | |_) |
 \__, |\___/|___/\__,_|_.__/ 
  __/ |  The Gateway to                    
 |___/   Optimized Searching and 
         Unlimited Browsing                    
```


## About

This repository is part of the GoSub browser project. Currently there is only a single component/repository (this one), 
but the idea will be that there are many other components that as a whole make up a full-fledged browser. Each of the 
components can probably function as something standalone (ie: html5 parser, css parser, etc).

In the future, this component (html5 parser) will receive through an API a stream of bytes and will output a stream of
events. The events will be consumed by the next component and so on, until we can display something in a window/user 
agent. This could very well be a text-mode browser, but the idea is to have a graphical browser.


## Status

This is a work in progress. The current status is that the parser can parse a few html5 documents, but it is far from
ready. The main goal is to be able to parse correctly all the tests in the html5lib-tests repository 
(https://github.com/html5lib/html5lib-tests). As soon as we can do this, we can try and see if we can generate a DOM 
tree and then we can start thinking about the next component (css parser).

## How to build

This project uses cargo (https://doc.rust-lang.org/cargo/). To build the project, simply run:

``` 
cargo build
```

This will create the following binaries and libs:

| File           | Type | Description                       |
|----------------|------|-----------------------------------|
| gosub-engine   | lib  | The actual html5 parser/tokenizer |
| gosub-browser  | bin  | Dummy browser (see below)         |
| parser_test    | bin  | A test suite for the parser       |
| tokenizer_test | bin  | A test suite for the tokenizer    |

### Gosub-engine

This is the actual html5 parser/tokenizer. It is a library that can be used by other projects. It is not a standalone
project. It is used by the gosub-browser project.

### Gosub-browser

This is a dummy browser. It is not a real browser, it is just a test project to see if the parser/tokenizer is working 
and tries to parse the given url on the command line:

```shell
$ gosub-browser https://www.google.com
```

### Parser_test

This is a test suite for the parser. It is not a standalone project. It is used by the gosub-engine project. You need 
to specify the directory to the html5lib-test in order to run, or it will use the default one (./html5lib-tests).

```shell
$ parser_test /path/to/html5lib-tests
```
