#Build Automations

##CRISP Builds
* **Complete**  - recipe lists all ingredients
* **Repeatable**  - version control time machine
* **Informative**  - radiate valuable information
* **Schedulable**  - complete and repeatable
* **Portable** 
  - machine-independent
  
##POM
Contains all information to generate output from source:
* **General** Information: URL, organization, developers, license, packaging, source code management (SCM)* **Project Coordinates**: groupId, artifactId, version* **Dependencies**: required libraries to build (and run) the artifact,* **Build Settings**: customization of the build process* **Properties**: project specific property values* **Profile**: build variants* **Reporting**: project documentation
```xml
<project>  <modelVersion>4.0.0</modelVersion>  <groupId>ch.fhnw.imvs</groupId>  <artifactId>myapp</artifactId>  <version>1.0-SNAPSHOT</version>  <packaging>jar</packaging>  <name>My First App</name>  <url>http://maven.apache.org</url></project>```