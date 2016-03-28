## How to use python to verify that a folder exists and create it if necessary

To verify that a particular directory exists and then create it if not:
```python
import os

if not (os.path.exists(folder_path) and os.path.isdir(config.manifest_file_dir)):
    os.makedirs(config.manifest_file_dir)
```
Notice the conditional:
1. checks for existence
2. confirms that the path is a directory.
### References:
http://stackoverflow.com/questions/8933237/how-to-find-if-directory-exists-in-python
http://stackoverflow.com/questions/1274405/how-to-create-new-folder
