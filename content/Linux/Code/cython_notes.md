---
title: 💻 Cython
author: Chris Schammert (csmertx -- Christopher Schammert)
published: 2023-01-31
weight: -20
---

<br />

> Python language translator for C (check links below for current information)

## Installation

> For Linux systems

### Windows

- ```sudo apt-get mingw-w64```

### Linux

- ```sudo apt-get cython3```

## Translate Python to C using Cython

> Basic examples

### Create Linux programs

- ```cython --embed python.py -o python.c```

- ```gcc -I /usr/include/python$(version) python.c -lpython$(version) -o python(.exe)```

### Create Windows programs

- ```x86_64-w64-mingw32-gcc -o main64.exe main.cx```

## Resources

- [Cython: C-Extensions for Python](https://cython.org/)