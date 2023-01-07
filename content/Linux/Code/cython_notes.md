---
title: Cython (Python/C)
weight: -20
---

=> apt-get mingw-w64 (Windows)  
=> x86_64-w64-mingw32-gcc -o main64.exe main.cx  
=> cython --embed python.py -o python.c  
=> gcc -I /usr/include/python$(version) python.c -lpython$(version) -o python(.exe)
