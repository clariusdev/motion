IMU Renderer
============

A small python application that receives IMU rotational information through the Listen API and renders the Clarius L7HD scanner.

Requirements for executing under Linux:
- Install Pillow (latest PIL library) and PySide2 using pip
- Copy pylisten.so and liblisten.so to same folder as pyimu.py (libraries found in the separate listen repository)
- Ensure scanner.obj and scanner.mtl files are in the same folder as pyimu.py
- Execute: LD_LIBRARY_PATH=. python3 pyimu.py
