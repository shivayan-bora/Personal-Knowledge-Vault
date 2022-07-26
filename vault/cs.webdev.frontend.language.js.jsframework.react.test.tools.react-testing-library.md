---
id: oq3rav3t80a0b8py80pwfsv
title: React Testing Library
desc: ''
updated: 1658775060083
created: 1658771977136
---

React Testing Library is built on top of [DOM Testing Library](https://testing-library.com/docs/dom-testing-library/intro/) which in turn is a part of the [`@testing-library`](https://testing-library.com/docs/) family of packages.

## The Problem

As per it's guiding principle, you would want to write maintainable tests that give you confidence that your componenets are working for your users.

Therefore, you would want your tests to avoid including implementation details, so, refactors of your components i.e. changes to implementation but not to the functionality, don't break the tests and slow you down.

## The Solution

The core library i.e. DOM Testing library, is a light-weight solution for testing webpages by querying and interacting with the DOM nodes (whether simultaed  with JSDOM/[[cs.webdev.frontend.language.js.testing.tools.jest]] or in the browser).

It provides utilities for interacting/querying the DOM nodes in a way that's similar to how user finds elements on the web page. In this way, the framework ensures confidence that our application will work when a real user interacts with it as our tests will mimic the way a user interacts with our application.

## What this library is not?

1. A test runner or framework.
2. Specific to a testing framework.

DOM Testing Library works with any environment that provides DOM APIs, such as Jest, Mocha + JSDOM, or a real browser.

## What you should avoid with Testing Library?

Testing Library encourages you to avoid testing implementation details like the internals of a component you're testing (though it's still possible).

The Guiding Principles of this library emphasize a focus on tests that closely resemble how our web pages are interacted by the users.

You may want to avoid the following implementation details:

1. Internal state of a component
2. Internal methods of a component
3. Lifecycle methods of a component
4. Child components
