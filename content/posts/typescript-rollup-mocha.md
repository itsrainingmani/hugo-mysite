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

Recently I embarked on reading Peter Norvig's excellent post about [Solving Every Sudoku Puzzle](http://norvig.com/sudoku.html) and I was inspired to [port](https://github.com/itsrainingmani/yass) the code to TypeScript. While working on this project, I struggled with the sheer amount of configuration options available with TypeScript. (Don't even get me started on bundling)

Eventually I found some great resources on how to properly setup the project and I wanted to share what I learned with the next person who might run into these issues.

## Initial Setup

It all starts with *npm*. We're going to create a test directory, (let's call it ts-app) and initialize an *npm* project in this directory.
I'm going to assume that you're familiar with *npm* and how to use it.

```shell
mkdir ts-app && cd ts-app && npm init -y
```

The `-y` option to `npm init` allows you to bypass the initial npm options and gets you a barebones project.
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

* typescript:
* ts-node:
* rollup:
* rollup-plugin-typescript2:
* mocha:
* @types/mocha:
* @types/node:
