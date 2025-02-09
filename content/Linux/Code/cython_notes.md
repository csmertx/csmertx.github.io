---
title: 💻 Cython
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-31
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/19/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Code/cython_notes.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Code \ Cython">
       History 🕵️
    </a>
</div>