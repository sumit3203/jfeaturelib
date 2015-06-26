The aim of **JFeatureLib** is to become a free library providing  reference implementations for
[several kinds of image features](FeaturesOverview.md) and point/region detectors used mainly in the research field of ComputerVision.
If you want to know some more about the background and target audience, please [read on here](Background.md).

**If you just want to download and use it, read on here.**

# moved over to github: https://github.com/locked-fg/JFeatureLib #

## Recent News ##
  * 2015/03/18: Google COde is shutting down - so everything finally moved over to github: https://github.com/locked-fg/JFeatureLib  Github is now the primary site!
  * 2014/09/13: published [v1.6.1](http://dl.bintray.com/locked-fg/JFeatureLib/JFeatureLib-1.6.1-bin.zip) with a stablized HARALICK computation. Thanks Erich Schubert, and an updated dependency to LIRE.
  * Google has shut down the ability to provide downloads here at GoogleCode. Therefore the downloads move over to [BinTray](https://bintray.com/locked-fg/JFeatureLib/de.lmu.ifi.dbs.jfeaturelib%3AJFeatureLib/view)
  * 2013/10/05: published v1.6.0 Thanks Sebastian Pölsterl
  * 2013/08/30: published v1.5.3 Thanks Johannes Niedermayer
  * 2013/08/25: published v1.5.2 Thanks Sebastian Pölsterl
  * 2013/08/17: published v1.5.1 Thanks Sebastian Pölsterl
  * 2013/07/24: published v1.5.0
**[more ...](https://code.google.com/p/jfeaturelib/source/browse/README.md)**


## Start using JFeatureLib ##
The main ressources to start working with JFeatureLib are:
  * The HowTo page for a quick start if you just want to extract features
  * [download](https://bintray.com/locked-fg/JFeatureLib/de.lmu.ifi.dbs.jfeaturelib%3AJFeatureLib/view) the latest complete package including runnable Jar, API Docs and Sources
  * [Javadoc API](http://api.jfeaturelib.googlecode.com/git/)
  * [Maven artifacts](http://mvnrepository.com/artifact/de.lmu.ifi.dbs.jfeaturelib/JFeatureLib):
```
<dependency>
	<groupId>de.lmu.ifi.dbs.jfeaturelib</groupId>
	<artifactId>JFeatureLib</artifactId>
	<version>1.6.1</version>
</dependency>
```
> > Unfortunately we have a dependency to [LIRE](https://code.google.com/p/lire/) which is not on Maven. So you have to install Lire into your local repo which is pretty easy!
    1. Clone the repo from GitHub: `git clone https://github.com/locked-fg/LIRE.git`
    1. Install the lib into your local repo: `mvn -Prelease install -DskipTests=true -Dgpg.skip=true`
    1. now build JFeatureLib


## How to get support ##
  * [Google Group](http://groups.google.com/group/JFeatureLib) code where announcements are posted. This is also a good place if you are seeking help.
  * [my Google+ profile](https://plus.google.com/107945158062341260943) where you can also contact me


## Reporting Bugs & Requesting Features ##
  * if you are experience a reproducible bug or
  * if you are desperately missing a feature or
  * if you know some code to integrate (must be GPL-compatible!)
Then, **please [file an issue](https://github.com/locked-fg/JFeatureLib/issues/) in the issue tracker**, write a mail/message to the [google group](http://groups.google.com/group/JFeatureLib) to share your experience or drop me a message in [G+](https://plus.google.com/107945158062341260943).


## What about openCV? ##
OpenCV is a great ressource for CV algorithms! Have a look at the [documentation](http://opencv.willowgarage.com/documentation/cpp/index.html), and you will find several valuable algorithms for image recognition etc.
Yet the support of reference implementations of feature descriptors is limited. JFeatureLib in contrary aims at providing reference implementations for feature descriptors and not algorithms that use these features.