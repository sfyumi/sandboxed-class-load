sandboxed-class-load
====================

Basic demo and unit testing on class loading that allows different classes with the same (fully qualified) name to live on the same program.

This was developed made using eclipse and maven quickstart.

This is composed of multiple projects that, inside the code, do not interact between eachother.

In the classloader, the path towards where it searches for the class files is hardcoded. As for the final version, the intent is to load the classes directly from the memory from a class that will do that work (probably directly from a git repository).

The "main" is inside the classloading-test project. Both Main of the project and the Main for the tests are there.  
The class loader is also in that project.

ClassesA and ClassesB are two projects that are meant to simulate two different versions of the same class that never communicate between eachother on any ocation. The only classes that know that this exists are the classes in the classloading-test project. All other classes in this set of eclipse projects have no information that there are those 2 "versions".

ForA and ForB are 2 projects that the respective ClassesA and ClassesB depend on. The .jar that is generated by them has to be placed inside the lib directory in the root of ClassesA and ClassesB projects.  
They act as external dependency libraries that they (ClassesA and ClassesB) require in order to work properly.

dependsTOP acts as a library that both ForA and ForB require in order to function. This one acts as a demonstration that hierarchical loading works no matter the order that the libs are placed in the libs directory.
