# Poetry

``` shell
poetry new
poetry env use python3.12
poetry env info
poetry shell
poetry run COMMAND
poetry show --tree
portry show --lateset
```

Add custom command:
``` toml
[tool.poetry.scripts]
somecmd = "tests.main:func"
```
Then
```shell
poetry install
```
