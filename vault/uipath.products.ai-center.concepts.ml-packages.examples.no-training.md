---
id: cfb23go44sn5hqn4ty75kau
title: Simple ready-to-serve ML model with no Training
desc: ''
updated: 1656584064401
created: 1656583922372
---

In this example, our business problem does not require model retraining, thus the ML Package must contain the serialized model (IrisClassifier.sav) that will be served.

- Initial project tree (without main.py and requirements.txt):

![Initial project tree](/assets/images/2022-06-30-15-42-36.png)

- Sample main.py to be added to the root folder:

![Sample main.py](/assets/images/2022-06-30-15-43-19.png)

- Add requirements.txt:

![requirements.txt](/assets/images/2022-06-30-15-43-35.png)

- Final folder structure:

![Final folder structure](/assets/images/2022-06-30-15-43-50.png)
