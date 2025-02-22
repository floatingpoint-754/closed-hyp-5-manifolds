# Closed hyperbolic 5-manifolds

This repository is a supplement to [arXiv:...], in which we construct and study some closed hyperbolic 5-manifolds.

## Requirements

Make sure you have [Python 3](https://www.python.org/) and [SageMath](https://www.sagemath.org/) installed.
You will also need a C++ compiler, such as [GCC](https://gcc.gnu.org/), to compile `count-cc.cpp`.

Next, install the GAP package [HAP](https://www.gap-system.org/Packages/hap.html):

```
$ sage -i gap_packages
```

On some installations this fails for similar reasons, but there should be a corresponding system package such as `gap-packages`.

Finally, clone this repository in a directory of your choice:

```
$ cd /path/to/directory
$ git clone https://github.com/floatingpoint-754/closed-hyp-5-manifolds
$ cd closed-hyp-5-manifolds
```

## Contents

This repo provides various Sage notebooks, containing computations and technical proofs referenced in the paper.
It is recommended to use the JupyterLab notebook:

```
$ sage -n jupyterlab
```

A browser tab will open, from which you can open the notebooks (and do your own experimentations).

The repository also contains the C++ program `count-cc.cpp`, which implements the Choi-Park formula,
and a precomputed list of good independent sets in `indsets.txt`.

## Details

The following is a description of each file provided here:

#### `5-manifolds.ipynb`
The main construction of the 5-manifolds: the Long 4-manifolds, their 17-fold coverings, the adjacency graph, good independent sets, and the quadratic residue code.
This notebook also generates the file `indsets.txt` and part of the code of `count-cc.cpp`.

#### `5-manifolds-2.ipynb`
An analogous notebook for the 4-manifold $X$, tessellated by 650 copies of the order-3 120-cell, and some possible colorings for the right-angled 5-manifold $Y$.

#### `count-cc.cpp`
An implementation of the Choi-Park formula, optimized specifically for the manifolds $N_{i,I}^\pm$.

#### `indsets.txt`
A text file containing 200054 lines, each containing 17 sorted and space-separated integers in {0, 1, ..., 271}: the labels of a good independent set.

#### `volume.ipynb`
The (rather short) computation of the volume of $P$, based on a number-theoretical formula of Emery and Kellerhals.

#### Classification of the manifolds $N_{i,I}^\pm$
The classification is very technical and is divided in three parts:
- `isometry-long-mfds.ipynb`: classification of Long manifolds up to tessellation-preserving isometry;
- `recover-from-tessellation.ipynb`: recovery of combinatorial information from the tessellation of $N_{i,I}^\pm$;
- `geodesics.ipynb`: classification of geodesics in the manifolds $N_{i,I}$ and proof of their unique tessellation by copies of $P$.
