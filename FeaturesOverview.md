# Image Features #
  * AutoColorCorrelogram (since v1.2.0) Based on _[Image Indexing Using Color Correlograms](http://doi.ieeecomputersociety.org/10.1109/CVPR.1997.609412)_.
  * CEDD
  * Color Histogram
  * FCTH
  * Fuzzy Histogram
  * FuzzyOpponentHistogram
  * Gabor
  * Haralick Texture Features ([Wikipedia](http://en.wikipedia.org/wiki/Co-occurrence_matrix), [Google Scholar](http://scholar.google.de/scholar?q=Textural+features+for+image+classification))
  * Histograms:
    * Gray-Histogram
    * RGB Histogram, including possibility to only extract Red, Green or Blue histograms
    * HSB Histogram, including possibility to only extract Hue, Saturation or Brightness histograms
  * JCD
  * JpegCoefficientHistogram
  * LuminanceLayout
  * MPEG7ColorLayout
  * MPEG7EdgeHistogram
  * Statistical Moments. The first 4 statistical moments: Mean, Standard Deviation, Skewneess and Kurtosis
  * OpponentHistorgam
  * PHoG (Pyramid Histograms of Oriented Gradients) Based on _[Representing Shape with a Spatial Pyramid Kernel](http://www.robots.ox.ac.uk/~vgg/publications/2007/Bosch07/)_.
  * ReferenceColorSimilarity
  * [SURF](http://labun.com/imagej-surf/)
  * Sift Wrapper for the SIFT binary. The binary can be obtained [here](http://www.cs.ubc.ca/~lowe/keypoints/)
  * Tamura
  * Thumbnail

Some Features support masking. Masking can be used to extract features only from a certain part of the input image.
A list of the feature descriptor capabilities can be obtained by
```
java -cp JFeatureLib-x.x.x-jar-with-dependencies.jar de.lmu.ifi.dbs.jfeaturelib.utils.Extractor --list-capabilities

AutoColorCorrelogram     : [DOES_8G, DOES_8C, DOES_16, DOES_32, DOES_RGB]
CEDD                     : [NoChanges, DOES_8G, DOES_8C, DOES_32, DOES_RGB]
ColorHistogram           : [Masking, NoChanges, DOES_8C, DOES_16, DOES_32, DOES_RGB]
FCTH                     : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
FuzzyHistogram           : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
FuzzyOpponentHistogram   : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
Gabor                    : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
Haralick                 : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
Histogram                : [Masking, NoChanges, DOES_8G, DOES_8C, DOES_RGB]
JCD                      : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
JpegCoefficientHistogram : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
LuminanceLayout          : [DOES_8G]
MPEG7ColorLayout         : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
MPEG7EdgeHistogram       : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
Moments                  : [DOES_8G, DOES_8C, DOES_16, DOES_32, DOES_RGB]
OpponentHistogram        : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
PHOG                     : [Masking, DOES_8G, DOES_8C, DOES_16, DOES_32]
ReferenceColorSimilarity : [Masking, NoChanges, DOES_8C, DOES_16, DOES_32, DOES_RGB]
SURF                     : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
Sift                     : [DOES_8G]
Tamura                   : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
Thumbnail                : [NoChanges, DOES_8G, DOES_8C, DOES_RGB]
```

Several implementations of features are origininally located in the [Lire](http://lire.googlecode.com)-Project. JFeatureLib provides wrapper methods/classes so that these features can be extracted like others, too.


---


# Point Detectors #
  * [Harris Corner Detector](http://svg.dmi.unict.it/iplab/imagej/Plugins/Feature%20Point%20Detectors/Harris/harris.htm)
  * [Moravec](http://code.google.com/p/jfeaturelib/wiki/Moravec)
  * [Trajkovic And Hedley](http://code.google.com/p/jfeaturelib/wiki/TrajkovicHedley)
  * [FAST](http://code.google.com/p/jfeaturelib/wiki/FAST) - ([paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.60.3991&rep=rep1&type=pdf))

---


# Edge Detectors #
  * [Sobel-Operator](http://en.wikipedia.org/wiki/Edge_detection) (in edgeDetector.Kernel)
  * [Scharr-Operator](http://en.wikipedia.org/wiki/Edge_detection) (in edgeDetector.Kernel)
  * [Prewitt-Operator](http://en.wikipedia.org/wiki/Edge_detection) (in edgeDetector.Kernel)
  * [Kirsch-Operator](http://en.wikipedia.org/wiki/Kirsch-Operator)
  * [Canny ](http://www.graphics.pku.edu.cn/members/chenyisong/lectures/readings/Canny86pami.pdf)
  * [Marr-Hildreth](http://de.wikipedia.org/wiki/Marr-Hildreth-Operator) ([paper](http://cirl.lcsr.jhu.edu/wiki/images/7/77/MarrHildreth.pdf))
  * [SUSAN](http://users.fmrib.ox.ac.uk/~steve/susan/susan/node2.html)
  * [Roberts-Operator](http://en.wikipedia.org/wiki/Roberts_Cross)
  * [Laplace-Filter](http://en.wikipedia.org/wiki/Discrete_Laplace_operator) ([ImageJ Plugin](http://svg.dmi.unict.it/iplab/imagej/Plugins/Forensics/Filters/PAGINE%20HTML/Laplaciano.html))
  * Derivative of Gaussian ([DroG](http://svg.dmi.unict.it/iplab/imagej/Plugins/Edge%20Detectors/Canny/EdgeDetection.htm))

---


# Shape Features #
(keep in mind that those only work on binarized images, see [issue 15](https://code.google.com/p/jfeaturelib/issues/detail?id=15))
  * AdaptiveGridResolution
  * CentroidBoundaryDistance
  * CentroidFeature
  * Compactness
  * Eccentricity
  * Extremal Points
  * PolygonEvolution
  * Profiles
  * SquareModelShapeMatrix (since v1.1.0) also known as GridDescriptor. Based on _[Invariant shape description and measure of object similarity](http://scholar.google.de/scholar?q="Invariant+shape+description+and+measure+of+object+similarity")_

---


# Sources for other Features/Detectors #
Several other features and point detectors are described and evaluated in the following publications:
  * [Hough transformation](http://www.dtic.mil/cgi-bin/GetTRDoc?AD=ADA457992&Location=U2&doc=GetTRDoc.pdf)
  * [HIP Histogram Intensity Patches](http://www.springerlink.com/index/16K40W2J465L3521.pdf)
  * [MPEG7](http://www.ee.columbia.edu/~sfchang/course/vis/REF/sikora01.pdf)
  * [Evaluation of Interest Point Detectors and Feature Descriptors for Visual Tracking](http://www.springerlink.com/content/k062m660066wl2j6/)
  * [Evaluation of Interest Point Detectors ](http://www.springerlink.com/content/k4v378g251624x64/)

  * http://users.ecs.soton.ac.uk/msn/book/new_demo/
  * [CenSurE](http://www.springerlink.com/content/ngx06074r126x362/)
  * [Histogram Intersection, Histogram Backprojection](http://dl.acm.org/citation.cfm?id=134841)
  * [OpenCV](http://opencv.willowgarage.com/wiki/)
  * http://koen.me/research/colordescriptors/readme
  * http://www.semanticmetadata.net/features/
    * ColorLayout (measures color distribution in an image)
    * ScalableColor (basically a color histogram)
    * EdgeHistogram (measures edginess)
    * DominantColor (measure dominant colors)
  * http://svg.dmi.unict.it/iplab/imagej/index.htm GPL licenced for jFeatureLib
  * Surface Roughness ([issue 1](https://code.google.com/p/jfeaturelib/issues/detail?id=1))  [ImageJ Plugin and description](http://www.gcsca.net/IJ/SurfCharJ.html)
  * [Low-dimensional and comprehensive color texture description](http://www.sciencedirect.com/science/article/pii/S107731421100186X)
  * [Interest Operators](http://de.wikipedia.org/wiki/Interest-Operator#Moravec-Operator)

Shape descriptors
  * [Zernike moments](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.89.431&rep=rep1&type=pdf)
  * [Shape Survey](http://hal.archives-ouvertes.fr/docs/00/44/60/37/PDF/ARS-Journal-SurveyPatternRecognition.pdf)
  * [another Shape Survey](http://cdn.intechopen.com/pdfs/5781/InTech-A_survey_of_shape_feature_extraction_techniques.pdf)

Edge Detectors:
  * http://en.wikipedia.org/wiki/Edge_detection / http://de.wikipedia.org/wiki/Kantendetektion include the links to
  * Kontrastverstärker