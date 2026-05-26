# f5c_rna-dist

Public binary-wheel distribution for **f5c_rna** — in-memory direct-RNA
eventalign (RNA002 / RNA004), CPU + GPU.

The engine source (C/C++/CUDA) lives in a private repository. **Only compiled
wheels are published here** — the `.whl` files contain machine code, not source.

## Install

This repo serves a [PEP 503](https://peps.python.org/pep-0503/) simple index via
GitHub Pages.

```sh
# CPU (portable manylinux wheel)
pip install --index-url https://loganylchen.github.io/f5c_rna-dist/simple/ f5c_rna

# GPU (CUDA 12.2 build; needs a matching NVIDIA driver)
pip install --index-url https://loganylchen.github.io/f5c_rna-dist/simple/ "f5c_rna==<version>+cu122"
```

To use it alongside PyPI for dependencies, use `--extra-index-url` instead:

```sh
pip install --extra-index-url https://loganylchen.github.io/f5c_rna-dist/simple/ f5c_rna
```

Wheels are hosted as release assets on this repository and indexed automatically
by the upstream project's CI on each tagged release.
