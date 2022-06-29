---
id: mp790kg06jtxc9yyvfa3ecq
title: For Training
desc: ''
updated: 1656488767982
created: 1656488697767
---

When a model is uploaded and it is indicated as retrainable as in section Uploading a Retrainable Package, AI Fabric validates the uploaded .zip file against the requirements stated in section Structure of an ML Package: Training and Evaluation Component.  For these packages the following two checks are performed:

- A non-empty root folder exists.
- A file named train.py exists in the root folder which implements a class Main. The class is further validated to implement an __init__ function and the following functions (train, evaluate, save).

Success or failure (along with any errors that caused validation failure) is shown in ML Logs.
