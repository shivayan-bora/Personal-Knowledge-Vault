---
id: vaomgx8kpe81ft09quy8esw
title: Persisting Arbitrary Data
desc: ''
updated: 1656583472526
created: 1656583381934
---

In `train.py`, any executed pipeline can persist arbitrary data (called pipeline output). Any data that is written to the directory path from environment variable `artifacts` will be persisted and can be surfaced at any point by navigating to the Pipeline Details Page. Typically, any kind of graphs, statistics of the training/evaluation jobs can be saved in `artifacts` directory and will be accessible from the UI at the end of the Pipeline Run.

![Persisting Arbitrary Data](/assets/images/2022-06-30-15-33-04.png)
