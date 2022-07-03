---
id: mfeci2pg31630grsys8ha7f
title: Training Pipeline
desc: ''
updated: 1656670185059
created: 1656590522679
---

A Training Pipeline is used to train a new machine learning model. To use this pipeline the ML Package must contain code to train a model (the `train()` function in `train.py`) and code to persist a newly trained model (the `save()` function in `train.py`), these together with a Dataset (or sub-folder within a Dataset) produce a new ML Package Version.

- Input Dataset (required): Select Dataset/Folder from which you want to import data for training. All files in this Dataset/Folder will be available locally during the runtime of the pipeline and will be passed to the first argument to your `train()` function (`def train(self, data_directory)`)

- Parameters: Environment variables defined and used by Pipelines are:

  - artifacts_directory (default ‘artifacts’): Define where artifacts folder is accessible locally for the Pipeline. Note: artifacts folder can be used to save any file during pipeline execution and folder will be uploaded at the end of the Pipeline run as an output of the Pipeline under directory artifacts _directory.

  - `save_training_data` (default ‘False’): If set to True data_directory folder will be uploaded at the end of the Pipeline run as an output of the Pipeline under directory data_directory.
