---
id: 6xpfphc9nxmeopv7htan08j
title: Serving Component
desc: ''
updated: 1656483593334
created: 1656483484107
---

An ML Package must at minimum provide the following:

- A folder containing a main.py file at root of the folder
- In this file, a class called Main that implements at least two functions:
  - `_init_(self)`: takes no argument and loads your model and/or data for the model (e.g. word embeddings).
  - `predict(self, input)`: a function that will be called at a model serving time.
- A file named `requirements.txt` with dependencies needed to run the model

This component of an ML Package can be thought of as the model at inference time. That is, at serving time, a container image will be created using the provided `requirements.txt` and the `predict` function will be used as the endpoint to the model.
