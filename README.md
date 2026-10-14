# Sample repo for testing of `uv, ruff, ty`

> [!NOTE] Files within this repo:
> Initial file \( \rightarrow \) [average_edd_before_ruff_ty.py](average_edd_before_ruff_ty.py)
> Resulting file \( \rightarrow \) [average_edd.py](average_edd.py)

## Used commands:
```sh
uv init --no-package

uv add "django>5.0"
uv add django==5.2.18
uv remove django

uv sync
uv lock

uv add ruff
uv run ruff check
uv run ruff check --fix
uv run ruff check --fix --unsafe-fixes
uv run ruff format --check
uv run ruff format

uv add ty
uv run ty check --error all
```

## Ruff config:

```toml
[tool.ruff.lint]
select = [
    "E",    # pycodestyle
    "F",    # pyflakes
    "I",    # isort
    "UP",   # pyupgrade
    "B",    # flake8-bugbear
    "SIM",  # flake8-simplify
    "S",    # flake8-bandit
]
ignore = ["E501"]

[tool.ruff.format]
quote-style = "double"
indent-style = "space"
```