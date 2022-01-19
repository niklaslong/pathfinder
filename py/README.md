# py

This directory will host the code to call contracts using `cairo-lang` python package, and other utilities:

- src/generate_test_storage_tree.py -- generates the patricia tree for a single contract from stdin
- src/generate_test_global_tree.py -- generates the main patricia tree from stdin

See files for usage instructions.

## Development

Setup development environment by creating a virtual environment and entering it:

```bash
$ python3 -m venv .venv
$ source .venv/bin/activate
```

Then install tools:

```bash
$ PIP_REQUIRE_VIRTUALENV=true pip install --upgrade pip
```

Then install development tools:

```bash
$ PIP_REQUIRE_VIRTUALENV=true pip install -r requirements-dev.txt
```

Finally install the only real dependency, which cannot currently be managed by lock files:

```bash
$ PIP_REQUIRE_VIRTUALENV=true pip install cairo-lang==0.6.2
```

## Testing

Inside the virtual environment, in the same directory as this README, after installing all of the dependencies:

```
$ pytest
```

At the moment pytest ignores all warnings, which are from dependencies.

## Formatting

Running this will modify your files, regardless if they staged in git or not.

Inside the virtual environment, similar to testing:

```
$ black src/
```

## Linting

Many lints consider formatting, so format before linting.

Inside the virtual environment, similar to testing:

```
$ flake8 src/
```