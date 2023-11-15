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

## Naming format of the dev branches

format: `dev-{BUILD_SYSTEM}-{PY_LAYOUT}-{RUST_LAYOUT}-{EXTRAS}`
where:
```rust
enum BUILD_SYSTEM:
    poetry
    maturin

enum PY_LAYOUT:
    root_pkgname
    src_pkgname
    src_deep_pkgname

enum RUST_LAYOUT:
    conventional  // ROOT_DIR/src/{lib.rs etc.}, do not specify workspace in cargo.toml
    workspace_src_bare  // ROOT_DIR/src/{lib.rs etc.}, specify workspace in ROOT_DIR/cargo.toml
    workspace_src_shallow  // ROOT_DIR/crates/src+Cargo.toml/{lib.rs etc.}, specify workspace in ROOT_DIR/cargo.toml
    workspace_src_deep  // ROOT_DIR/src/rust+Cargo.toml/src/{lib.rs}
```


e.g.:

- `dev-poetry-`

