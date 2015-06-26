


# Contact #
Discussions and announcements can be found at the according [GoogleGroup](https://groups.google.com/forum/#!forum/jfeaturelib).


# Maven #
Unfortunately we have a dependency to [LIRE](https://code.google.com/p/lire/) which is not on Maven. So you have to install Lire into your local repo which is pretty easy!
  * [Maven artifacts](http://mvnrepository.com/artifact/de.lmu.ifi.dbs.jfeaturelib/JFeatureLib):
```
<dependency>
	<groupId>de.lmu.ifi.dbs.jfeaturelib</groupId>
	<artifactId>JFeatureLib</artifactId>
	<version>1.6.1</version>
</dependency>
```
    1. Clone the repo from GitHub: `git clone https://github.com/locked-fg/LIRE.git`
    1. Install the lib into your local repo: `mvn -Prelease install -DskipTests=true -Dgpg.skip=true`
    1. now build JFeatureLib

# Development Environment #
The currently favoured developmnet IDE is [NetBeans](http://netbeans.org/). Eclipse is accepted as well, just don't check in Eclipse specific files (like classpath).
in order to prevent reinventing the wheel, we rely on [ImageJ](http://rsb.info.nih.gov/ij/index.html) which provides several very fast implementations for some operations.
ImageJ sources and Java Docs are not included in the SVN but may be very helpful for your project setting. You can download source and API [directly from the ImageJ website](http://rsb.info.nih.gov/ij/download.html).

# Java Platform #
The minimum required Java version is currently Java 7.


# Code Style #
The basic code style is the default style which is proposed by a fresh [NetBeans](http://netbeans.org) installation.
Just hit `Alt+Shift+F` for auto-formating once in a while (especially before checking in!).

  * 1 Tab should expand to 4 spaces
  * UTF-8 encoding should be used throughout the whole project (Eclipse defaults to your OS-setting)
  * For loops and conditionals, open the bracket in the same line as the loop/if statement and always use brackets:
```
if ( foo ) {
 ...
}
```



# new Image Features #
Image Features should be placed in the package `de.lmu.dbs.features` and must implement `de.lmu.dbs.features.FeatureDescriptor` or extend `de.lmu.dbs.features.FeatureDescriptorAdapter`.
It is recommended to extend `FeatureDescriptorAdapter` as deprected methods find a default implementation there before they will be removed from the API.



# new Interesting Point Detectors #
coming soon, but very similar to "new Image Features"



# new Descriptors/Detectors #
For each new descriptor (e.g a new `GrayLevelHistogram` for a running examoke), please check the following steps:
  * Place the class implementing `FeatureDescriptor` directly in the package `de.lmu.dbs.features` and give it a reasonable name using [CamelCaseNotation](http://en.wikipedia.org/wiki/CamelCase). Do not mind if the name is a bit longer. Just avoid names like `CoGLHist` instead of `CombinedGrayLevelHistogram`.
  * If the descriptor requires additional classes which you do not want to keep as inner classes, create a package with the same name like `de.lmu.dbs.features.combinedGrayLevelHistogram` and place all additional classes in there.
  * Try not to use classes from other descriptors! This quickly leads to unmaintainable all-to-all dependencies. Either copy the according class or request to extract a super class which might be put in `de.lmu.dbs.utils`.
  * Use the strictest possible [access modifiers](http://en.wikipedia.org/wiki/Java_syntax#Access_modifiers) for your classes, methods and fields.
  * Never return instances of [nested/inner classes](http://download.oracle.com/javase/tutorial/java/javaOO/nested.html). As they always keep an implicit reference to the surrounding class, you might be producing memory leaks as the outer class cannot be garbage collected as long as the inner class instance lives. If you think you have to return such a class, you should have good reasons ;)
  * Avoid `System.out.println()` statements but use the [java logging framework](http://download.oracle.com/javase/1.4.2/docs/guide/util/logging/overview.html) (examples follow soon).

For documentation purposes, add an entry to the FeaturesOverview page including:
  * Class Name of the class implementing `(Multi)FeatureDescriptor`
  * What is the aim of the descriptor/detector
  * Link to a ressource from where you have taken the definitions (wiki, publication, bibtex, etc).
  * If all the information above is given in the JavaDoc of the according class, just link to the file.


# External Resources #
  * [API Docs](http://api.jfeaturelib.googlecode.com/git/)
  * [Maven Repository](https://oss.sonatype.org/content/groups/public/de/lmu/ifi/dbs/jfeaturelib/JFeatureLib/)
  * [GitHub Mirror](https://github.com/locked-fg/JFeatureLib)
  * [Travis-Ci build status](https://travis-ci.org/locked-fg/JFeatureLib)