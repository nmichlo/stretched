# Stretched
Python bindings for Stretch - A high performance flexbox implementation written in rust.

⚠️ PLEASE NOTE THIS PROJECT IS A WORK IN PROGRESS ⚠️


## Install

```bash
pip3 install stretched
```

Note: Only MacOS versions for python 3.6 and 3.7 have been compiled. Linux and Windows binaries are on the roadmap.


## Quickstart


```python
from stretched import *

# Flexbox container/node
node = Node()

# Flexbox container/node child
child = Node()
node.add_child(child)
assert len(node) == 1

# Remove child
node.remove_child(child)
assert len(node) == 0

# Flexbox style object
style = Style()
child = node.add_child(Node(style))
assert len(node) == 1

# Compute/Recompute layout for a container of 1920x1080 units
layout = node.compute_layout(Size(1920, 1080))
assert layout.width == 1920
assert layout.height == 1080

# Size measuring callback for compute layout:
node.measure = lambda size: Size(1920, 1080)
layout = node.compute_layout(Size(None, None)) # unbounded
assert layout.width == 1920
assert layout.height == 1080
```

## Overview

These bindings were translated from the origional swift bindings for Stretch .

- See the tests in ./tests/test.py for examples on how to use the bindings.



Bindings are generated using pyo3 and pyo3-pack.

- Please see the relevant documentation for more information on how to build the bindings.



## Basic Build Instructions

Python 3.5 to 3.7 should be supported.

- You will need pyenv and pyenv virtualenv setup, activate your virtual environment.
- install the requirements `pip install -r ./requirements_dev.txt`
- compile and install the development version directly into your environment with `pyo3-pack develop`
- compile a release version with `pyo3-pack build`



