# Infobip API Java Demo Application
Simple desktop application written in Java, illustrating integration with Infobip's SMS API. All of the documentation
 of the API methods used in this app can be found at [dev.infobip.com](https://dev.infobip.com/).

## Requirements
* Java version 8 or later. You can find JDK at 
[Oracle downloads pages](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
* Maven version 3. You can find download instructions at 
[Maven Project downloads page](http://maven.apache.org/download.cgi) and for installation instructions take a look at
 [installation guide](http://maven.apache.org/install.html)
* Git, which if you do not already have you can find at [git downloads page](https://git-scm.com/downloads)

To check if you have all the requirements installed you can check for their versions.
To do that on a Windows run Command Prompt (you can easily do that by pressing `WinKey+R` to open a Run window, 
typing `cmd` in the input text field and pressing `Enter`). With the terminal running you can check for the versions 
of programs installed and configured on your computer.

To check your version of Java execute:
```
java -version
```
The result should look something like this:
```
java version "1.8.0_31"
Java(TM) SE Runtime Environment (build 1.8.0_31-b13)
Java HotSpot(TM) 64-Bit Server VM (build 25.31-b07, mixed mode)
```

To check your version of Maven execute:
```
mvn --version
```
The result should look something like this:
```
Apache Maven 3.3.9 (bb52d8502b132ec0a5a3f4c09453c07478323dc5; 2015-11-10T17:41:47+01:00)
Maven home: C:\mvn\apache-maven-3.3.9\bin\..
Java version: 1.8.0_25, vendor: Oracle Corporation
Java home: C:\Program Files\Java\jdk1.8.0_25\jre
Default locale: en_US, platform encoding: Cp1250
OS name: "windows 8.1", version: "6.3", arch: "amd64", family: "dos"
```
To check your version of Git execute:
```
git --version
```
The result should look something like this:
```
git version 2.9.3.windows.1
```

## Building the app
The first step is downloading the source code to your computer. To achieve this you can either download a ZIP archive from 
this GitHub page and unzip it, or use `Git` to clone the repository. To clone it using Git open your terminal, position 
yourself in the directory that you want the project to be downloaded to and execute `git clone` command. It should look 
like this:
```
C:\>git clone https://github.com/infobip/infobip-api-java-demo.git
Cloning into 'infobip-api-java-demo'...
remote: Counting objects: 116, done.
remote: Compressing objects: 100% (63/63), done.
Receiving objects:  55% (64/116)   d 101 (delta 36), pack-reused 0 eceiving objects:  54% (63/116)
Receiving objects: 100% (116/116), 32.81 KiB | 0 bytes/s, done.
Resolving deltas: 100% (51/51), done.
Checking connectivity... done
```
Git has now created a new directory, named `infobip-api-java-demo`, and downloaded the contents of this repo to it.
Position yourself in the newly created directory and verify that the files are there. On Windows it should look like 
this:
```
C:\>cd infobip-api-java-demo
C:\infobip-api-java-demo>dir

 Directory of C:\infobip-api-java-demo

10/14/2016  01:17 PM    <DIR>          .
10/14/2016  01:17 PM    <DIR>          ..
10/14/2016  01:17 PM             2,211 .gitignore
10/14/2016  01:17 PM            11,558 LICENSE
10/14/2016  01:17 PM             2,054 pom.xml
10/14/2016  01:17 PM             1,726 README.md
10/14/2016  01:17 PM    <DIR>          src
               4 File(s)         17,549 bytes
               3 Dir(s)   9,403,285,504 bytes free
```

Now that you have the source code downloaded to your computer, you can build it by executing `mvn install` command in 
`infobip-api-java-demo` directory. This will produce many lines of output code, but the beginning and the end should 
look like this:
```
C:\infobip-api-java-demo>mvn install
[INFO] Scanning for projects...
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] Building Infobip API Java Demo Application 1.0.0
[INFO] ------------------------------------------------------------------------
[INFO]
...
[INFO]
[INFO] --- maven-install-plugin:2.4:install (default-install) @ infobip-api-java-demo ---
[INFO] Installing C:\infobip-api-java-demo\target\DemoApp.jar to C:\.m2\repository\com\infobip\infobip-api-java-demo\1.0.0\infobip-api-java-demo-1.0.0.jar
[INFO] Installing C:\infobip-api-java-demo\pom.xml to C:\.m2\repository\com\infobip\infobip-api-java-demo\1.0
.0\infobip-api-java-demo-1.0.0.pom
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 21.971 s
[INFO] Finished at: 2016-10-14T13:37:01+02:00
[INFO] Final Memory: 17M/187M
[INFO] ------------------------------------------------------------------------

```

A new directory named `target` should now exist in your root project directory. You can enter it and list its contents:
```
C:\infobip-api-java-demo>cd target

C:\infobip-api-java-demo\target>dir

 Directory of C:\infobip-api-java-demo\target

10/14/2016  01:37 PM    <DIR>          .
10/14/2016  01:37 PM    <DIR>          ..
10/14/2016  01:36 PM    <DIR>          archive-tmp
10/14/2016  01:36 PM    <DIR>          classes
10/14/2016  01:37 PM           854,674 DemoApp.jar
10/14/2016  01:36 PM    <DIR>          generated-sources
10/14/2016  01:36 PM            49,532 infobip-api-java-demo-1.0.0.jar
10/14/2016  01:36 PM    <DIR>          maven-archiver
10/14/2016  01:36 PM    <DIR>          maven-status
               2 File(s)        904,206 bytes
               7 Dir(s)   9,403,604,992 bytes free
```
Note the file named `DemoApp.jar`. You can use it to run the application.

## Running the app
To run the installed application position yourself in the `target` directory within your root project directory. If 
you were following previous steps you should already be positioned appropriately. From there simply run the app using
 `java -jar` command:
```
C:\infobip-api-java-demo\target>java -jar DemoApp.jar
```
That should start the app and present you with the log in screen. There you can enter your Infobip account 
credentials and start playing around with sending SMSes and reviewing logs and delivery reports.

## Used technologies

The application is a simple desktop program written in Java. For communicating with the Infobip APIs the application uses Infobip’s [java API client library](https://github.com/infobip/infobip-api-java-client). Core business logic is implemented in the adapter classes, e.g. `SendSmsAdapter.java`. Check out those classes to find out how best to use the API client. Along with the code itself, there are abundant comments and documentation for clarifying every part of the implementation as well as the behavior of the API client library.

The user interface is implemented using the [JavaFX](https://en.wikipedia.org/wiki/JavaFX) framework that comes bundled with the Java version 8. The interface itself is kept basic and the code related to the JavaFX is separated neatly into user interface packages.

> Note that there are other online sources for documentation and examples on how to architect applications based on [JavaFX](http://docs.oracle.com/javafx/2/get_started/jfxpub-get_started.htm) and this demo app does not try to instruct you on that subject. Nevertheless, it does use a clean approach in its setup and can be used as a starting point for your own project.

## Basic code structure

The application code itself is structured in [per feature packages](http://www.javapractices.com/topic/TopicAction.do?Id=205). That means that all of the code related to, for example, sending of SMS is grouped in a package called `send`. Therein you can find before mentioned `SendSmsAdapter.java` class that implements calls to the Infobip API client library, along with a [POJO](https://en.wikipedia.org/wiki/Plain_Old_Java_Object) (Plain Old Java Object) class used to represent the SMS message in the demo application and an exception class used to indicate problem encountered while sending messages.

Additionally, send package has a UI (user interface) package inside of it that holds classes implementing parts of the JavaFX framework needed to render the send SMS form and handle user input. You’ll find a similar structure in the other top-level packages, namely `log` and `report`.

A package named `common` houses interfaces and abstract classes used throughout the rest of the application. `SmsApplication.java` is the starting point of the application and implements Java’s main method as well as the JavaFX setup.