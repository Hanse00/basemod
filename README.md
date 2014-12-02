# BaseMod

BaseMod is a project to ease the process of creating a new Minecraft mod, with the ForgeGradle system.

## Prerequisites

The use of ForgeGradle requires the [Java Development Kit](http://www.oracle.com/technetwork/java/javase/downloads/index.html) to be installed.

## Using the project

Using BaseMod to set up your own ForgeGradle project, is done in the following steps

1. [Copy](#copy)
2. [Edit build.gradle](#buildgradle)
3. [Edit gradle.properties](#gradleproperties)
4. [Generate project](#generate-project)
5. [Code](#code)
6. [Build](#build)
7. [Running Minecraft](#running-minecraft)

## Steps
### Copy

Copying the repository can be done in two ways:

* Follow the GitHub instructions for [duplicating a repository](https://help.github.com/articles/duplicating-a-repository/).  
You can then download, and use this repository as your working directory.

* Click `Download ZIP` in the right side of the repository page, to download a zipped version of this repository.  
This can then be unzipped to a working directory, and be used as the base for your mod.

### build.gradle

This file contains the configuration for gradle to build and package the mod to a jar file.
The whole file is written in groovy, a programming lanaguage, so practically anything is possible in this file.

First read the build.gradle and try to understand it. If you cannot, don't worry: all of the hard work is done for you.

Edit the build.gradle file to fit the needs for your mod.
In most cases this only requires the change of the `group` and  `archivesBaseName` variables.

For more specialized mods, you may need to refer to ForgeGradle documentation.

### gradle.properties

This file sets out some variables which are accessible in the `build.gradle` script such as `mcversion` and `mcversion`.
The reason they are stored in this file is because they tend to change much more often than the other items in `build.gradle`.

You should edit these variables to fit the needs of your mod.

### Generate project

#### Generate workspace

**Note:** You can run the following commands without the `w` at the end if you already have gradle installed.  
Add `./` to the front of the command on OSX and *NIX systems. For example: `./gradlew` instead of `gradlew`

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


### Code

You should now be ready to code your mod!

### Build

To build the mod, run the command:

```
gradlew build
```

This will place the compiled jar files inside the `<project directory>/build/libs` directory.

The `-sources.jar` file contains the source code for the mod.
The `-deobf.jar` file contains the deobfuscated code which is useful to other developers.
The `.jar` file without a specifier is the file that should be installed by others.

If this is not the first time you are building the mod, or you experience that any files are not correctly updated, you may want to run the clean command, such as:

```
gradlew clean
```

This can also be chained as:

```
gradlew clean build
```

### Running Minecraft

If you want to run minecraft to test the mod, you can use either the run commands in your IDE (reccomended) or use gradle.

To run the client using gradle:

```
gradlew runClient
```

To run the server using gradle:

```
gradlew runServer
```
