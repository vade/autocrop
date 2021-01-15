# autocrop
Automatically crop and rotate scanned images using OpenCV.
Should work on Windows, Linux and Mac.

## Install requirements

```bash
pip install opencv-python
pip install numpy
```

## Usage
### Simple
Place autocrop.py into a folder of scanned images. Those images should be roughly cropped already (see examples).
Also: only one image per scan!

`python autocrop.py`

This creates a new folder `crop` where all cropped and rotated images will be saved to. 

### Additional options
`python autocrop.py [-h] [-i INPUT_PATH] [-o OUTPUT_PATH] [-t THRESHOLD] [-c CROP] [-p THREADS] [-s]`

|Argument| Description|
|:--|:--|
|`-h, --help`| Show this help message and exit.|
|  `-i INPUT_PATH`| Input path. Specify the folder containing the images you want be processed.|
|`-o OUTPUT_PATH`| Output path. Specify the folder name to which processed images will be written.|
|`-t THRESHOLD`| Threshold value. Higher values represent less aggressive contour search. If it's chosen too high, a white border will be introduced.|
|`-c CROP`| Standard extra crop. After crop/rotate often a small white border remains. This removes this. If it cuts off too much of your image, adjust this.|
|`-p THREADS`| Specify the number of threads to be used to process the images in parallel. If not provided, the script will try to find the value itself (which doesn't work on Windows or MacOS -> defaults to 1 thread only).|
|`-s, --single`| Process single image. i.e.: -i img.jpg -o crop/|

## Troubleshooting

### Problem:
`ValueError: too many values to unpack (expected 2)`
### Solution:
You likely use an outdated version of OpenCV. Make sure you have OpenCV 4.0 or higher installed. The version can be checked by executing the following code in the terminal.

```bash
python -c 'import cv2; print(f"OpenCV version: {cv2.__version__}")'
> OpenCV version: 4.2.0
```

## Todo: executables for Windows + basic GUI
To make it usable for less nerdy people.
