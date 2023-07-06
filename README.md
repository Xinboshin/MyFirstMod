# Workspace Setup: Standalone 1.12.2

Basic setup for Forge-based mod development workspace. Essentially serves as ennobled version of last official setup provided by Forge itself (can be found [here](https://maven.minecraftforge.net/net/minecraftforge/forge/1.12.2-14.23.5.2855/forge-1.12.2-14.23.5.2855-mdk.zip)). Has a couple features that original setup does not:

## Building Features:

- Gradle wrapper 4.9 is used by default;
- Custom ForgeGradle 2.3 fork is used ([this one](https://github.com/juanmuscaria/ForgeGradle/tree/FG_2.3)). Though ForgeGradle 3.+ does partially support 1.12.2 projects already, it does not have `GradleStart` wrapper, which in 1.12.2 and below is relied upon for discovering coremods on the classpath. Without it coremods and tweakers are effectively unable to load in development environment, which is a critical issue for a lot of projects;
- Brought back `eclipse` folder with its embedded workspace shenanigans and integrated launch configurations;
- Enforced UTF-8 encoding for all files;
- Buildscript contains tasks for generating `dev` and `sources` artifacts for your mod, as well as ensures they will be generated alongside main jar when executing `gradlew build`;
- All data in `mcmod.info` file is filled when actually building a mod. This illustrates both how to inflate text files upon building and how to use `gradle.properties` file for declaring custom properties used by `build.gradle`;
- Illustration of how to add another mod to project dependencies, in a form of local file.
