Notes on Development
====================

These are some general, and personal, observations about developing software.

Always to set up your development environment with the aim to find problems as early as possible in its development.

Testing
-------

Do it! Automate it (or it won't get done)!

Make it a condition that new code must have an accompanying test and must pass all existing tests (or have a good justification for modifying/removing a failing test).



Developing JavaScript specifically
----------------------------------

I am fairly new to JavaScript development but...

Use a Type System
~~~~~~~~~~~~~~~~~

JavaScript is `dynamically typed <https://en.wikipedia.org/wiki/Dynamic_programming_language>`_, which makes it easy to write bad code. (Why dynamic typing? The theory is that it allows more adaptable code and that code is more concise---no type enforcement overhead.)

Whether you use JSDocs to type your code or TypeScript (or A.N.Other system), USE TYPES in your code. They allow static type checking and *will* help find errors in your code much earlier. Without using a type system we cannot perform static analysis on our code and this opens us up to a whole class of common bugs (e.g. passing a string to a function that expects an integer).



Build System
------------

Automate the build of your module.

This makes life easier in the long run (no having to remember weird incantations to get it working), it is also important that we check that our version control system contains *all* sources for our module and this is easiest checked using automated build and testing.



Automate Deployment
-------------------

In the context of Foundry module development this means automating making our module available to users.

This means creating a new ``zip`` file and ``manifest.json`` and making these available in a way that users see our update. It also means automating updates to any sites that promote our module (wherever possible) and updating our module's documentation.



Provide Good Documentation
--------------------------

Both user and developer documentation is important. Write them as a part of the product, not an afterthought.

User documentation
~~~~~~~~~~~~~~~~~~

This should be provided alongside the module. Possibly within the module but certainly as an easily accessible web resource. Also, user documentation should be maintained for each release of your module.

Developer documentation
~~~~~~~~~~~~~~~~~~~~~~~

By and large your module code should be clear enough to need only light documentation. That said, external documentation should be provided for:

* High level architecture. If your module is large or complex enough to warrant it.
* API. If you provide an API it should be documented. This document should be generated automatically as part of the build and should be derived from the code to which is applies.
