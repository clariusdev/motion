IMU Renderer
============

A small python application that receives IMU rotational information through the Cast API and renders the Clarius L7HD scanner.

Requirements for executing under Linux:
- Install Pillow (latest PIL library) and PySide6 using pip
- Copy the pyimu.py to the extracted libs folder (where pyclariuscast.so and libcast.so are placed)
- Ensure scanner.obj and scanner.mtl files are in the same folder as pyimu.py
- Execute: python3 pyimu.py
