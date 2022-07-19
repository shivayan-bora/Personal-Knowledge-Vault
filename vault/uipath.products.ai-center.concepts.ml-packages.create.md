---
id: hd4k5gprr6fqqbpbvse717f
title: Create
desc: ''
updated: 1656484852875
created: 1656484191176
---

The Create New Package page has a number of optional and required fields.

- Package Name (required):  Name of your package in AI Fabric app.
- Upload Package (required): Zipped file representing the ML Package and containing all necessary code as described above.
- Package Description: Provide clear description of the model. This description will be seen while deploying a new skill based on this model and on ML Packages page.
- Input Type (required): Select type of input the package is going to work with among json, file or files.
- Input Description: Enter clear description of the input expected by the model. Note that this description will be visible to RPA Developers using the ML Skill Activity in UiPath Studio. As a good practice, it is recommended to show an example of the input format to facilitate communication between Data Scientists and RPA Developers.
- Output Description: Enter clear description of the output returned by the model. Note that this description will be visible to RPA Developers using the ML Skill Activity in UiPath Studio. As a good practice, it is recommended to show an example of the output format to facilitate communication between Data Scientists and RPA Developers.
- Language (required): Select development language of the model.
- Enable Training (required default No): Indicates if this ML Package can be used in any Pipeline. If yes, the validation step will check if train.py is implemented in the package and validation will fail otherwise.

- Custom Package Version #todo
- Recommend GPU #todo
