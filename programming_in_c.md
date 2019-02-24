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
