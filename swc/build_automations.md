#Build Automations

##CRISP Builds
* **Complete**
* **Repeatable**
* **Informative**
* **Schedulable**
* **Portable** 
  - machine-independent
  
##POM
Contains all information to generate output from source:


<project>




* **validate** check if project is valid and all necessary information is
* **process-resources** convert and filter resource files
* **compile** compile source code
* **test-compile** compile test code
* **test** execute tests


 |- /src
 |	|	|- /java
 |		|- /java
 |- /target
 |- pom.xml
 
##Plugin
```xml
   <build>