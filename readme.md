# ⚡︎ BoxLang Module: MyLambdaProject

```
|:------------------------------------------------------:|
| ⚡︎ B o x L a n g ⚡︎
| Dynamic : Modular : Productive
|:------------------------------------------------------:|
```

<blockquote>
	Copyright Since 2023 by Ortus Solutions, Corp
	<br>
	<a href="https://www.boxlang.io">www.boxlang.io</a> |
	<a href="https://www.ortussolutions.com">www.ortussolutions.com</a>
</blockquote>

<p>&nbsp;</p>

This template allows you to build BoxLang Lambda projects that you can deploy to AWS Lambdas.  This template leverages CommandBox and Gradle for the build process and dependencies.  If your lambda leverages Java libraries, then add them to the `build.gradle` file.  If your lambda leverages BoxLang libraries, then add them to the `box.json` file.

The main lambda code is located in the `src/main/bx/Lambda.bx` folder and the test code is located in the `src/test/java/com/myproject` folder.

## Directory Structure

Here is a brief overview of the directory structure:

* `build` - This is a temporary non-sourced folder that contains the build assets for the module that gradle produces
* `gradle` - The gradle wrapper and configuration, goes into source control don't remove
* `src` - Where your module source code lives
* `workbench` - The workbench for your module including several Lambda resources
* `.cfformat.json` - A CFFormat using the Ortus Standards
* `.editorconfig` - Smooth consistency between editors
* `.gitattributes` - Git attributes
* `.gitignore` - Basic ignores. Modify as needed.
* `.markdownlint.json` - A linting file for markdown docs
* `.ortus-java-style.xml` - Ortus Java Style for IntelliJ, VScode, Eclipse.
* `box.json` - The box.json for your dependencies or if you want to publish to ForgeBox
* `build.gradle` - The gradle build file for the project.
* `changelog.md` - A nice changelog tracking file
* `gradlew` - The gradle wrapper, don't remove
* `gradlew.bat` - The gradle wrapper for windows, don't remove
* `settings.gradle` - The gradle settings file

### Source Directory

Here is a brief overview of the `src` directory structure:

* `main` - Gradle source set for main code
  * `bx` - The BoxLang source code
    * `Lambda.bx` - Your lambda code to deploy
    * Any other BoxLang code you need
* `test`
  * `java` - Java test code for the lambda just like if you were running it in AWS
   	* `com` - Your package
   	  * `myproject` - Your project package
        * `LambdaRunnerTest.java` - Your test code for the lambda
  * `resources` - Resources for testing
    * `libs` - BoxLang binary goes here for now.

## Project Properties

The project name is defined in the `settings.gradle` file.  You can change it there.
The project version, BoxLang Version and JDK version is defined in the `build.gradle` file.  You can change it there.

## Gradle Tasks

Before you get started, you need to run the `downloadBoxLang` task in order to download the latest BoxLang binary until we publish to Maven.

```bash
gradle downloadBoxLang
```

This will store the binary under `/src/test/resources/libs` for you to use in your tests and compiler.  Then you can create your Lambda.  Once you are ready you can run the following to create the final zip to deploy to AWS.

```bash
gradle build
```

This will create a `build/distributions` folder with the final zip file to deploy to AWS.

### Basic Tasks

Here are some basic tasks

| Task                | Description                                                                                                        	|
|---------------------|---------------------------------------------------------------------------------------------------------------------|
| `build`             | The default lifecycle task that triggers the build process, including tasks like `clean`, `assemble`, and others. 	|
| `clean`             | Deletes the `build` folders. It helps ensure a clean build by removing any previously generated artifacts.			|
| `compileJava`       | Compiles Java source code files located in the `src/main/java` directory											|
| `compileTestJava`   | Compiles Java test source code files located in the `src/test/java` directory										|
| `dependencyUpdates` | Checks for updated versions of all dependencies															 			|
| `downloadBoxLang`   | Downloads the latest BoxLang binary for testing																		|
| `jar`               | Packages your project's compiled classes and resources into a JAR file `build/libs` folder							|
| `javadoc`           | Generates the Javadocs for your project and places them in the `build/docs/javadoc` folder							|
| `serviceLoader`     | Generates the ServiceLoader file for your project																	|
| `spotlessApply`     | Runs the Spotless plugin to format the code																			|
| `spotlessCheck`     | Runs the Spotless plugin to check the formatting of the code														|
| `tasks`			  | Show all the available tasks in the project																			|
| `test`              | Executes the unit tests in your project and produces the reports in the `build/reports/tests` folder				|

## Tests

Please use the `src/test` folder for your unit tests.  You can either test using TestBox o JUnit if it's Java.

## Ortus Sponsors

BoxLang is a professional open-source project and it is completely funded by the [community](https://patreon.com/ortussolutions) and [Ortus Solutions, Corp](https://www.ortussolutions.com).  Ortus Patreons get many benefits like a cfcasts account, a FORGEBOX Pro account and so much more.  If you are interested in becoming a sponsor, please visit our patronage page: [https://patreon.com/ortussolutions](https://patreon.com/ortussolutions)

### THE DAILY BREAD

 > "I am the way, and the truth, and the life; no one comes to the Father, but by me (JESUS)" Jn 14:1-12
