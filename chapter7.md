It is common to see that in many projects, error handling code is scattered around and dominate most of the portion in project.

Error handling is undoubtedly important, but it must not obscure the code logic!

1. avoid lot of checking but instead, throw and exception

    avoid having if else to check each condition that could fail, but use exception

2. Try Catch Finally

    When writing code that could throw exception, start writing block of try catch finally first.

it helps you define what user of the code should expect.

treat Try statement like a transaction, it could fail at any line in the try.

3. Use unchecked exception

    checked exception comes with the price of Open/Closed principle. 
    if we want to catch it 3 levels above from the throw (sounds familiar enough for me here when I reach this line) you have to declare this throw in all signatures of above level classes.

4. Provide context with exception

    Each exception that you throw should provide enough context to determine the source and location of an error. (stacktrace). but stacktrace does not give you the intent. so, create informative error message and pass them along. 

5. Define Exceptions in term of callers need.

     Our most important concern should be how they are caught.
     instead of throwing random, different level of abstraction error, if caller would treat them and handle them the same. you can group them.
    
     Also, it would be good to wrap vendor's APIs so that we can throw our own exception and not relying on their error design.

6.  SPECIAL CASE PATTERN [Fowler]. 

    You can design object that can handle the error by itself and return special case object not the error. this way, the client does not have to handle the exception.
    for example, if we cannot get MealExpense from employee we will return per diem, instead of throwing expense not found.

7.  Don't return Null!!

    it will introduce hell chain of null checking in the code.
    when we return null, we create work for ourself in the future to check it.

    instead of returning null, throw exceptions or special case object.

    for list, we can return Empty list instead of null

8.  Don't pass Null!!

    I don't think I have to explain anything here.

    

9.  

