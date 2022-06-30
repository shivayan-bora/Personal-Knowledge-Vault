---
id: r5dc3kc7go4qx6v6vyfcr51
title: Simple ready-to-serve Model with Training Enabled
desc: ''
updated: 1656586997037
created: 1656586727751
---

In this example, our business problem requires that our model be retrained. Building on the ML Package described above we may have the following:

Initial project tree (serving only ML Package):

![Initial project tree](/assets/images/trainingEnabled1.PNG.png)

Sample train.py to be added to the root folder:

![Sample train.py](/assets/images/trainingEnabled2.PNG.png)

Edit requirements.txt if needed.

![requirements.txt](/assets/images/trainingEnabled3.PNG.png)

Final folder (ML Package) structure:

![Final Folder](/assets/images/iris%20tree.PNG.png)

**Note:** Now this model can be first served and, as new data points come into the system via Robot or Human-in-the-Loop, Training and Evaluation Pipelines can be created leveraging train.py.
