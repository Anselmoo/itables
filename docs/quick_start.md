---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: itables
  language: python
  name: itables
---

# Interactive Tables

**Pandas DataFrames as Interactive DataTables**

[![Pypi](https://img.shields.io/pypi/v/itables.svg)](https://pypi.python.org/pypi/itables)
![CI](https://github.com/mwouts/itables/workflows/CI/badge.svg)
[![codecov.io](https://codecov.io/github/mwouts/itables/coverage.svg?branch=main)](https://codecov.io/github/mwouts/itables?branch=main)
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/mwouts/itables.svg)](https://lgtm.com/projects/g/mwouts/itables/context:python)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
<a class="github-button" href="https://github.com/mwouts/itables" data-icon="octicon-star" data-show-count="true" aria-label="Star mwouts/itables on GitHub">Star</a>
<script async defer src="https://buttons.github.io/buttons.js"></script>

## Quick start

Install the `itables` package with

```shell
pip install itables
```

Activate the interactive mode for all series and dataframes with

```{code-cell} ipython3
from itables import init_notebook_mode

init_notebook_mode(all_interactive=True)
```

After this, any Pandas object (DataFrame or Series) is displayed as an interactive [datatables.net](https://datatables.net/) table, which lets you explore, filter or sort your data.

```{code-cell} ipython3
from itables.sample_dfs import get_countries

df = get_countries()
df
```

If you prefer to render just one series or dataframe as an interactive table, use `show`:

```{code-cell} ipython3
from itables import show
from itables.sample_dfs import get_population

x = get_population()
show(x)
```

(NB: In Jupyter Notebook, Jupyter NBconvert and Jupyter Book, you need to call `init_notebook_mode()` before using `show`).

## Offline mode

While the table data is embedded in the notebook, the [jquery](https://jquery.com/) and [datatables.net](https://datatables.net/) libraries and CSS are normally loaded from a CDN, so an internet connection is normally to display the tables.

The only exception to this is Jupyter Lab, which has an offline mode. To activate that mode, you should use `itables>=0.5.0` and install our [`jupyterlab-itables` extension](https://github.com/mwouts/jupyterlab-itables) with
```shell
pip install jupyterlab-itables
```

:warning: Unlike `itables` which has to be installed in the Python environment used in the notebook (the _kernel_), the `jupyterlab-itables` extension should be installed in the Python environment used to serve the notebooks (i.e. the environment in which you execute `jupyter lab`).

## Advanced parameters

The `show` method let you pass parameters to [datatables.net](https://datatables.net/)'s `DataTable()`'s constructor - see the [advanced parameters examples](advanced_parameters.md).

## Try ITables on Binder

You can run our examples notebooks directly on [![Lab](https://img.shields.io/badge/Binder-JupyterLab-blue.svg)](https://mybinder.org/v2/gh/mwouts/itables/main?urlpath=lab/tree/docs/quick_start.md), without having to install anything on your side.