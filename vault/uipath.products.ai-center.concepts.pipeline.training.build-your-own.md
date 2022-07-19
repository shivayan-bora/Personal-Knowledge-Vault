---
id: vqg54d1ru4e9k7sxohdbkw2
title: Simplified Conceptual Analogy for Building your Own Pipelines
desc: ''
updated: 1656656111174
created: 1656655986149
---

Below is a conceptually analogous execution of a Training Pipeline on some ML Package (say version 1.0). Note this example is simplified. Its purpose is to illustrate how Datasets and ML Packages interact in a Training Pipeline. The steps below are merely conceptual and do not represent how the platform functions.

1. Copy ML Package Version 1.0 into ~/mlpackage
2. Copy the Input Dataset (or Dataset subfolder) selected from the UI to ~/mlpackage/data
3. Execute the following python code:

```python
from train import Main
m = Main()
m.train('./data)
m.save()
```

4. Persist the contents of ~/mlpackage as ML Package version 1.1. Persist artifacts if written, snapshot data if save_data is set to true.
