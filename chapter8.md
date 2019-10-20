# Boundaries
How to keep integration between our code and 3rd party/foreign code clean

3rd party aims to provide broad usability, but our application needs specific implementation.

There can be case like, we want immutable but the library provides mutable. also, there will be lots of interfaces that we won't use

Also, Map class as an example treats everything as generic (Object). it means that we are forced to work with the using casting or

generic Map<OurClass>


Good example: 
>
>public class Sensors {

>> private Map sensors = new HashMap();
>
>> public Sensor getById(String id) {
>
>> return (Sensor) sensors.get(id);
 
> }
>}

don't pass Map object around, there will be lots of places to fix if Map interface changes.


**Learning tests** 

If we want to learn API interface we can write the simple test to play with the interface to learn its behaviour.

They are free, useful if interface changes in the next release.

**Using code that does not exist**

refers to subsystem, that we want to use but it's not there yet.

we can create inteface for that feature we want, and define what we need from them.








