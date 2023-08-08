# M-spectrophotometer-capture
# Real time spectrum capture and display using Python/OpenCV/Matplotlib

Specific application: interactive program to control and capture spectra from the Thunder Optics M-spectrophotometer.  See https://thunderoptics.fr/

This is a bare-bones Python program intended for aligning optics, with hard-coded options for device selection, wavelength axis scaling, and data file saving.
It captures a full frame and displays the region of interest (ROI) image using OpenCV, integrates the ROI vertically and displays the captured spectrum as an autoscaled plot, as fast as the data come in from the spectrophotometer. 

Developed on Windows 10 using Python 3.11. Modify as you see fit!

1. Device selection: video capture device number has to be determined by experiment, as they are arbitrarily chosen by the OS. "0" or "1" are likely choices.
2. Exposure control: integer power of 2, time in seconds. "0" is 1 second, "-1" is 0.5 seconds, etc.
3. Gain control: possible, but I don't know the allowable settings range. Gain values of 200 to 1000 seem to work as expected.
4. Interactive options: click on the "frameROI" window to bring it into focus.
- Typing "q" on the keyboard quits the program.
- Typing "s" on the keyboard saves the current displayed spectrum as an ASCII text file in .csv format. The first line is date/time/exposure/gain, following    lines are wavelength (nm) and intensity.
 - Typing "u" or "d" increases/decreases exposure setting by one stop (one power of two).
6. Device specific parameters: A, B, C, D are X-axis wavelength calibration constants for a third order polynomial, supplied with each M-spectrophotomter. ROI is also supplied. These constants were determined from the "settings" page in the Acquire menu of the Spectragryph software package, after loading the device specific calibration file.

Program installation and execution:

Install Python3, version 9 or greater, Python versions of OpenCV and Matplotlib.
On Windows 10, command line execution is best performed after setting default to a folder containing the M_capture.py source.
The source will need to be edited to reflect camera specific parameters and the video capture device number.

At the command prompt, type `python3 M_capture.py`

Suggestions for options are welcome!

Example spectrum display (blue sky, 0.5 second exposure):

![Capture](https://github.com/jremington/M-spectrophotometer-capture/assets/5509037/a112949e-9c29-420a-9e89-68357478a834)
