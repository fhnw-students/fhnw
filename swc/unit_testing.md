#Unit Testing

##Why
**YOU** have to show, that your software does what it is expected to do – correctly!

##What
Testing is the process of evaluating a software to determine if it meets the customers’ requirements.

1. Testing is comparing actual results to expected results

##Organizing Your Tests

##Terms
**Validation**: The process of evaluating software at the end of software development to ensure compliance with intended usage








Unit Testing is done






@Test

@Before


@After
```

####Assertions
**assertEquals(<Type> expected, <Type> actual)**  

* Compares primitive types by value





####Exception
Use an expected argument to the @Test annotation: **@Test(expected=IllegalArgumentException.class)**

```java
try {
```

####Anotaions Order
1. @BeforeClass *(they must be static)*
2. @Ignore
3. @Before
4. @Test
5. @After
6. @AfterClass *(they must be static)*

####(static) imports
* Annotations can be imported from the org.junit package.


##Good Tests are ATRIP:
* **A**utomatic


###Boundary Conditions - CORRECT
