#Unit Testing

##Why
**YOU** have to show, that your software does what it is expected to do – correctly!

##What
Testing is the process of evaluating a software to determine if it meets the customers’ requirements.

1. Testing is comparing actual results to expected results2. Testing must produce actual results repeatedly, reliably and reproducibly

##Organizing Your TestsPut it into the same packagesSeparate tests from production code

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
**assertEquals(<Type> expected, <Type> actual)**  

* Compares primitive types by value* Compares class types by calling equals* Overloaded with all primitive types, Object and String.
Rundung bei Double immer angeben```java
@Testpublic void testSquareRootUsingInverse() {   double x = mySquareRoot(4.0);   assertEquals(4.0, x * x, 0.00001);}```
**assertSame(Object expected, Object actual)** 
* Compares references using ==-operator**assertNull(Object x), assertTrue(boolean b)**
* Does what it says :-)
**fail()*** Unconditional failure of test

####Exception
Use an expected argument to the @Test annotation: **@Test(expected=IllegalArgumentException.class)**

```java
try {	// code that should throw an exception fail();} catch (<Type of expected exception> e) {	assertNotNull(e); // to prevent empty catch clause // or more detailed, e.g.:	assertEquals("Correct Message?", e.getMessage());}
```

####Anotaions Order
1. @BeforeClass *(they must be static)*
2. @Ignore
3. @Before
4. @Test
5. @After
6. @AfterClass *(they must be static)*

####(static) imports
* Annotations can be imported from the org.junit package.* All assertions must be imported statically from the org.junit.Assert class.


##Good Tests are ATRIP:
* **A**utomatic...invoking the tests and checking the results* **T**horough...test everything that is likely to break => Code coverage* **R**epeatable...able to run over and over again, producing same results* **I**ndependent...no test relies on an other test* **P**rofessional...use same professional standards as for the production code##RIGHT-BICEP* **Right** - Are the results right?* **B** - Are all boundary conditions CORRECT?* **I** - Can you check inverse relationships?* **C** - Can you cross-check results using other means?* **E** - Can you force error conditions to happen?* **P** - Are performance characteristics within bounds?
###Conditions to check:* bogus or inconsistent input values* badly formatted data such as email addresses * empty or missing values* values far in excess* duplicates* ordered versus unordered data

###Boundary Conditions - CORRECT* **C**onformanceDoes the value conform to an expected result?* **O**rderIs the set of values ordered or unordered as appropriate?* **R**angeIs the value within reasonable minimum and maximum values?* **R**eferenceDoes the code reference anything external that isn't under direct control of the code itself?* **E**xistenceDoes the value exist (e.g. is non-null, non-zero, present in a set,...)* **C**ardinalityIs there the expected number of values?* **T**imeIs everything happening in order? At the right time? In time?
***Only test this, if it is really relevant – go for correctness and robustness first***

##TDD - Test First
Write Test Code before productive code**Approach**
* Define methods (names, parameters, return values, exceptions) * Write test code according to method requirements* Implement productive code until tests are green
**Advantages*** You have tested software * You have a safety net* You have testable code
**What is Testable Code?**
* it is easy to add tests* it requires no big infrastructure * it can be tested in isolation##Terms* **Class under Test (CUT)**	* A class that has to be tested* **Method under Test (MUT)**	* A single method that has to be tested* **Test Case**	* specific data that is chosen for testing methods of a CUT* **Test Suite**	* a set of test cases that serves a particular testing goal* **Test Fixture**	* See following slides##Example
```javapublic class SimpleTest {
	private Collection<Object> collection;
	@Before // assures that objects under test are always created the same way 	public void setUp() { collection = new ArrayList<Object>(); }
	// all tests operate on objects with the same content.	@Test	public void testEmptyCollection() {		assertTrue(collection.isEmpty()); 	}
	@Test	public void testOneItemCollection() {		collection.add("itemA");		assertEquals(1, collection.size()); 	}
		@After // assures that all resources are freed after each test	public void tearDown() { 		collection = null; 	} }```