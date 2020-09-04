---
title: Jupyter
linktitle: Jupyter Notebooks
toc: true
type: docs
date: "2019-05-05"
draft: false

menu:
  python:
    parent: python_jupyter
    weight: 400


# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 400
---

{{< figure src="jupyter.png" title="" lightbox="true" width="200" >}}

Should we do Jupyter Lab??


## Matplotlib
To embed a Matplotlib pyplot figure in a notebook do:

```python
import matplotlib.pyplot at plt
%matplotlib inline
# or for interactive plots:
# %matplotlib notebook ```