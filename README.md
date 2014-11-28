# BaseMod

BaseMod is a project to ease the process of creating a new Minecraft mod, with the ForgeGradle system.

## Prerequisites

The use of ForgeGradle requires the [Java Development Kit](http://www.oracle.com/technetwork/java/javase/downloads/index.html) to be installed.

## Using the project

Using BaseMod to set up your own ForgeGradle project, is done in the following steps

1. [Copy](https://github.com/Hanse00/basemod#copy)
1. [Edit build.gradle](https://github.com/Hanse00/basemod#buildgradle)
1. [Generate project](https://github.com/Hanse00/basemod#generate-project)
1. [Code](https://github.com/Hanse00/basemod#code)
1. [Build](https://github.com/Hanse00/basemod#build)

## Steps
### Copy

Copying the repository can be done in two ways:

* Follow the GitHub instructions for [duplicating a repository](https://help.github.com/articles/duplicating-a-repository/).  
You can then download, and use this repository as your working directory.

* Click `Download ZIP` in the right side of the repository page, to download a zipped version of this repository.  
This can then be unzipped to a working directory, and be used as the base for your mod.

### Build.gradle

Edit the build.gradle file to fit the needs for your mod.

In most cases this only requires the change of the `version`, `group`, `archivesBaseName`, and possibly `minecraft version` variables.

For more specialized mods, you may need to refer to ForgeGradle documentation.

### Generate project

#### Generate workspace

To generate the Forge workspace which is used to code in, you will need to run one of the following commands:

```
gradlew setupDevWorkspace
```

Sets up the workspace without decompiling the Minecraft class files, allowing you to compile and run your mod, but not see the Minecraft sources.

```
gradlew setupDecompWorkspace
```

Sets up the workspace, and decompiles Minecraft, allowing you to refer to the decompiled Minecraft sources as you code.

#### Generate project files

To generate the project used by IntelliJ IDEA or Eclipse use one of these commands:

```
gradlew idea
```

```
gradlew eclipse
```

These commands can be run at once, such as:

```
gradlew setupDecompWorkspace idea
```

**Note:** You can run the commands without the `w` at the end if you already have gradle installed.  
Add `./` to the front of the command on OSX and *NIX systems.

### Code

You should now be ready to code your mod!

### Build

To build the mod, run the command:

```
gradlew build
```

This will place the compiled jar file inside the `<project directory>/build/libs` directory.

If this is not the first time you are building the mod, or you experience that any files are not correctly updated, you may want to run the clean command, such as:

```
gradlew clean
```

This can also be chained as:

```
gradlew clean build
```
