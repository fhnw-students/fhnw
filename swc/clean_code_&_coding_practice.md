#Clean Code & Coding Practice

##Why
* 80% of the lifetime cost of a piece of software goes to maintenance.* Code is written once, but read all other times* Hardly any software is maintained for itswhole life by the original author.* Cleancodeimprovesthereadabilityofthesoftware, allowing engineers to understandnew code more quickly and thoroughly.
##What
Clean code is **simple** and direct. Clean code reads like well-written prose. Clean code never obscures the designer’s intent but rather is full of **crisp** abstractions and **straightforward** lines of control.
1. Clean (Meaningful) Names
```java
int elapsedTimeInDays;int daysSinceCreation;int daysSinceModification;
```
2. Clean Formatting
3. Avoid negative conditionals
4. Clean Formatting
5. Check Brackets

##Horizontal Openness and Density
* Keep lines short.	* Better 80 characters than more* Don’t try to horizontally align lists of assignments	* it draws attention to the wrong thing and can be misleading, e.g., encouraging the reader to read down a column.* Always indent scopes (classes, methods, blocks).

##Team Rules
* Every team should agree on a coding standard
* Beware of code formatting standards getting religious.

##Code conventions usually cover:* filenames, file organization* formatting like indentation, white spaces, line breaks * naming conventions* declarations, statements* comments* and of course: programming practices

##JavaDoc
###Rules For Writing Summaries
 For methods, omit the subject and write in the third-person narrative form
 * Good: Fin**ds** the first blank in the string.* Not as good: Find the first blank in the string.* Bad: This method finds the first blank in the string.* Worse: Method findBlank(String s) finds the first blank in the string.
Use the standard ordering for javadoc tags  In method descriptions, use:
```￼@param p		A description of parameter p.
@return			A description of the value returned (unless the method returns void).
@exception e	Describe any thrown exception.
@see			Adds a "See Also" heading with a link or text entry that points to reference```
In class and interface descriptions, you may use:
```@author your name
@version a version number or date```
#Know Where To Put Comments!* javadoc comments must be immediately before: * a package (only in package-info.java)* a class* an interface* a constructor * a method * a field