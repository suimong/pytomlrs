PyTOML.rs
==================

Python object (de)serializer to/from TOML using Rust.

## Development

ref: https://zenn.dev/yyu/articles/3b87c9499fddde



```shell
poetry run maturin develop
poetry run maturin build
```

## Usage Example

```python
import pytomlrs

python_value = {
    'a': {
        'b': 1,
        'c': True
    },
    'd': {
        'e': [1.2, 'foobar']
    }
}
pytomlrs.to_toml(python_value)
""" ==>
[a]
b = 1
c = true

[d]
e = [1.2, "foobar"]
"""
```