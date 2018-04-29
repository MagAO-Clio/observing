Camera Operation
================


Coadds vs. Cubes
----------------

### Bit Depth

The electronics read out the Clio detector at a bit-depth of 16 bits per data pixel. Therefore cubes are saved as 16-bit. However, coadded images are saved as 32-bit, to avoid digital saturation.

### Readout Speed



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

