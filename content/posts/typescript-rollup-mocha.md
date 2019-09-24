---
title: "Setting up a TypeScript project with Rollup & Mocha"
date: 2019-09-18T21:22:33-04:00
draft: true
tags: ["blog", "typescript"]
---

## You're here. What now?

Welcome, Traveler of the Interwebs. You seek knowledge and erudition, but will you find it here? That remains to be seen.

If you want to learn how to setup a TypeScript library, bundle it with Rollup and test it with Mocha then this is the tutorial for you.

## Motivation

Recently I embarked on reading Peter Norvig's excellent post about [Solving Every Sudoku Puzzle](http://norvig.com/sudoku.html) and I was inspired to [port](https://github.com/itsrainingmani/yass) the code to TypeScript. While working on this project, I struggled setting up TypeScript configuration, making sure that I could test my code properly with Mocha, and bundling the code into CommonJS & ES Module compliant JavaScript.

Eventually, after combing through stackoverflow and a variety of blogs, I found some great resources on how to properly setup the project and I wanted to share what I learned with the next person who might run into these issues.

## Initial Setup

It all starts with *npm*. We're going to create a test directory, (let's call it ts-app) and initialize an *npm* project in this directory.
I'm going to assume that you're familiar with *npm* and how to use it.

```shell
mkdir ts-app && cd ts-app && npm init -y
```

The `-y` option to `npm init` allows you to bypass the initial npm options and sets you up with a barebones project.
The ts-app folder now has a `package.json` file.

```shell
$ ls -h
package.json
```

## TypeScript. How do we get started

To get started, we're going to install some npm packages:

```shell
npm i -D typescript ts-node rollup rollup-plugin-typescript2 mocha @types/mocha @types/node
```

That's a lot of packages. Let's break it down:

* typescript: Typescript is a language for application-scale JavaScript. TypeScript adds optional types to JavaScript and compiles to readable, standards-based JavaScript.
* ts-node: TypeScript execution environment and REPL for node.js with source-map support.
* rollup: Rollup is a module bundler for JavaScript which compiles small pieces of code into something larger and more complex, such as a library or application.
* rollup-plugin-typescript2: Rollup plugin for typescript with compiler errors and syntactic and semantic diagnostic messages.
* mocha: Mocha is a feature-rich JavaScript test framework running on Node.js and in the browser, making asynchronous testing simple and fun.
* @types/mocha: Type definitions for Mocha.
* @types/node: Type definitions for Node.

The `-D` flag for npm installs these packages as devDependencies since we are only going to be using them for development.

Now the devDependencies part of our `package.json` should be looking like this:

```json
"devDependencies": {
    "@types/mocha": "^5.2.7",
    "@types/node": "^12.7.5",
    "mocha": "^6.2.0",
    "rollup": "^1.21.4",
    "rollup-plugin-typescript2": "^0.24.2",
    "ts-node": "^8.4.1",
    "typescript": "^3.6.3"
  }
```
