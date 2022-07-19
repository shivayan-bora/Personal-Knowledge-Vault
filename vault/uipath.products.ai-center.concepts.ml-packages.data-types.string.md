---
id: 5pt86zy1c5rd5q25b1tjw6y
title: Handling String Data
desc: ''
updated: 1656583141928
created: 1656583102489
---

Any data that can be serialized can be used with an ML Package. If used within an RPA workflow, the data can be serialized by the Robot (perhaps using a custom Activity) and sent as a string. If used externally from UiPath, the data can be formatted and serialized by the client. In both of these cases, the ML Package uploader would have selected json as the ML Package’s input type.

The deserialization of data is done in the predict function. Below are a handful of examples for deserializing data in Python:

![Deserializing string data](/assets/images/2022-06-30-15-28-45.png)
