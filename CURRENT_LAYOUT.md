# Current Layout

build system: poetry
python layout: src/<package name>
rust layout: src/<lib.rs etc.>
Cargo.toml workspace setting: false

# Build status on various commands

- `maturin build`: ok with warning: "`build-backend` in pyproject.toml is not set to `maturin`, packaging tools such as pip will not use maturin to build this project."
- `poetry run maturin build`: same as `maturin build`
- `poetry build`: command finished without error, but the wheel does not contain the rust compiled `.so` file so probably won't work.