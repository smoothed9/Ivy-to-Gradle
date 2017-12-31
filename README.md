# Ivy-to-Gradle
<H1>Code to convert Ivy files to Gradle</H1>

<B>Background:</B>

Apache Ivy is a Dependency Management framework. Combining it with Apache Ant gives a complete Build and Dependency Management system. 

Ivy has it’s own Pros and Cons. Ironically, one of the main Pro and Con is Ant. Ant adds a lot of flexibility to the system. You can write any custom task in Ant.  
But the same strengths also contribute to it’s weakness. Ant is written in XML. As your system grows, so does the build script. It becomes very tedious to manage large Ant XMLs. 

When Gradle was started, they used Ivy as the dependency management. But later, they started developing own solution. Gradle takes the best features of both Ivy and Maven. It has grown in popularity in recent years. Gradle supports Groovy and off late, Kotlin to write custom scripts. 

When you are working to convert Ivy projects to Gradle, it soon becomes time consuming. Since the structure of Ivy and Gradle files are different, rewriting each dependency or artifacts manually could become error prone. 

<B>Solution:</B>

In this post, I’ll be covering a simple Groovy script to convert an Ivy file into a Gradle script. You just have to keep this in the same folder as the existing Ivy file and execute it. The script will create a Gradle file, execute the “wrapper” task and delete the Ivy file. You can customize this further to delete any Ant files or modify the .project file to add/remove Ivy/Gradle natures.

The command to execute this file is 
<I>gradle -b IvyToGradle.gradle executeIvyToGradle</U></I>

We have to use -b parameter as the script was written in a custom file. By default, Gradle executes only the build.xml. If -b is not given, it'll throw an error as there is no build.gradle file in this project. 
