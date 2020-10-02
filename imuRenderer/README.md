IMU Renderer
============

A small python application that receives IMU rotational information and renders a Clarius L7HD scanner accordingly.

Executing under Linux:
- Install Pillow (latest PIL library) and PySide2 using pip
- Copy pycast.so and libcast.so to same folder as imurenderer.py, these libraries can be found on Jenkins(build isonosw.master.linux.desktop)
- Ensure scanner.obj and scanner.mtl files are in the same folder as imurenderer.py
- Execute: LD_LIBRARY_PATH=. python3 imurenderer.py
