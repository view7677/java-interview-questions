## Maven


#### 772. What is Maven?

Apache Maven is a software project management and comprehension tool. Based on the concept of a project object model (POM), Maven can manage a project's build, reporting and documentation from a central piece of information.

#### 773. What are the main features of Maven?

Some of the main features of Maven are:

1. **Simple**: Maven provides simple project setup that is based on best practices.
2. **Fast**: You can get a new project or module started in a few seconds in Maven.
3. **Easy** to learn: Maven usage and commands are easy to learn across all projects.Therefore ramp up time for new developers coming onto a project is very less.
4. **Dependency management**: Maven provides superior dependency management including automatic updates and transitive dependencies.
5. **Multiple Projects**: You can easily work with multiple projects at the same time by using Maven.
6. **Large Library**: Maven has a large and growing repository of libraries and metadata to use out of the box.
7. **Extensible**: Maven supports the ability to easily write plugins in Java or scripting languages for extending its core functionality.
8. **Instant**: Maven is online and it provides instant access to new features with very less configuration.

#### 774. What areas of a Project can you manage by using Maven?

Maven can help us manage following areas of a project:

1. Build
2. Testing
3. Release
4. Reporting
5. Software Change Management (SCM)
6. Documentation
7. Distribution

#### 775. What are the main advantages of Maven?

Maven has a long list of advantages for Software development. Some of the main advantages are:

1. **Common Project Structure**: By using Maven, every developer has a common project structure that helps in understanding the code as well as developing new features in a new project.
2. **Modular Design**: Maven promotes modular design that divides a complex project into multiple modules that are easier to manage. By using Maven, it is easier to manage multiple modules for build, test, release etc.
3. **Centralized Dependency Management**: With Maven, each developer does not have to include the jars separately in each project or module. Maven provides a centralized dependency management that can help improve efficiency of software development.
4. **Fewer Decisions**: With Maven a developer has to make fewer decisions about things unrelated to software development work. The project structure comes ready with Maven, dependency management is a uniform approach and build/release are handled by Maven. So a developer can focus on core work of developing software.

#### 776. Why do we say “Maven uses convention over configuration”?

Convention over configuration is a Software Design Paradigm that decreases the number of decisions made by a software developer, without losing flexibility.

In Maven, there are many conventions for setting up the project, building the artifacts, running unit tests and releasing the code. These conventions lead to common process for Software development.

In case of other tools, there are a lot of configuration options are present. But most of the time, a developer uses same set of configuration options. So it is better to make these as a default options. Maven uses default options from best practices and provides right conventions for Software development.

#### 777. What are the responsibilities of a Build tool like Maven?

1. **Source Code**: A Build tool can generate source code based on templates.
2. **Documentation**: We can get documentation files from source code by using a build tool. E.g. Javadoc
3. **Compilation**: Primary responsibility of a Build tool is to compile source code into executable code.
4. **Packaging**: A Build tool packages compiled code into a deployable file like- jar, zip war etc.
5. **Deployment**: We can deploy the packaged code on server by using a Build tool.

#### 778. What are the differences between Ant and Maven?

Key differences between Ant and Maven are:

| Ant                                                                         | Maven                                                                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| Ant is a Java library and command line toolbox for build process            | Maven is a framework for many aspects of software development like- project setup, compile, build, documentation etc. |
| Ant does not have any conventions for project structure or build processes. | Maven has conventions for setting up project structure as well as for build processes.                                |
|Ant does not have any conventions for project structure or build processes. | Maven has conventions for setting up project structure as well as for build processes.|
|Ant is based on procedural programming. We have to write code for compilation build, copy etc. |Maven is based on declarative programming. We have to just configure it for our project setup and programming.|
|Ant does not impose any lifecycle. We need to create the sequence of tasks manually. |Maven has a lifecycle for software build processes. There are well-defined phases that we can use in Maven.|
|Ant scripts are not reusable in multiple projects.|Maven has plugins that are reusable across multiple projects.|



#### 779. What is MOJO in Maven?

MOJO stands for **M**aven plain **O**ld **J**ava **O**bject. Every MOJO is an executable goal in Maven. It is like an annotated Java class. It specifies metadata about a goal like- goal name, phase of lifecycle for goal and parameters required by goal. A Maven plugin can contain multiple MOJOs.

#### 780. What is a Repository in Maven?

A repository is a location on file system where build artifacts, jars, dependencies and pom.xml files are stored.

#### 781. What are the different types of repositories in Maven?

There are mainly two types of repositories in Maven:

1. **Local Repository**: This is your local folder in which a copy of your installation and dependencies is stored.
2. **Remote Repository**: This is a remote folder in which jars and other build artifacts are stored. These can be located on servers within your organization.
3. **Central Remote Repository**: This is the central Maven repository that is located on _repo.maven.apache.org_ or _uk.maven.org_ or any other third party location. This where we can find artifacts from different providers that are available for download and use. Like- Hibernate, Spring libraries etc.

#### 782. What is a local repository in Maven?

Maven local repository is a folder in your local files system in which your project’s installation, dependency jars, plugins etc. are stored. Default location of Maven local repository is .m2 folder. It can be located under following location on file system:
1. Windows – `C:\Documents and Settings{ username}.m2` 
2. Unix/Linux/Mac – `~/.m2`

#### 783. What is a central repository in Maven?

Maven central repository is a truly remote repository that is located on _repo.maven.apache.org_ or _uk.maven.org_ or any other third party location.

This contains the jars and artifacts provided by various software providers.

Central repository contains a large amount of data. Therefore it is not allowed to scrape the whole site. But you can use the relevant jars that you want for download and use in your Maven project.

#### 784. What is a Remote repository in Maven?

A Remote repository is a remote location on the internet where the jars and dependencies from different vendors are stored.

These files can be accessed by protocols like- `file://` or `http://` etc.

These can be truly remote repositories set up by third party vendors or locations inside your organization that contains the relevant jars required by your project.

#### 785. Why we should not store jars in CVS or any other version control system instead of Maven repository?

Maven recommends storing jars in local repository instead of CVS or any other version control system. There are following advantages of storing it in Maven repo vs. CVS:

**Less Storage**: A repository is very large, but it takes less space because each JAR is stored only in one place. E.g. If we have 10 modules dependent on Spring jar, then they all refer to same Spring jar stored in local repository.
**Quicker Checkout**: Project checkout is quicker from local repository, since there is not need to checkout jars if they are already present in repo.
**No need for versioning**: There is no need to version JARS since external dependencies do not change so often.

#### 786. Can anyone upload JARS or artifacts to Central Repository?

No, we need special permissions to upload JARS and artifacts to Central Maven Repository?

#### 787. What is a POM?

POM is an abbreviation for Project Object Model. This is the basic unit of work in Maven. It is an XML file with name pom.xml.

It contains details of project and project configuration that are used by Maven to build the project.

It also contains default values for many projects. E.g. target is the name of build directory for Java Maven project.

#### 788. What is Super POM?

Super POM is Maven’s default POM. All the POM files extend from Super POM.

#### 789. What are the main required elements in POM file?

Every POM file should have following required elements:

1. project root
2. modelVersion
3. **groupID**: the id of the project’s group.
4. **artifactID**: the id of the artifact (project)
5. **version**: the version of the artifact under the specified group

#### 790. What are the phases in Build lifecycle in Maven?

In Maven, each build lifecycle consists of many phases. Default build lifecycle has following phases:

1. **validate**: In this phase, Maven validates that the project is correct and all necessary information is available to run next phase.
2. **compile**: Maven compiles the source code of the project in this phase.
3. **test**: This is the phase to run unit tests on the compiled source. There should not be any need to package or deploy the code to run these tests.
4. **package**: In this phase, Maven takes the compiled code and packages it in its distributable format, such as a JAR.
5. **verify**: Maven runs any checks on results of integration tests to ensure that quality criteria are met.
6. **install**: In this phase, Maven installs the package into local repository. After this it can be used as a dependency in other projects locally.
7. **deploy**: In the build environment, Maven copies the final package to the remote repository for sharing with other developers and projects.

#### 791. What command will you use to package your Maven project?

To package a project into a distributable format we use following command: `mvn -package`

#### 792.What is the format of fully qualified artifact name of a Maven project?

A POM requires that its groupId, artifactId, and version be configured. These three values form the project's fully qualified artifact name. This is in the form of `<groupId>:<artifactId>:<version>`. As for the example above, its fully qualified artifact name is "com.mycompany.app:my-app:1".

#### 793. What is an Archetype in Maven?

In short, Archetype is a Maven project templating toolkit. An archetype is defined as _an original pattern or model from which all other things of the same kind are made_. The name fits as we are trying to provide a system that provides a consistent means of generating Maven projects. Archetype will help authors create Maven project templates for users, and provides users with the means to generate parameterized versions of those project templates.

#### 794. What is the command in Maven to generate an Archetype?

To create a new project based on an Archetype, you need to call `mvn archetype:generate` goal

#### 795. What are the three main build lifecycles of Maven?

Maven has following three build lifecycles that further contain multiple phases:

1. **clean**: In this lifecycle any files generated by previous builds are removed.
2. **default**: This lifecycle is used for validating, compiling and creating the application. It has multiple phases like- compile, test, package inside it.
3. **site**: Maven generates and deploys the documentation of a site in this phase.

#### 796. What are the main uses of a Maven plugin?

Maven is mainly a plugin execution framework. At the code of Maven all the work is done by plugins. A Maven plugin can be used for following purposes:

1. Cleaning up the code
2. Compiling the code
3. Creating a JAR file
4. Deploying the artifacts
5. Running the unit tests
6. Documenting the project
7. Generating the site of a project
8. Generating a WAR file
9. Generate a checkstyle report

#### 797. How will you find the version of a plugin being used?

Maven Help Plugin has a describe goal. This can be used for listing the version of a plugin. Sample command for this is: mvn -Dplugin=install help:describe 

Note: In the above command replace Dplugin with the plugin prefix as the argument. Do not use the artifact ID of plugin here.

#### 798. What are the different types of profile in Maven? Where will you define these profiles?

In Maven, we can have following types of Profile: 
1. **Per Project** It is defined in the POM itself (pom.xml). 
2. **Per User** We can define it in the Maven-settings (%USER_HOME%/.m2/settings.xml). 
3. **Global** It is defined in the global Maven-settings (${maven.home}/conf/settings.xml). 
4. **Profile descriptor** Descriptor is located in project basedir (profiles.xml) (It is not supported in Maven 3.0)


#### 799. What are the different setting files in Maven? Where will you find these files?


#### 800. What are the main elements we can find in settings.xml?

In settings.xml we can have all the configuration information for Maven. Some of the important elements are:

1. **localRepository**: The value of this element is the path of this build system’s local repository. The default value is `${user.home}/.m2/repository`.It is used for a main build server to allow all logged-in users to build from a common local repository.
2. **interactiveMode**: If it is true then Maven should attempt to interact with the user for input. If it is false then Maven does not interact with the user. Default setting is true.
3. **usePluginRegistry**: If it is true Maven uses the ${user.home}/.m2/plugin-registry.xml file to manage plugin versions. By defaults it is false.
4. **offline**: If it is true this build system should be able to operate in offline mode. By default it is false. This element is used for build servers that cannot connect to a remote repository due to network setup or security reasons.

#### 801. How will you check the version of Maven in your system?

We can use following command in console to check the version of Maven in our system. `mvn -version`

#### 802. How will you verify if Maven is installed on Windows?

To check this, type `mvn –version` in cmd prompt of Windows. This will give you the version of Maven installed on Windows.

#### 803. What is a Maven artifact?

A Maven artifact is a file that gets deployed to a Maven repository. In most cases it is a JAR file.

When Maven build runs, it creates one or more artifacts. In case of Java projects, it produces a compiled jar and a sources jar.

Every artifact in Maven has a group ID, an artifact ID and a version string. These three attributes uniquely identify an artifact.

In Maven, we specify a project’s dependencies as artifacts.

#### 804. What are the different dependency scopes in Maven?


#### 805. How can we exclude a dependency in Maven?


#### 806. How Maven searches for JAR corresponding to a dependency?


#### 807. What is a transitive dependency in Maven?


#### 808. What are Excluded dependencies in Maven?


#### 809. What are Optional dependencies in Maven?


#### 810. Where will you find the class files after compiling a Maven project successfully?


#### 811. What are the default locations for source, test and build directories in Maven?


#### 812. What is the result of jar:jar goal in Maven?


#### 813. How can we get the debug or error messages from the execution of Maven?


#### 814. What is the difference between a Release version and SNAPSHOT version in Maven?


#### 815. How will you run test classes in Maven?

We need Surefire plugin to run the test classes in Maven. To run a single test we can call following command: `mvn -Dtest=TestCaseA test` 

We can also use patterns to run multiple test cases:` mvn -Dtest=TestCase* test` or `mvn -Dtest=TestCaseA,TestCaseB,TestImportant* test`

#### 816. Sometimes Maven compiles the test classes but doesn't run them? What could be the reason for it?
In Maven, Surefire plugin is used for running the Tests.

We can configure it to run certain test classes. Sometimes we you may have unintentionally specified an incorrect value to ${test} in settings.xml or pom.xml.

We need to look for following in `pom.xml/settings.xml` and fix it:

```xml
<properties>
    <property>
        <name>test</name>
        <value>some-value</value>
    </property>
</properties>
```

#### 817. How can we skip the running of tests in Maven?

We can use the parameter `-Dmaven.test.skip=true` or `-DskipTests=true` in the command line for skipping the tests. The parameter `-Dmaven.test.skip=true` skips the compilation of tests. The parameter `-DskipTests=true` skips the execution of tests Surefire plugin of Maven honors these parameters.

#### 818. Can we create our own directory structure for a project in Maven?

Yes, Maven gives us the flexibility of creating our own directory structure. We just need to configure the elements like `<sourceDirectory>`, `<resources>` etc. in the `<build>` section of `pom.xml`.

#### 819. What are the differences between Gradle and Maven?

Gradle is nowadays getting more popular. Google uses it for Android development and release. Companies like LinkedIn also use Gradle.

Gradle is based on **D**omain **S**pecific **L**anguage (DSL). Maven is based on XML.

Gradle gives more flexibility to do custom tasks similar to ANT. Maven scripts have predefined structure. So it is less flexible.

Maven is mainly used for Java based systems. Gradle is used for a variety of languages. It is a Polyglot build tool.

#### 820. What is the difference between Inheritance and Multi-module in Maven?



#### 821. What is Build portability in Maven?