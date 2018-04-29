Camera Operation
================


Coadds vs. Cubes
----------------

### Readout Efficiency Tests

* 2014/07/18

For the Key Project we are interested in temporal sampling of the PSF. So here we did some efficiency tests of the various combinations of Integration time, Coadds, and Cubes to see which mode to use to jointly optimize temporal sampling and efficiency. First let's explain the different options in ways to save Coadds and Cubes.

#### Clio Data Sequence Options:
Between Coadds, Nimgs, and Cubes, there are a few options for temporal sampling and resultant image size for how to take a sequence of Clio data. *If you are using Cubes, then the Coadds are not added but are saved as individual frames within a 3-dimensional data cube.* The Cube will be saved as a single .fit file and so it will have only 1 FITS header. Thus, while the temporal sampling of the data is higher, the temporal sampling of the FITS header (not listed here) is per .fit written. Also, the FITS header will state the # of Coadds only if they are added, so if you are saving in Cubes, asking for "10 coadds saved in cubes" gives you 1 coadd in 10 frames in a data cube.

The Table explains it with an example:

| Nimgs | Integration Time [ms] | Coadds | Cubes | What Will the FITS Header Say for # of Coadds | Result | FITS dimensions (Example for Full Frame) | Total Integration Time [sec] = Nimg x IntTime x Coadds | Temporal Sampling of Images [sec] |
|:--:|:----:|:-:|:--:|:-:|:----------------------------:|:----------:|:--:|:-:| 
| 10 | 1000 | 1 | No | 1 | 10 2-d FITS files, no coadds | 1024 x 512 | 10 | 1 |
| 10 | 1000 | 10 | No | 10 | 10 2-d FITS files, each with 10 frames coadded (the total duration is 10x longer than the above line) | 1024 x 512 | 100 | 10 |
| 10 | 1000 | 1 | Yes | 1 | 10 "3-d" FITS files, with the coadds saved in cubes except that since there is only 1 coadd, the 3rd dimension has nothing in it | 1024 x 512 x 1 | 10 | 1 |
| 10 | 1000 | 10 | Yes | 1 | 10 3-d FITS files, each with 10 frames in a 3-d Cube | 1024 x 512 x 10 | 100 | 1 |


#### And here are the readout efficiency tests:

(Also a quick note about taking data at a very high temporal sampling. To save computer processing speed, you may want to stop the Transfer Files program (hit the X in upper left corner of window) during the data taking. Restart it when resuming normal observations by going to Restart Clio Components -> FileBackup)

##### Strip Mode Tests

| Integration time [ms] | # Coadds | Cubes or 2-d FITS? | # Frames | Images ID | Total Clock Time Elapsed [min:sec] / [sec] | Total Integration [sec] | % Efficiency = 100 x Total Integration / Clock Time Elapsed | Temporal Sampling of Images [sec] |
|:---:|:--:|:-----:|:--:|:-----------------:|:--------------:|:----:|:------:|:-----:|
| 164 | 40 | Cubes | 15 | n140410 test 1-15 | 3:39.5 / 219.5 | 98.4 | 44.8 % | 0.164 |
| 164 | 40 | 2-d FITS | 15 | n140410 test 16-30 | 3:33.3 / 213.3 | 98.4 | 46.1 % | 6.56 |
| 164 | 1 | 2-d FITS | 600 | n140410 test 31-630 | 6:30.0 / 390.0 | 98.4 | 25.2 % | 0.164 |
| 164 | 6 | Cubes | 100 | n140410 test 631-730 | 4:10.8 / 250.8 | 98.4 | 39.2 % | 0.164 |


### Bit Depth

The electronics read out the Clio detector at a bit-depth of 16 bits per data pixel. Therefore cubes are saved as 16-bit. However, coadded images are saved as 32-bit, to avoid digital saturation.




Array Formats, Integration Times, and Coadds
--------------------------------------------

* Array Formats on clio1.lco.cl
  * clio1.lco.cl is the computer used to control Clio from 2012--2018

|    Format    |    Array Size    |    Minimum Int. Time (ms) (Also Readout Time)    |    Max. Coadds or Cubes     |
|--------------|------------------|--------------------------------------------------|-----------------------------|
| Full         | 1024 x 512       | 280                                              | 73                          |
| Strip        | 1024 x 300       | 164                                              | ?                           |
| Stamp        | 400 x 200        | 43                                               | ?                           |
| Substamp     | 100 x 50         | 3                                                | ?                           |


### Notes on measuring max. coadds on clio1.lco.cl, 2018/04/28, Alycia Weinberger:
This study was motivated by a data set Alycia took last year in which she saved 100 frames in cubes, but the data looked like normal images were read-out for the first 73 frames, but the last 27 frames were all 0s. So to test the corresponding limit with coadds, she put in the blocked filter and saved darks for varying numbers of coadds. She analyzed it by checking the number of counts per coadd, which should be steady if all the frames had actually been read-out and coadded. Instead, it looks like, similar to cubes, the # of counts per coadd starts dropping after around 73 frames -- so we assume that is the limit in the memory buffer for both cubes and coadds. (We limit this analysis to clio1.lco.cl because the clio2.lco.cl computer has a different memory buffer.)

| File | # coadds | counts per coadd if all frames were readout |
|:---:|:--------:|:------------------------------------------:|
| 2 | 36 | 7066.8 |
| 3 | 37 | 7035.8 |
| 4 | 50 | 7009.9 |
| 5 | 75 | 6812.5 |
| 10 | 20 | 6985.5 |
| 11 | 30 | 6987.7 |
| 12 | 19 | 6948.5 |
| 13 | 150 | 3412.7 |



* Array Formats on clio2.lco.cl
  * clio2.lco.cl is the computer used to control Clio from 2018--?

|    Format    |    Array Size    |    Minimum Int. Time (ms) (Also Readout Time)    |    Max. Coadds or Cubes     |
|--------------|------------------|--------------------------------------------------|-----------------------------|
| Full         | 1024 x 512       | 280                                              | ?                           |
| Strip        | 1024 x 300       | 164                                              | ?                           |
| Stamp        | 400 x 200        | 43                                               | ?                           |
| Substamp     | 100 x 50         | 3                                                | ?                           |

