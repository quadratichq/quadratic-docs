---
description: Using and installing Python packages.
---

# Packages

## Default Packages

Many libraries are included by default, here are some examples:

* Pandas ([https://pandas.pydata.org/](https://pandas.pydata.org/))
* NumPy ([https://numpy.org/](https://numpy.org/))
* SciPy ([https://scipy.org/](https://scipy.org/))

Default packages can be imported like any other native Python package.

```python
import pandas as pd
import numpy as np 
import scipy
```

[Micropip](https://micropip.pyodide.org/en/stable/project/api.html) can be used to install additional Python packages that aren't automatically supported (and their dependencies).

```python
import micropip

# `await` is necessary to wait until the package is available
await micropip.install("faker")

# Import installed package
from faker import Faker

# Use the package!
fake = Faker()
fake.name()
```

This only works for packages that are either pure Python or for packages with C extensions that are built in Pyodide. If a pure Python package is not found in the Pyodide repository, it will be loaded from PyPI. [Learn more about how packages work in Pyodide](https://pyodide.org/en/stable/usage/loading-packages.html#loading-packages).
