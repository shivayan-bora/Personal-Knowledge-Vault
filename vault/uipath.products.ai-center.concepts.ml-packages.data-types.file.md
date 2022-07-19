---
id: z0tdv1i0uswzqunyhu8ut90
title: Handling File Data
desc: ''
updated: 1656583305289
created: 1656583150374
---

Selecting input type file at ML Package upload time is a convenience that the uploader is giving to the RPA developer using this model through UiPath's RPA platform. Within the RPA workflow, the input to the ML Skill Activity is just the path to the file. The activity reads the file, serializes it, and sends the file bytes to the predict function. The deserialization of data is again done in the predict function, the general case is just reading the bytes directly into a file-like object as below:

![Serialization of file](/assets/images/2022-06-30-15-29-48.png)

Reading the serialized bytes as above is equivalent to opening a file with the read binary flag turned on. To test the model locally, read a file as a binary file. The following shows an example reading an image file and testing locally:

![Reading the serialized bytes](/assets/images/2022-06-30-15-30-13.png)

The following shows an example reading a csv file and using a pandas dataframe in the predict function:

![CSV Example](/assets/images/2022-06-30-15-31-17.png)
