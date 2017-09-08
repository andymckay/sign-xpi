==========
 sign-xpi
==========

An AWS Lambda (and a supplementary CLI utility) to sign XPI files.

The packaging of this repository is meant to be reminiscent of the
amo2kinto-lambdo repo.

Use this script to generate a zip for Amazon Lambda::

  make clean virtualenv zip

You must run this script on a linux x86_64 arch, the same as Amazon Lambda.

This will package a lambda with a handler at ``aws_lambda.sign_xpi.handle``.

Using the docker file
=====================

If you have docker installed then you can do the following::

  docker build . -t sign-xpi
  docker run -it sign-xpi bash

Development
===========

Another virtualenv is created for doing development, so that we don't
accidentally include dev tools in the lambda. To build it::

  make virtualenv-dev

Run the tests using::

  . .venv-dev/bin/activate
  make run-autograph &
  py.test
