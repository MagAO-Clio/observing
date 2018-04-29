---
title: Observing with Clio on MagAO at Magellan Clay
---


User's Guides
=============
1. Beginning of the Night Checklist
  * How to start up Clio2
2. Using Clio Cookbook
  * A quick guide to taking data, once you're on sky and ready to go
  * Camera Operation[https://magao-clio.github.io/observing/camera_operation]
  * Info about the Array and Subarray sizes and Co-adds allowed
  * How to run the camera through the GUI
3. Observing Scripts
  * How to run the camera through scripts
4. PSF Stars (Switching stars quickly)
  * How to take PSF stars, i.e. How to work with the AO operator and TO to reduce overheads in order to quickly acquire a PSF star (only works when the target star is a similar brightness and in a similar part of the sky)
5. Spectroscopy


Random note:
============
Which file is being used to subtract the background?

Check Programs/mirkwood_persist.cfg

It's the one in this line:

dark_fn dark0.fit



Info
====
Filters Info -- List of which filters we have in the 2 wheels, also includes filter curves
Pupil Stops
Readout Efficiency Tests -- Also includes info about what the various combinations of Nimg, Coadds, and Cubes mean for your data taking.

Data Reduction
==============
Orientation (true North)
Non-linearity/Saturation: Pixels above 27000 DN are non-linear and must be corrected. Conservatively, pixels above ~45000 should be considered saturated because they can not be corrected to high precision. (See more at Calibration Data)
Calibration Data - Bad pixel map, astrometric calibration, linearity, flat fields, etc. Also links to raw calibration data such as Calibration Data - 2014A
Full Frame and Sub Frame Formats - Info about Full Frame, Strip, Stamp, and Substamp Mode


User's Resources
================
Magellan Weather Info
Magellan telescopes weather station: All-inclusive weather info
Las Campanas weather info (old page)
Environmental information page
Precipital Water Vapor at La Silla
L' and M' photometric standards
