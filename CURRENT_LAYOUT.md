 # Current Layout

 build system: poetry
 python layout: src/py/<package name> i.e. "pytomlrs"
 rust layout: src/rust/src/<lib.rs etc.>
 Cargo.toml workspace setting: true

 # Build status on various commands

 - `maturin build`: ok with warning: "`build-backend` in pyproject.toml is not set to `maturin`, packaging tools such as pip will not use maturin to build this project."
 - `poetry run maturin build`: same as `maturin build`
 - `poetry build`: command finished without error, but the wheel does not contain the rust compiled `.so` file so probably won't work.

# Notes

- the root `Cargo.toml` must have a `[package]` in order for `maturin` to work. In other words, the `virtual manifest` type of workspace does not work with `maturin`.

- the `name` field in the `[lib]` table of `Cargo.toml` should match the `name` field in the `package` table of `pyproject.toml`