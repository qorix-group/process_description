# process_description

S-CORE process description

## Overview

The S-CORE process model aims to establish organization rules for developing open source software in the automotive industry, which can be used in safety and security context.

## Features

The process model provide processes, which conform to state-of the art standards

- ASPICE PAM 4.0
- ISO 26262
- ISO/SAE 21434
- ISO PAS 8926

## Building process documentation

#### Run a documentation build:

```bash
bazel run //:docs
```

#### Access your documentation at:

- `_build/` for incremental
- `bazel-bin/bazel-bin/docs/_build/html`

#### Getting IDE support

Create the virtual environment via `bazel run //:ide_support`.\
If your IDE does not automatically ask you to activate the newly created environment you can activate it.

- In VSCode via `ctrl+p` => `Select Python Interpreter` then select `.venv_docs/bin/python` OR
- Click in the top level search bar, open `Show and Run Commands` => `Select Python Interpreter` then select `.venv_docs/bin/python`
- In the terminal via `source .venv_docs/bin/activate`

Now run the live_preview commands

```bash
bazel run //:live_preview
```

#### Format your documentation with:

```bash
bazel test //:format.test
bazel run //:format.fix
```

Now server should be available with a preview on the link that is given (normally 127.0.0.1:8000) and the documentation can be previewed there.

#### Find & fix missing copyright

```bash
bazel test //:copyright.test
bazel run //:copyright.fix
```

#### Explore more functions with
bazel query //...
