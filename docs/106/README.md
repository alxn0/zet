# __init__.py

The `__init__.py` file is used to mark directories on the disl as python regular package[^1] directory (i.e., pre-3.3 python). It is executed when the package is imported. It can be empty or contain initialization code for the package.

For `namespace package`[^2], the `__init__.py` file is not required.

## Primarly usage
It is primarly used for subpackage imports. 

For example, if you have the files:

```
package/foo/__init__.py
package/foo/bar.py
```

if `package` is on your path, your can import `bar.py` as:

```python
# Option 1
import foo.bar

# Option 2
from foo import bar
```

## Secondary usage
The `__init__.py` file can also be used to specify the contents of the package.

Here's a non exhaustive list of what it may contains:

- `__version__` : a string that specifies the version of the package.
- `__author__` : a string that specifies the author of the package.
- `__all__` : a list of module names that should be imported when `from package import *` is used.
- `import` statements to import modules that are part of the package.
- more complex initialization code such as setting up logging, reading configuration files or providin deprecation warnings.

```python
import logging
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)
logger.info('Initializing my_package')
```

```python
def function(*args, **kwargs):
    warnings.warn(
    "my_package.module2.function2 is deprecated and will be removed in the next release. "
    "Please use my_package.module1.function1 instead.",
     DeprecationWarning,
     stacklevel=2)
    return module2.function2(*args, **kwargs)
```

## references
<https://docs.python.org/3/tutorial/modules.html>
<https://stackoverflow.com/questions/448271/what-is-init-py-for>

[^1]: <https://stackoverflow.com/questions/448271/what-is-init-py-for>
[^2]: <https://peps.python.org/pep-0420/>
