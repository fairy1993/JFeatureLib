[![DOI](https://zenodo.org/badge/doi/10.5281/zenodo.31793.svg)](http://dx.doi.org/10.5281/zenodo.31793)

JFeatureLib
===========

JFeatureLib is a free library that provides implementations for several kinds of image features 
and also several point/region detectors used mainly in the research field of 
ComputerVision.

[Refer to the Wiki for further information](https://github.com/locked-fg/JFeatureLib/wiki)

Releases can also be found at Maven Central: https://oss.sonatype.org/content/repositories/releases/de/lmu/ifi/dbs/jfeaturelib/JFeatureLib/

The API can be found here: http://jfeaturelib-api.locked.de

Build & Install
======
JFeatureLib's dependencies are all but one in MavenCentral. 
To get LIRE into the maven environment as well and compile JFeatureLib, just use the following commands:
```
git clone https://github.com/locked-fg/LIRE.git
cd LIRE
mvn -Prelease install -DskipTests=true -Dgpg.skip=true -Dmaven.javadoc.skip=true

cd ..
git clone https://github.com/locked-fg/JFeatureLib.git
cd JFeatureLib
mvn clean install 
```

Include JFeatureLib in your program:
```
<dependency>
    <groupId>de.lmu.ifi.dbs.jfeaturelib</groupId>
    <artifactId>JFeatureLib</artifactId>
    <version>1.6.5</version>
    <type>jar</type>
</dependency>
```

Changelog
=======
* 1.6.5
  - raised compiler level to Java 8
  - fixed dependencies
* 1.6.4: 
  - fixed SIFT Wrapper
* 1.6.3:
  - replaced LIRE Dependency with a maven repo
  - extended LocalBinary patterns so that it can hold more than 14 neighbours.
* 1.6.2: 
  - Haralick Bug fixed (Fixes Issue #26)
  - Histogram descriptor crashed with non binary masks
* 1.6.1: 
  - changed the LIRE dependency and added some help how to get LIRE working (Use my fork: https://github.com/locked-fg/LIRE)
  - added numerically stable variance calculation for Haralick (Issue #20). Thanks Erich Schubert
* 1.6.0:
  - added LocalBinaryPatterns, MeanIntensityLocalBinaryPatterns, MeanPatchIntensityHistogram (Pull Request #21).
        Thanks Sebastian Pölsterl.
* 1.5.3:
   - Omit "save file" dialog when using SIFT. Fixes #19. Thanks Johannes Niedermayer
* 1.5.2:
   - Caught all Throwables in Extractor (Pull Request #17). Thanks Sebastian Pölsterl.
   - added quoting of Extractor Output (Pull Request #18). Thanks Sebastian Pölsterl.
* 1.5.1:
   - Fixed an Haralick-Bug (Issue #16). Thanks Sebastian Pölsterl.
   - Provide multi character image classes (Issue #15). Thanks Sebastian Pölsterl.
   - Fixed quite some issues that FindBugs marked.
* 1.5.0:
   - Extractor now also supports output to stdout (Thanks Erich Schubert)
   - Extractor now also supports case insensitive file suffixes
   - added JpegCoefficientsHistogram (from Lire)
   - added basic tests for features
   - added capabilities to SUSAN extractor
   - removed obsolete RGBtoGray
   - extended the Extractor help functionality
   - fixed an invalid API in Kernel
   - fixed LuminanceLayout (typo and wrong implementation)
   - fixed Extractor debugging
* 1.4.1: 
   - fixed Tamura instanciation bug
* 1.4.0: 
   - packaged LIRE directly into the JARs, thanks David Maiserer
   - updated to LIRE 0.9.4-beta (08.July.2013 including custom patch)
   - added LuminanceLayout (from LIRE)
   - added OpponentHistogram (from LIRE)
   - added FuzzyOpponentHistogram (from LIRE)
   - added MPEG7ColorLayout (from LIRE)
   - added MPEG7EdgeHistogram (from LIRE)
   - fixed Threading issue in Histograms, thanks Christian Surer
   - updated dependency to imageJ v1.46
* 1.3.2: 
   - fixed Dependency to Google Guava, thanks Nepomuk Seiler
* 1.3.1: 
   - fixed Issue 29 & 20
   - changed dependency of common-extension-lib (fixes NaNs)
   - Made the jar executable (again)
* 1.3.0: 
   - changed PHOG code according to new common-extension-lib
   - fixed Issue 24: NPE in AutoColorCorrelogram
   - fixed Issue 26: LibProperties
   - fixed Issue 23: added new feature ColorHistogram, ReferenceColorSimilarity
* 1.2.0: 
   - added new feature descriptor AutoColorCorrelogram, thanx LIRE
   - replaced the lire library with the most recent lire version 0.9.3
   - removed the package de.lmu.ifi.dbs.jfeaturelib.features.lire and implemented the according delegates
   - added properties support for lire features
   - added properties support for thumbnail
   - removed deprecated method calls in SURF / removed surf classes that are not needed for extraction
   - Changed ConfigurableDescriptor to AbstractDescriptor
   - added code licencing blocks
   - corrected JavaDocs to get rid of all the warnings
   - changed dependency to common-extension-lib 2.1.0
* 1.1.0: 
   - added SquareModelShapeMatrix and according properties
   - changed de.lmu.ifi.dbs.jfeaturelib.shapeFeatures.Profiles to a new implemenation provided by Johannes Niedermayer
   - made Histogram.TYPE public static
   - added config option for haralick distance
* 1.0.1: 
   - fixed error that properties were not found
   - added possibility to extract jfeaturelib.properties from jar by using the Extractor
   - added possibility to extract logging.properties from jar by using the Extractor
* 1.0.0: 
   - corrected package path from de.lmu.dbs.jfeaturelib to de.lmu.ifi.dbs.jfeaturelib (added ifi)
   - Fixed Issue 19 (possibility to list feature descriptor capabilities in CLI)
   - published to maven https://oss.sonatype.org/content/groups/public/de/lmu/ifi/dbs/jfeaturelib/JFeatureLib/
* 0.4.0: 
   - changed build system to maven, thanks Nepomuk Seiler
   - checked the support values of all feature extractors
   - Fixed Issue 18 (masking support in PHOG)
   - Fixed Issue 17 (masking support in CLI)
   - Made Extractor more convenient and robust
   - Fixed Issue 8 (Canny support)
* 0.3.1: 
   - annoying Logging.properties fix in Extractor
* 0.3.0: 
   - made Canny and PHOG configurable via properties
   - extend properties and PHOG to combine PHOG and Canny
* 0.2.0: 
   - added shape features (special thanks to Johannes Stadler and Johannes Niedermayer)
   - changed completely to log4j
   - fixed buildfile
   - Fixed Issue 14
* 0.1.2: 
   - aggregates GrayHistogram and RGB Histogram in Histogram which also supports 
         separate extraction of R,G,B, HSB, H, S, B Histograms
   - added settings to properties
   - added more convenient way of setting properties even through Extractor
* 0.1.1:
   - introduced Abstract Feature Descriptor
   - fixed bug in Haralick feature (Issue 11)
* 0.1.0: init
