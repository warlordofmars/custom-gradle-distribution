# warlordofmars-gradle

![current release](https://img.shields.io/github/release/warlordofmars/warlordofmars-gradle.svg?style=flat)

## Overview

Custom Gradle distribution for warlordofmars projects to apply some sane defaults in order to avoid duplication.

## Features

### Default Group

This gradle distribution will set the default `group` for all projects that use it.  This is so that the group does not have to always be defined in every project's `build.gradle`:

```gradle
group = 'com.github.warlordofmars'
```

### Default Repositories

Similiarly, to keep from having to define multiple maven repositories in each project, a number of default repositories (as well as buildscript repositories):

```gradle
buildscript {
    repositories {
        mavenLocal()
        mavenCentral()
        jcenter()
        maven {
            url "https://jitpack.io"
        }
        maven {
            url "https://plugins.gradle.org/m2/"
        }
    }
}

repositories {
    mavenLocal()
    mavenCentral()
    jcenter()
    maven {
        url "https://jitpack.io"
    }
    maven {
        url "https://plugins.gradle.org/m2/"
}
```

## How to Use

### Existing Gradle Project

In order to update an existing project to use this custom gradle distribution, run the following command from within the project directory:

```bash
./gradlew wrapper --gradle-distribution-url=https://github.com/warlordofmars/warlordofmars-gradle/releases/download/release-0.1.1/warlordofmars-gradle-5.2.1-0.1.1-bin.zip
```

### New Gradle Project

For a new Gradle project, first `init` the project:

```bash
gradle init
```

Then update the wrapper in the same way as described above:

```bash
./gradlew wrapper --gradle-distribution-url=https://github.com/warlordofmars/warlordofmars-gradle/releases/download/release-0.1.1/warlordofmars-gradle-5.2.1-0.1.1-bin.zip
```

## Author

* **John Carter** - [warlordofmars](https://github.com/warlordofmars)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowlegements

* Based off of [gradle-custom-distribution](https://github.com/bmuschko/gradle-custom-distribution) from [bmuschko](https://github.com/bmuschko)
* Using the [warlordofmars](https://github.com/warlordofmars) gradle plugin, [gradle-release-helper](https://github.com/warlordofmars/gradle-release-helper), for automatic versioning, git tagging, and publishing of releases to GitHub
