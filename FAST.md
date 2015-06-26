# Link #

[Papers and Source Code](http://www.edwardrosten.com/work/fast.html)


# Basic Idea #

Fast tests the surrounding pixels of a possible corner. A pixel is a corner since the pixel is very different from most of its surroundings. The surrounding Pixels are located on a circle around the center Pixel as shown in the Picture below.

[![](http://www.edwardrosten.com/work/corner.png)](http://www.edwardrosten.com/work/fast.html)

The highlighted squares are the pixels used in the corner detection. The pixel at p is the centre of a candidate corner.

To speed up matching, the response in the horizontal and vertical directions only is checked first. If this response is positive only then are these possible corners' circles checked. If there are n contiguous pixels in the circle which are all brighter than the intensity of the candidate pixel Ip plus a threshold t, or all darker than Ip − t, then the candidate Pixel classifies as a corner.

In this Project you can choose 9 to 12 for Number n.