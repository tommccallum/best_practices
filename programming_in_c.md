# Programming in C

See https://wiki.sei.cmu.edu/confluence/display/c/SEI+CERT+C+Coding+Standard for secure coding standards.

- treat all warnings as errors
- use pragma's if you are absolutely sure you want to override the warning.  Put reasons in comments.
- small main function allows for maximum unit test coverage.
- minimise the dependency between compilation units by putting required headers in the .c file rather than .h
= local headers should use quotes, not angle brackets
- list system headers first, then local headers
- always use a header guard (preferably with a application local prefix)
- use <pre>_WIN32</pre> to define windows specific code
- remember than names should not start with underscore as these are reserved
- always right side const to minimise errors reading
- return ```char const *``` if you want to return a pointer to a constant string
- ```error: storage class specified for parameter ``` is a missing semi-colon in a declaration
- ensure you use const when you do not want the function being handed the object to delete it
- if a function is not required outside of the compilation unit then declare as static
- try not to have files that combine lots of functions like "utils.h", group similar function together so that they can be independently tested.
- only put headers in a header file if the declarations require them

# Lessons learned from Python C-code

- using structures as singleton objects for True and False
```typedef struct {} _Py_FalseStruct```
then to check
```#define Py_False ((PyObject *) &_Py_FalseStruct```

- uses the , to shorten macro 
``` #define SOME_END return Py_INCREF(object), &object;```

- uses a level of abstraction, using Macros, to allow functions to be overriden later by defining function with underscore "_py_some_function" and then having a macro #define Py_SomeFunction _py_some_function

- all items are reference counted pointers
- wrap all code within extern "C" so can be compiled in C++ compiler
- use a macro that returns itself to expand macros within macros
```#define Py_FORCE_EXPANSION(X) X```
- uses libm for GNU mathematical functions
- defined macros for compiler attributes it uses to allow for change
- public API and variable wrapped in macros (PyAPI_FUNC, PyAPI_DATA and PyMODINIT_FUNC)
( See pyport.c )
- heap objects implemented as a doubly linked list
- variable size objects is a struct of pointer to the first object and number of items
- all user methods of objects are a hash table
- core functionlity of a buildin type is fixed
- richcompare is implemented as a macro Py_RETURN_RICHCOMPARE
- uses unicode for all strings and has good functions in stringlib (http://effbot.org/zone/stringlib.htm )

