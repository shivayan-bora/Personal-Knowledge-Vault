---
id: 0jmt0yy8omfry317kvwzkaa
title: Evaluation Pipeline
desc: ''
updated: 1656670500111
created: 1656670170784
---

An Evaluation Pipeline is used to evaluate a trained machine learning model. To use this pipeline the ML Package must contain code to evaluate a model (the `evaluate()` function in train.py), this together with a Dataset (or subfolder within a Dataset) will produce a score (the return of the `evaluate()` function) and any arbitrary outputs the user would like to persist in addition to the score.

Various mandatory and optional fields and controls for a Training Pipeline:

- Evaluation Dataset: Select Dataset/Folder from which you want to import data for evaluation. All files in this Dataset/Folder will be available locally at pipeline runtime as the argument passed to the evaluate function.

- Parameters: Environment variables defined and used by Pipelines are:  
  - `artifacts_directory` (default `artifacts`): Define where artifacts folder is accessible locally for the Pipeline. Note: `artifacts` folder can be used to save any file during pipeline execution and folder will be uploaded at the end of the Pipeline run as an output of the Pipeline under directory artifacts _directory.
  - save_test_data (default ‘False’): If set to True data_directory folder will be uploaded at the end of the Pipeline run as an output of the Pipeline under directory data_directory.
