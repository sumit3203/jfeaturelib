#Motivation and background information of JFeatureLib

# Motivation #
## Development efficiency ##
During my diploma thesis, I read about a lot of features descriptors and implemented some of them on my own. Later in my PhD thesis I read (and implemented) even more descriptors - or students of mine implemented yet other descriptors. While you gain quite some knowledge on reimplementing - it also consumes valuable time and you can NEVER be sure if the reimplementation is really the same as the published paper due to lack of test data and the lack of source code.

Even though a lot of descriptors are either well known or published and well cited - sample source code or binaries are rarely available ([SIFT](http://www.cs.ubc.ca/~lowe/keypoints/) is a great counterexample). This is a bit absurd in computer science as sharing code is not an ultimate problem.

## Repeatability ##
Another issue is that even if you are a top coder, you can never be sure that your code is correct just by having read a paper. This is usually due to the lack of given details in the papers. Contacting an author is an option - but you hardly ever get helpful replys.
If you do not have access to both, the image data and the extracted features (which is the usual case), the re-implementation always remains in a _might be correct_ state.

# Audience #
  * **Developers** incorporating feature extraction in their similarity search ([Development FAQ](http://code.google.com/p/jfeaturelib/wiki/DevelopmentFAQ))
  * **Computer vision scientists**, to
    * provide repeatability of their descriptors (proof)
    * provide an easy to use implementation so that others can compare their approaches (easier citations!)
  * **Machine learning scientists** who have image data but need features and do not want or do not have the time to reimplement all on their own