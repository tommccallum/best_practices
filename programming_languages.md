# Lessons from the GNU C++ standard library includes

- Pragma's are instructions to the compiler that can be embedded in code files
- have some way to determine internal code e.g. C/C++ use the double underscore prefix (__)
- uses DEFINE constants to check for functionality e.g. #define __cpp_lib_some_functionality 201402
- __cplusplus macro contains the current version (by date) and is hard defined by the compiler
- COW = copy on write
- SSO = short string optimisation
- txnal = transactional
- <exception> has routines for setting how unhandled exceptions are managed.
- POD, plain old data with standard constructor, copy, move and destructor semantics
- non-POD a customised object
- the compiler creates std::initialzer_list<T> when it sees {}
- initializer_list<T> is defined in specification as the class that is used
- TR1 and TR2 are technical reports, groups of functionality that were at one point not part of the STL
- Boost is a way to create new libraries that might one day become part of the standard
- experimental is the stuff being worked on for the next version of C++
- unordered_set is a set of immutable items, optimised for checking for duplicates so order returned is not necessarily the order added
- use <regex> for regular expressions
- 
