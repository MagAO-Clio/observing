Motors
======

Clio uses Parker OEM750 cryogenic motors. There are no encoders so we home the motors before each move, so a filter change (which moves 2 motors) takes about 2--3 minutes.


Motors and Wheels
-----------------

Clio has 6 motors that control the following 6 wheels:
1. Field Stop
2. Pupil Stop
3. Filter Wheel 1
4. Filter Wheel 2
5. Camera Lens
6. Collimator Lens

What is in each wheel, in order, as of 2015--2018:

| 1. Field | 2. Pupil | 3. FW 1 | 4. FW 2 | 5. Camera Lens | 6. Collimator |
|:--------:|:--------:|:-------:|:-------:|:----------:|:-------------:|
| 50um Pinhole | f/21.5 Stop | Blocked | J band | f/21.5 | f/37.7 |
| Open | vAPP A1 | MKO M' | 0.1% ND | Pupil Imaging | f/21.5 |
| Narrow Slit | vAPP A2 | 3.3um | 4.4% ND | f/37.7 |  |
| 120mas Medium Slit | f/37.7 Stop | Prism | Open |  |  |
| 360mas Wide Slit |vAPP B1 & B2 | 3.1um | Lspec |  |  |
| Rectangle | 6-hole NRM | MKO L' | BrGamma |  |  |
|  |  | 3.9um | Barr Ks |  |  |
|  |  | PK50 | H band |  |  |


Wide and Narrow Camera:
-----------------------

### Changing magnification, or putting in a pupil mask

* The Narrow camera has a focal ratio of approximately f/37.7.
* The Wide camera has a focal ratio of approximately f/21.5.

When you want to change magnifications, you have to go to pupil imaging mode to align the pupil stop and collimator lens by eye.

Put:
* Motor 2 -> Selected cold stop or pupil mask
* Motor 3 -> 3.9um (for imaging the sky in thermal)
* Motor 4 -> Open (other filter wheel)
* Motor 5 -> Pupil Imaging
* Motor 6 -> f/stop of selected camera

