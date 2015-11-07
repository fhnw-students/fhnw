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
**Mandatory**:* groupId:theorganizationidentifiersuchastheDNSname:ch.fhnw.imvs* artifactId: the name of the product: myapp* version: the release identifier: 3.1.2 (major.minor.incremental)* packaging:thetypeofpackaging(jar,ear,war...)
**Optional**:
* name: the project name* url:theproject’swebpage
##The Standard Build Process
* **validate** check if project is valid and all necessary information is
* **process-resources** convert and filter resource files
* **compile** compile source code
* **test-compile** compile test code
* **test** execute tests* **package** package the artifact* **integration-test** execute integration tests* **install** copy artifact into the local repository* **deploy** publish artifact in the remote repository
##Directory Structure
```project home |
 |- /src |	|- /main
 |	|	|- /java |	|	|- /resources |  | |	|- /test
 |		|- /java |		|- /resources |
 |- /target
 |- pom.xml
```
 
##Plugin
```xml
   <build>     <plugins>       <plugin>         <artifactId>maven-compiler-plugin</artifactId>         <version>3.2</version>         <configuration>           <source>1.7</source>           <target>1.7</target>         </configuration>       </plugin>     </plugins></build>``` 