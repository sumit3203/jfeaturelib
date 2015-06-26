# Algorithm #
  1. A circle is drawn around Pixel P and in this Implementation only the 4 Points from the circle are used to calculate the cornerness measure. The first calculation is performed on a lower Resolution image to decrease computation. ![http://kiwi.cs.dal.ca/~dparks/CornerDetection/TrajNotation.gif](http://kiwi.cs.dal.ca/~dparks/CornerDetection/TrajNotation.gif) ![http://kiwi.cs.dal.ca/~dparks/CornerDetection/TrajFormulaCornerness.gif](http://kiwi.cs.dal.ca/~dparks/CornerDetection/TrajFormulaCornerness.gif)
  1. If this cornerness measure is grater than the first Threshold it is added as a potential Corner.
  1. These potential Corners are then examined in the original Image, by calculation a simple cornerness measure again. ![http://kiwi.cs.dal.ca/~dparks/CornerDetection/TrajFormulaSimple2.gif](http://kiwi.cs.dal.ca/~dparks/CornerDetection/TrajFormulaSimple2.gif)
  1. If this corner is still a possible corner then a Interpixel Cornerness Measure is computed. ![http://kiwi.cs.dal.ca/~dparks/CornerDetection/TrajFormulaInterpixel.gif](http://kiwi.cs.dal.ca/~dparks/CornerDetection/TrajFormulaInterpixel.gif)
  1. If this inter pixel measure is greater than the second threshold, the examined Pixel is a corner

Images taken from [here](http://kiwi.cs.dal.ca/~dparks/CornerDetection/trajkovic.htm).


# Links #

  1. [Basic algorithm by Donovan Parks and Jean-Philippe Gravel, used for this Detector](http://kiwi.cs.dal.ca/~dparks/CornerDetection/trajkovic.htm)
  1. [Wikipedia](http://en.wikipedia.org/wiki/Corner_detection#The_Trajkovic_and_Hedley_corner_detector)

# Example #
![http://jfeaturelib.googlecode.com/svn/trunk/test/checkerboard.png](http://jfeaturelib.googlecode.com/svn/trunk/test/checkerboard.png)
![http://jfeaturelib.googlecode.com/svn/wiki/pictures/trajkovic_result_1_500_500_2.png](http://jfeaturelib.googlecode.com/svn/wiki/pictures/trajkovic_result_1_500_500_2.png)

Result for:
Distance = 1;
Threshold1 = 500;
Threshold2 = 500;
Lower Resolution Size = 2;