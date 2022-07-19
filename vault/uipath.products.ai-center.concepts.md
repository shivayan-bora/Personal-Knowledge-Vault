---
id: eooci4l1008c4d1n67hqutu
title: Concepts
desc: ''
updated: 1656420716991
created: 1656419958265
---

- Project: A project groups Datasets, ML Packages, Pipelines, ML Logs and ML Skills related to the same business problem.

- Dataset: A folder of storage (containing arbitrary files and sub-folders).

- Pipeline: A Pipeline is a description of an ML workflow, including all of the functions in the workflow and the order of executions of these functions. The Pipeline includes the definition of the inputs required to run the pipeline and outputs to get from this pipeline.
  - Pipeline Run: It is an execution of a pipeline based on code provided by the user. This code is where the functions called in the pipeline are actually implemented. Types:
    - Training: Training Pipeline takes as input an ML Package and a dataset together producing a new ML Package Version.
    - Evaluation: Evaluation Pipeline takes as input an ML Package Version and a dataset and produces a set of metrics and logs.
    - Full: A Full Pipeline essentially runs a Training Pipeline and immediately after, an Evaluation Pipeline.

- ML Skills: An ML Skill is a live deployment of an ML Package Version, it can be used in an RPA workflow simply by dragging and dropping an ML Skill Activity in UiPath Studio.

- ML Logs: ML Logs are a consolidated view of all events related to a Project.
