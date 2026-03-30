# Contributing

First off, thank you for considering contributing to this project! 

## Local Development Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/vcoderun/vcode
   cd vcode
   ```

2. **Install dependencies using `uv`:**
   ```bash
   uv sync --extra dev --extra docs
   ```

   `pip` fallback:
   ```bash
   pip install -e ".[dev,docs]"
   ```

3. **Install pre-commit hooks:**
   ```bash
   pre-commit install
   ```

## Development Workflow

We use a `Makefile` to simplify common tasks:

- `make format`: Formats code using `uv run ruff format`.
- `make check`: Runs the repo-default validation pass with `uv`.
- `make check-matrix`: Runs `ruff`, `ty`, and `basedpyright` under Python `3.11`, `3.12`, and `3.13`.
- `make tests`: Runs the test suite using `uv run pytest`.
- `make all`: Runs `make format` then `make check`.
- `make prod`: Runs `make tests`, `make format`, and `make check-matrix`.

Before submitting a Pull Request, ensure `make prod` runs without errors.

## Pull Requests

1. Create a new branch for your feature or bugfix.
2. Commit your changes (your commit will be checked by `pre-commit`).
3. Push to your branch and open a Pull Request.
4. Ensure the CI workflows (GitHub Actions) pass.
