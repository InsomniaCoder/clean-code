First introduction to this chapter talks about how we expose variables of our classes.
we make them private because we do not want anyone to depend on them. but, why we have getter and setter for all of them? blindingly, have getter/setter for all of them is wrong.

the key message here is hiding implementation = ABSTRACTIONS! just having a layer of getter/setter does not help hiding the implementation.

Classes should expose abstract interfaces that allow its user to manipulate "essence" of the data without knowing the implementation.

For example, 

1. for the coordinate class, we may have getter for both x,y but we should have only single setter that take both x and y at the same time.

2. for Vehicle class, in order to communicate the fuel level. instead of having getFulesTankCapacityInGallons() or getGallonsOfGasoline() (both are implementation detail of the data)
we should have the interface of getRemainingFuelPercent() which expose essence of the information we want here without providing unnecessary information to the user.

#Object vs Data structure

Object hides its data behind abstraction and expose abstract functions that operate on its data.
While Datastructure expose data without meaningful fuctions.

#Law of Demeter
The method should not invoke methods on objects that are returned by any of allowed functions. (talk only to friends not strangers)

#Train wrecks..
This is an example of train wrecks:

final String outputDir = ctxt.getOptions().getScratchDir().getAbsolutePath();

we should split them up like this 

Options opts = ctxt.getOptions(); 
File scratchDir = opts.getScratchDir();
final String outputDir = scratchDir.getAbsolutePath(); 

the bad example also breaks the law of demeter because it assumes that it knows ctxt has options which has directory that has an absolute path.

the calling function knows too much, too deep about the object.

If ctxt is an object, we should be telling it to do something

BufferedOutputStream bos = ctxt.createScratchFileStream(classFileName);

#DTO
DTO or Data Transfer Objects is a class with public variable and no functions.
They are useful for communicating with database, parsing message from network, API.


#Conclusion

Objects expose behavior and hide data. This helps with changing implementation without breaking existing code that relies on the same interface.



