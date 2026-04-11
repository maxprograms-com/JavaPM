# JavaPM

![JavaPM icon](images/JavaPM_90_rounded.png)

## Java Properties Manager

JavaPM is a set of scripts for localizing Java projects using XLIFF as an intermediate format.

JavaPM scans a source folder for all Java resource bundles and converts all source .properties files into a single XLIFF file.

After translating an XLIFF file created by JavaPM, import it to generate the .properties files corresponding to the target language.

## Binary downloads

You can download compressed binary packages for Windows, macOS and Linux from [https://maxprograms.com/products/javapm.html](https://maxprograms.com/products/javapm.html).

## Convert .properties to XLIFF

Running `.\createxliff.cmd` or `./createxliff.sh` without parameters displays help for XLIFF generation.

```text
Usage:

    createxliff.sh [-help] -src sourceFolder -xliff xliffFile -srcLang sourceLanguage [-enc characterSet] 
    [-tgtLang targetLanguage] [-reuse] [-2.0] [-2.0] [-2.2]

Where:

   -help:      (optional) display this help information and exit
   -src:       source code folder
   -xliff:     XLIFF file to generate
   -srcLang:   source language code
   -enc:       (optional) character set code for .properties files; default: ISO-8859-1
   -tgtLang:   (optional) target language code
   -reuse:     (optional) reuse existing translations
   -2.0:       (optional) generate XLIFF 2.0
   -2.1:       (optional) generate XLIFF 2.1
   -2.2:       (optional) generate XLIFF 2.2
```

## Import translated XLIFF

Running `.\mergexliff.cmd` or `./mergexliff.sh` without parameters displays help for importing translated XLIFF files.

```text
Usage:

    mergexliff.sh [-help] -src sourceFolder -xliff xliffFile

Where:

    -help:       (optional) display this help information and exit
    -src:        source code folder
    -xliff:      XLIFF file to merge
    -unapproved: (optional) accept translations from unapproved segments
    -export:     (optional) generate TMX file from approved segments
```

## Build Requirements

- JDK 21 is required for compiling and building. Get it from [https://adoptium.net/](https://adoptium.net/).
- Gradle 9.0. Get it from [https://gradle.org/install/](https://gradle.org/install/).

Pre-built binaries already include everything you need to run all options.

## Building

- Checkout this repository.
- Point your JAVA_HOME variable to JDK 21
- Run `gradle` to generate a binary distribution in `./dist`

### Steps for building

``` bash
  git clone https://github.com/rmraya/JavaPM.git
  cd JavaPM
  gradle
```

A binary distribution will be created in `/dist` folder.
