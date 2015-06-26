#howTo Helpful guide to start with the library




---


# Questions #
Questions, discussions and announcements can be found at the according [GoogleGroup](https://groups.google.com/forum/#!forum/jfeaturelib).


# Usage #
## Extract features for multiple image classes ##
Using the commandline, features can be extracted via the [Extractor class](https://code.google.com/p/jfeaturelib/source/browse/src/main/java/de/lmu/ifi/dbs/jfeaturelib/utils/Extractor.java).

Imagine that you have two classe of images (classA, classB) and you want to extract [CEDD](https://code.google.com/p/jfeaturelib/source/browse/src/main/java/de/lmu/ifi/dbs/jfeaturelib/features/CEDD.java) features from the images. The features  should afterwards be saved in a CSV file.

**Step1:** Extract features for `classA` and write to output.csv
```
java -jar JFeatureLib.jar -D CEDD -c classA -d /images/of/classA -o /write/output.csv
```
**Step2:** Extract features for `classB`, omit headers (-nh) and append to  output.csv
```
java -jar JFeatureLib.jar -D CEDD -c classB -nh -d /images/of/classB --append -o /write/output.csv
```
**done!**


## Using masks ##
In some cases you might want to limit the feature extraction to certain regions of the input image.
From version 0.4.0, the `-m (--masks-dir)` option can be used to reference a directory containing masking images.
In order to match images to masking images, it is required that the directory structure must be the same in the image directory and in the masking directory. Also each image must have a corresponding masking image in the same relative directory branch. The file extension is ignored in this case.

The call `java -jar JFeatureLib.jar -d ./foo/images/ -m ./foo/masks/ ` will try to find a matching file in `/foo/masks` for each image in `/foo/images`.
```
foo/
   /images/foo.jpg
   /images/bar.jpg
   /masks/foo.png   <-- will match /images/foo.jpg
   /masks/x/bar.png <-- will *not* match as there is no /images/x/bar.*
```

If a mask is found, it will automatically be applied to the image prior to extracting the features. The extractor then ignores all black pixels and only process pixels with a value != 0.
But **keep in mind that not every feature extractor supports masking**! If you set a mask and use a feature descriptor that does not support masing, the masking is ignored and you should notice the following output:
`A masking directory is set but the chosen descriptor does NOT support masking. Masking will be ignored!`

A list of descriptors supporting masking will follow soon.


## Options ##
The options of the extractor class can be shown by simply calling the Extractor with no arguments or with the `--help` option
(x.x.x is of course the appropriate version number):
```
java -jar JFeatureLib-x.x.x-jar-with-dependencies.jar --help
 --append               : append to output file (default: false = overwrite)
 --help                 : show this screen
 --list-capabilities    : list the registered FeatureDescriptors and the output
                          of their supports() method
 --threads N            : amount of threads (defaults to amount of available
                          processors))
 --unpack-properties    : extracts the default properties and loggiing
                          properties into the current directory
 -D (--descriptor) VAL  : use this feature descriptor (e.G: Sift)
 -c VAL                 : image class that should be written to the output file
 -d (--src-dir) FILE    : directory containing images (default: execution
                          directory)
 -m (--masks-dir) FILE  : directory containing masks
 -nh                    : omit headerline
 -o (--output-dir) FILE : output to this file (default: features.csv)
 -r                     : recursively descend into directories (default: no)
 -v                     : show JFeatureLib debug messages
```


# Changing extraction options and logging #
Right after downloading you might only have the JAR files. to get the **jfeaturelib.properties** and **log4j.properties**, just either
  * open the JAR with any zip compatible program and extract both properties
  * or call `de.lmu.ifi.dbs.jfeaturelib.utils.Extractor --unpack-properties` which unpacks both files into the current exection directory


# Demo code #
Some demo code can be found either in the test cases or in the demo-repository that can be found at
  * https://code.google.com/p/jfeaturelib/source/browse/?repo=demo
  * https://github.com/locked-fg/JFeatureLib-Demo (mirror of the above)