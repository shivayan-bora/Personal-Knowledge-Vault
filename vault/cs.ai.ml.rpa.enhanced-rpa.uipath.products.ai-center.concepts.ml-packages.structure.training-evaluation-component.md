---
id: 9678kk7ip8i7ong3qs51xwc
title: Training and Evaluation Component
desc: ''
updated: 1656512437644
created: 1656512136763
---

In addition to inference, an ML package can optionally be used to train a machine learning model. This is done by providing the following:

- In the same root folder with `main.py`, provide a file named `train.py`
- In this file, provide a class called Main that implements at least four functions. All of the below functions, but `_init_`, are optional but will limit the type of Pipeline that can be run with the corresponding ML Package.
  - `_init_(self)`: takes no argument and loads your model and/or data for the model (e.g. word embeddings)
  - `train(self, training_directory)`: a function that takes as input a directory with arbitrarily structured data regroup in one root folder, should not return a value. This function will be called whenever a Training Pipeline is executed.
  - `evaluate(self, evaluation_directory)`: a function that takes as input a directory with arbitrarily structured data, should return a number. This function will be called whenever an Evaluation Pipeline is executed.
  - `save(self)`: takes no argument, will be called after every call to train to persist your model.
  - `process_data(self, input_directory)`: takes an input_directory with arbitrarily structured. This function will only called whenever a **Full Pipeline** is executed. In the execution of a **Full Pipeline** this function can perform arbitrary data transforms and can split data. Specifically, any data saved to the path pointed to by the environment variable `training_data_directory` will be the input to the train function, and any data saved to the path pointed to by the environment variable `evaluation_data_directory` will be the input to the evaluation function above.
