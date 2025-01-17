# Rigid Origami Animation Tool

[![GitHub release (latest SemVer including pre-releases)](https://img.shields.io/github/v/release/yrmiya/rigidori-animation?color=0033&include_prereleases&sort=semver)](https://github.com/yrmiya/rigidori-animation/releases/latest)

The repository contains a package to create vtk files for rigid origami animation.

The current version supports:

- Single crease fold (a)
- Miura-ori (b)
- Single-orbit Hexagonal-triangular Resch (c)
- Triangular startuck (d)

![Supported origami types][origami]

[origami]: img/origami.png "Supported origami types"

## List of packages

- ori-anim: Exports animation of selected rigid origami

## Requirements

- Python 3.10.x
  - NumPy
  - Matplotlib
  - SciPy
  - tqdm
- ParaView 5.8 (Download from [here](https://www.paraview.org/download/). The latest version is 5.11, but runs slow on laptop and requires powerful machine)

## Usage

### Generate 3D geometry file

In root directory of the project, run the program with origami type specified (ori_type), e.g., for Miura-ori,

```sh
python -m ori-anime run --ori_type miura
```

or

```sh
python3 -m ori-anime run --ori_type miura
```

For single crease fold, Resch, and startuck, give "crease", "resch", and "startuck" respectively, instead of "miura".

Without other arguments, the program generates vtk files with default parameters.
To define geometry, number of data points, and other options, see

```sh
python -m ori-anime run -h
```

or

```sh
python3 -m ori-anime run -h
```

### Clean previous results

To clean all previous results (`vtk_*/` directories and zip files) in the root directory, run

```sh
python -m ori-anime clean
```

or

```sh
python3 -m ori-anime clean
```

## Setting up environment

### Install Python

There are several different ways to install Python (for Mac and Linux, Python might be pre-installed and comes with OS).

1. Install with installer ([Python official website](https://www.python.org/downloads/release/python-3108/))
2. Install with Python distribution (e.g., [Anaconda](https://www.anaconda.com/products/distribution))
3. Install with package manager (e.g., homebrew for Mac, apt for Debian/Ubuntu)
4. Install with version control tool (e.g., [pyenv](https://github.com/pyenv/pyenv))

After installation, open terminal (e.g., PowerShell for Windows, Terminal for Mac and Linux) and run

```sh
python --version
```

or

```sh
python3 --version
```

Make sure that it returns Python 3.10.\*.

### Install required packages

To install packages, with pip

```sh
python -m pip install numpy matplotlib scipy tqdm PyQt5
```

or

```sh
python3 -m pip install numpy matplotlib scipy tqdm PyQt5
```

If the environmental path and alias are set for `pip`, simply

```sh
pip install numpy matplotlib scipy tqdm PyQt5
```

With Anaconda, either use GUI or

```sh
conda install numpy matplotlib scipy tqdm PyQt5
```

## Author

- Yasuhiro Miyazawa (Dept. of Aero. & Astro., UW)
- Ted Chang (Dept. of Aero. & Astro., UW)
