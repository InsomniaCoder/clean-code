# Unit Tests

**Three Laws of TDD**

*First law*

You may not write production code until you write a failing unit tests

*Second Law* 

You may not write more of a unit test than is sufficient to fail, and not compiling is failing.

*Third Law*

You may not write more production code than is sufﬁcient to pass the currently failing test. 

This forces us to write many tests daily. and will cover all our application code.


**Keeping test clean**

Writing dirty tests = no tests or worst.  because test must change as code evolve.

dirtier test, harder to change code.

there will be some point that we estimate too large because tests are hard to change.

*Tests are first class citizen*

**Tests Enable the -ilities**

Unit tests make your code flexible to change. Enable maintainable, reusable.

**Clean Tests**

Three things that make clean test

>Readability,
>Readability,
>Readability

What makes code readable
>
>Clarity,
>Simplicity,
>Density of expression

You need to explain a lot using few expression as possible.

reduce duplicate code in tests, remove too much detail that interfere with expressiveness of test.


**Domain Specific Testing Language**

we can wrap normal program API wih test-friendly interface to help improving test Readability

>public void testGetDataAsXml() throws Exception { 
   >>   makePageWithContent("TestPageOne", "test page");
   
>> submitRequest("TestPageOne", "type:data");

>>    assertResponseIsXML();   
 
 >>assertResponseContains("test page", "<Test");  }
 

**A Dual Standard**

test code must be simple, expressive but does not need to be as efficient as production code.

**One Assert Per Test**

do not need to be one, but be cautious and minimize assertion in one test

**Single concept per test**

test only one concept in one test function, this also helps minimize too many assertions.

**F.I.R.S.T.**

>>Fast: test should run quickly -> we want to run them often.


>>Independent: should not depend on each other, orderless, to prevent downstream failure.

>>Repeatable: repeatable in evert environment -> to not having excuse why it fails

>>Self-Validating: should have boolean output, we have to know instantly if it passes of fails by not looking to the logs.

>>Timely: write it *just before *production code.














