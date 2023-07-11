# datahooks
An example of useful precommit hooks, with a focus on data-related code

# Getting started

## Setting up
First of all - clone this repo!
next you will want to install the pre-commit package
`pip install pre-commit`

Then install the hooks (this only needs to be done when cloning the git repo to a new machine)
`pre-commit install`

## Running the hooks
The purpose of the hooks is to run automatically before a commit (ie when you do `git commit`).
So you can edit or add files, then attempt to commit them to run the hooks.
alternatively you can run `pre-commit run --all-files` to run the hooks against all files in the repo

## Bypassing hooks
You can, if you really need to, bypass the hooks for a commit like this:
`git commit -m "This code does not pass checks" --no-verify`
Remember though that you are just kicking the problem down the road for someone else to fix.

# Chetwood data hooks

## SQLFluff
SQLFluff can lint SQL and provide feedback.
It allows for exclusion rules, for example rule L011 covers implicit/explicit aliasing of tables. The rules we use will evolve with our use of the tool.
SQLFluff can also fix some problems it finds using `sqlfluff fix`, though we need to be careful with the actions that it takes.

## black
Black is a Python code formatter.
PEP 8 is widely adopted as the standard for python formatting, Black formatting is a subset of PEP 8.
Black is uncompromising, we will effectively cede control of formatting to black.

## blacken docs
Run Black on Python code blocks in documentation files.
https://github.com/adamchainz/blacken-docs

## iSort
Sorts imports in python files alphabetically.
It's (mostly) compatible with Black
Officially supports pre-commit
https://pycqa.github.io/isort/

## myPy
Type checker. Looks for incorrect types being passed.

## pyUpgrade
A tool (and pre-commit hook) to automatically upgrade syntax for newer versions of the language.
https://github.com/asottile/pyupgrade

## A whole load of github hosted hooks
json checkers, yaml checkers, line endings, whitespace, credentials private keys and loads of other things.
