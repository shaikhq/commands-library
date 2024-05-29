# How can I import a python module from a separate project into my current project?

Add the path to the other project to `sys.path` list: 
```python
import sys
sys.path.insert(0, '/path/to/other/project/')

import module_I_want_to_import
```