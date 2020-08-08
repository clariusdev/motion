Interial Measurement Unit
=========================

This repository contains all related items for using the integrated 9-DOF inertial measurement unit (IMU) on Clarius devices.

Images, videos, and raw data will include IMU meta information when the sensor has been enabled. To enable, press the IMU icon from within the modes menu within the Clarius App.

Inertial data can be accessed by:
- Using the Listen API to stream images in real-time
- Accessing stored  images, videos, and raw data from Clarius Cloud

The inertial data is sent or stored in text & binary formats, depending on the mode of acquisition, and includes:
- Linear acceleration (accelerometer)
- Angular velocity (gyroscope)
- Magnetic flux density (magnetometer)

## Calibration
If using the IMU for positional or motion tracking, ensure to calibrate the device on a semi-regular basis through the Motion Sensor calibration section in the Clarius App settings

There are two calibration modes:
- Static calibration, where the probe must remain still on a flat surface
- Motion calibration, where the probe should be rotated across all axes for approximately 10 seconds

## Units
- Acceleration is normalized to gravity (m/s2) / (m/s2)
- Angular rate is provided in degrees per second (dps)
- Magnetic flux density is provided in Gauss

## Axis Orientation:
The axes are based on raw data collection. It may be necessary to rotate or invert the raw measurements to ensure they align with the desired reference point(s). For example, multiplying both the X and Y measurements by -1 would be a 180° degree rotation around the Z axis.

## Sensor Location:
The physical sensor is offset from the centre of the imaging plane by the following dimensions. The Y and Z dimensions are the same for all models and the X dimension is model specific as shown in the table below.

![Axes](https://support.clarius.com/hc/article_attachments/360023171331/image.png)

Distance from scanning plane to internal sensor by scanner model (first generation Clarius):

| Model | X (mm) | Y (mm) | Z (mm) |
| :---- | :----- | :----- | :----- |
| C3    | -150   | 18     | -5.4   |
| C7    | -156   | 18     | -5.4   |
| L7    | -149   | 18     | -5.4   |

## Data Collection

### Listen API

The Listen API allows images and inertial data to be collected in real-time. When a new image is received, a set of inertial data will be passed to the new image callback function. Several inertial measurements may acquired for a single image, depending on the imaging frame rate. The ClariusPosInfo struct contains the inertial data for each measurement and contains 14 pieces of information:
- Data timestamp
- 3 gyroscope axes
- 3 accelerometer axes
- 3 magnetometer axes
- 1 real component of the orientation quaternion
- 3 imaginary components of the orientation quaternion

### Offline

Clarius Cloud is a convenient way to store and access images and data. Inertial information can be uploaded to Clarius Cloud after activating the sensor. Raw data can be downloaded from Clarius cloud in a compressed folder for offline analysis; the compressed file contains timestamp_imu.yml which contains the inertial measurements associated with the raw data and images collected.

Each entry in imu.yml file contains the same information as specified in the ClariusPosInfo structure for the Listen API.
