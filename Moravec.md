# Algorithm #
## Measurement of intensity variation at Pixel P: ##
  1. Placing a square window at P (typical window Sizes: 3x3, 5x5, 7x7) (red).
  1. Shifting this window by one pixel in each of the eight principle directions (3x3 window around P). (blue)
  1. Intensity Variation shift calculated by sum of squares of intensity differences of these two windows.
  1. Intensity variation at P is the minimum intensity variation calculated over the eight principle directions.
[![](http://kiwi.cs.dal.ca/~dparks/CornerDetection/MoravecWindowCalculation.gif)](http://kiwi.cs.dal.ca/~dparks/CornerDetection/moravec.htm)

# Links #
  * [Moravec 1980 paper](http://www.ri.cmu.edu/pub_files/pub4/moravec_hans_1980_1/moravec_hans_1980_1.pdf)
  * [Helpful Moravec Explanation by Donovan Parks and Jean-Philippe Gravel](http://kiwi.cs.dal.ca/~dparks/CornerDetection/moravec.htm)


# Example #
![http://jfeaturelib.googlecode.com/svn/trunk/test/checkerboard.png](http://jfeaturelib.googlecode.com/svn/trunk/test/checkerboard.png)
![http://jfeaturelib.googlecode.com/svn/wiki/pictures/moravec_result_500_3.png](http://jfeaturelib.googlecode.com/svn/wiki/pictures/moravec_result_500_3.png)

Result for: Threshold = 500; Window Size = 3;


### Please note: ###
This Implementation differs from the [Moravec Wikipedia Article](http://en.wikipedia.org/wiki/Corner_detection#The_Moravec_corner_detection_algorithm). This is due to the fact that both the original paper from Moravec and the Explanation which were used to implement this Algorithm differ from Wikipedia.