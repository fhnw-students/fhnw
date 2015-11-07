#Unit Testing

##Why
**YOU** have to show, that your software does what it is expected to do – correctly!

##What
Testing is the process of evaluating a software to determine if it meets the customers’ requirements.

1. Testing is comparing actual results to expected results2. Testing must produce actual results repeatedly, reliably and reproducibly

##Terms
**Validation**: The process of evaluating software at the end of software development to ensure compliance with intended usage- Did you build the right thing?
**Verification**: The process of determining whether the products of a given phase of the software development process fulfill the requirements established during the previous phase- Did you build it right?
**IMPORTANT**
*Testing can only show the presence of a defect but not the absence of defects!*
##Fault, Errors, Failure
* **Software Fault**: A static defect in the software = the actual "mistake" or "bug" in the code* **Software Error**: An incorrect internal state that is the manifestation of some fault (infection)* **Software Failure**: External, incorrect behavior with respect to the requirements or other description of the expected behavior
##Regression Testing
* How do you ensure, that	* your refactored code still does what it did before?	* a fixed bug never shows up again? (or you notice it immediately, at least)* You rerun existing tests on the changed code to assure	* no new bugs have been introduced 	* a bug has been fixed
	##Unit Testing
Unit Testing is done
* on each unit (usually class, sometimes method) * in isolation* to verify the unit’s behavior
Unit test will
* establish an artificial environment (called test harness) * invoke routines in the unit under test* check the results against expected values
###JUNITA test class is responsible for testing a unit
* Therefore, usually one test class is responsible for testing a single class* A test class is a normal Java class. It can have fields, methods, constructors, inner classes...* If the test class is declared in the same package as the class under test, then it can access its default and protected methods!* Usually a class that tests another class X is declared as:####Test MethodA unit test class consists of several test methods* Test methods take no arguments and return nothing, i.e. a test method is void* Each test method should be completely independent of any other test method* Often each test method tests a single method of the class under test. IDEs such as Eclipse support this pattern.* A test method must be public and is marked with the @Test annotation.* Usually a test method testing a method Y is declared:
```java
@Testpublic void testY() {	... }```
####Set UpIn order to prepare each test, a setup method is calledbefore each test method* In the setup method the test harness is initialized.* The existence of a setup method guarantees, that each test method starts with exactly the same environment.* A setup method must be public and is marked with the @Before annotation* Usually the setup method is declared:```java
@Beforepublic void setup() {	... }```
####Tear DownAfter each test method, a tear down method is called. 
* The tear down method allows to tidy up the “mess” that wasproduced during the test method.* The existence of teardown methods guarantees that the outcome of each test method can be cleaned up.* A teardown method must be public an is marked with the @After annotation* Usually the teardown method is declared:```java
@Afterpublic void teardown() {	... }
```

####Assertions
 assertEquals(<Type> expected, <Type> actual)  Compares primitive types by value Compares class types by calling equals Overloaded with all primitive types, Object and String. assertSame(Object expected, Object actual)  Compares references using ==-operator assertNull(Object x), assertTrue(boolean b)  Does what it says :-) fail() Unconditional failure of test