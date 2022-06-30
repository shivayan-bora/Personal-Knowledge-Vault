---
id: c82ihk8z4fi3ejlwwtb189v
title: Data Types
desc: ''
updated: 1656582664735
created: 1656582572817
---

To make AI Fabric easier to use within an RPA workflow, the ML Package can be denoted to have one of three input types:

- String: a sequence of characters.
- File: This informs the AI Fabric RPA Workflow Activity (ML Skill Activity) making calls to this model to expect a path to a file. Specifically, the ML Skill Activity will read the file from the file system and send the file to the predict function as a serialized byte string. In effect, this is a convenience that the model uploader is giving an RPA developer. That is, the RPA developer an now just pass a path to a file instead of having to read and serialize the file in the RPA workflow itself.
- Files: this informs AI Fabric that the ML Skill Activity making calls to this model expects a list of file paths. just as in the former case, the UiPath Activity will read each file, serialize each file, and send a list of byte strings to the predict function.

These high-level concepts are captured at ML Package upload time.
