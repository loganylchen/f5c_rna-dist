# f5c_rna-dist

Public binary-wheel distribution for **f5c_rna** — in-memory direct-RNA
eventalign (RNA002 / RNA004), CPU + GPU.

The engine source (C/C++/CUDA) lives in a private repository. **Only compiled
wheels are published here** — the `.whl` files contain machine code, not source.

## Install

This repo serves two [PEP 503](https://peps.python.org/pep-0503/) simple indexes
via GitHub Pages. Like the PyTorch download channels, **the index URL selects the
backend** — the CPU and GPU wheels share a version, so you pick one by index, not
by version specifier.

```sh
# CPU (portable manylinux wheel) — the default index
pip install --index-url https://loganylchen.github.io/f5c_rna-dist/simple/ f5c_rna

# GPU (CUDA 12.2 build; needs a matching NVIDIA driver) — the opt-in index
pip install --index-url https://loganylchen.github.io/f5c_rna-dist/cu122/simple/ f5c_rna
```

To resolve dependencies from PyPI at the same time, add PyPI as an extra index:

```sh
# CPU
pip install \
  --index-url https://loganylchen.github.io/f5c_rna-dist/simple/ \
  --extra-index-url https://pypi.org/simple/ \
  f5c_rna

# GPU
pip install \
  --index-url https://loganylchen.github.io/f5c_rna-dist/cu122/simple/ \
  --extra-index-url https://pypi.org/simple/ \
  f5c_rna
```

Wheels are hosted as release assets on this repository and the indexes are
regenerated automatically by the upstream project's CI on each tagged release.
