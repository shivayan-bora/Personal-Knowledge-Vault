---
id: 7vfkz860dqp8mz5tbzvy7k6
title: For Serving
desc: ''
updated: 1656488775320
created: 1656488501927
---

When a model is uploaded, AI Fabric validates the uploaded `.zip` file against the requirements stated in section [[cs.ai.ml.rpa.enhanced-rpa.uipath.products.ai-center.concepts.ml-packages.structure]]. For all packages, the following three checks are performed:

- A non-empty root folder exists.
- A `requirements.txt` file exists.
- A file named `main.py` exists in the root folder which implements a class `Main`. The class is further validated to implement an `__init__` and a `predict` function.

Success or failure (along with any errors that caused validation failure) is shown in ML Logs.
