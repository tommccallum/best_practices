# Lessons from the GNU C++ standard library includes

- Pragma's are instructions to the compiler that can be embedded in code files
- have some way to determine internal code e.g. C/C++ use the double underscore prefix (__)
- uses DEFINE constants to check for functionality e.g. #define __cpp_lib_some_functionality 201402
- __cplusplus macro contains the current version (by date) and is hard defined by the compiler
- 
