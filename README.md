
# Learn Poetry

Python Poetry (https://python-poetry.org/) is a Python dependency and package management tool.  It replaces PIP and removes the friction from creating a python project suitable for repackaging.

## Install

```bash
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -
```

## Create a Project

```bash
poetry new learn-poetry
```

## Add a dependency

```bash
poetry add geopandas
```

This updates pyproject.toml:

```toml
[tool.poetry.dependencies]
python = "^3.9"
geopandas = "^0.9.0"
```

## Install dependencies (after cloning a repo)

```bash
poetry install 
```

## Add Python Files

learn_poetry/geospatial.py

```python
import geopandas

path_to_data = geopandas.datasets.get_path("nybb")
gdf = geopandas.read_file(path_to_data)

gdf["area"] = gdf.area

print(gdf[["BoroName", "area"]])
```

## Run a Poetry Project

```bash
poetry run python learn_poetry/geospatial.py
```

## Run Pytest Tests

```bash
poetry run pytest
```