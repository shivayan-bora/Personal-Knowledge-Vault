---
id: 1x5fgbyia1zadna4inv4gv0
title: Pipeline
desc: ''
updated: 1656590534983
created: 1656589972481
---

A Pipeline is a description of an ML workflow, including all of the functions in the workflow and the order of executions of these functions. The Pipeline includes the definition of the inputs required to run the pipeline and outputs to get from this pipeline.

A Pipeline Run is an execution of a pipeline based on code provided by the user. Once completed a Pipeline Run will have associated outputs and logs.

There are three types of pipelines: Training, Evaluation, and Full Pipelines.

- At a high level, a **Training Pipeline** takes as input and ML Package and a dataset, together producing a new ML package Version.
- An **Evaluation Pipeline** takes as input a ML Package Version and a dataset, together producing a set of metrics and logs.
- A **Full Pipeline** essentially runs a data processing function, and a Training Pipeline and an Evaluation Pipeline in succession.
