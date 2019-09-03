# Competitive Programming (CP)

# Sites
- https://codeforces.com
- Top Coder

# How to win

- minimise time to type
- minimise time to solve

# Bad style habits

Source: https://www.quora.com/What-are-some-bad-coding-habits-you-get-from-competitive-programming

- _Variable and function naming_ - variables like n, m, a, b, x, y and functions like f, dp and solve are 
normal in CP but a big no no in real world
- _Macros_ - a lot of people use macros like REP(i, n) so they could type faster. This makes code hard to read
- _Over shortening_ - it is good to solve a problem in less lines. But in CP there is a tendency to shorten it 
too much making the code unreadable
- _Not using empty lines_ - empty lines will make your code readable. In CP you can often find cca 100loc without a single empty line
- _Non-modular code_ - even though a lot of competitors like writing functions so they could use them later you often find the core of 
the solution in the main() or solve() method
- _Non-OOP programming_ - huge number of codes don't have a single written class or struct. In RL you won't find variables like name 
and age hanging around by them selves
- _Global variables_ - it is very common to have a lot of global variables in CP. Obviously, in RL this is not recommended.

# General Tips & Help

- https://www.geeksforgeeks.org/tips-and-tricks-for-competitive-programmers-set-1-for-beginners/
- https://codeforces.com/blog/entry/23054
- https://www.geeksforgeeks.org/c-tricks-competitive-programming-c-11/
- https://www.quora.com/What-is-a-list-of-data-structures-that-a-competitive-programmer-must-know

# Tactics

- Look for shortcuts for small values of N
- If looking for strings within strings, you can use a graph and depth first search to navigate faster
- If using permutations you will probably need factorials

```
long long fac = 1;
for( int ii=1; ii < n; ii++ ) {
  fac *= ii;
  // ... other work ...
}
```

- use this include to get everything in standard library and remove need for std prefix:

```
#include <bits/stdc++.h>
using namespace std;
```

- rather than worry about 0 index, either ignore it or make arrays bigger than required. 
- use algorithm transforms to shorten typing required.
- if problem talks about modulo, then make all calculations modulo
- unroll some loops to be faster may be necessary
- Global variables are used because in the C standard they are required to be zero initialised.

_“If an object that has static storage duration is not initialized explicitly, it is initialized implicitly as if every member that has arithmetic type were assigned 0 and every member that has pointer type were assigned a null pointer constant.”_

- Large arrays tend to be put as Global variables as otherwise they can sometimes fall foul of a local stack limit.
- Global Variables are also allocated at the time the program is loaded all in one go rather than in small chunks.  Anything that might call malloc will slow down the application, so a one time allocation is better.

# Common C++ hacks to try and squeeze a little extra speed


- Disable syncing between C++ and C standard buffers

```ios::sync_with_stdio(false);```

- Disable syncing between cin and cout, downside is that console output may not be as expected

```cin.tie(0), cout.tie(0);```

- common macros
```
#define FOR(s,c,inc) for(int ii=s; ii < c; ii += inc )
#define cFOR(c) for(int ii=0; ii < c; ii ++ )
#define rFOR(s,c,dec) for(int ii=s-1; ii >= c; ii -= dec )
#define rdFOR(s) for(int ii=s; ii >= 0; ii-- )
#define NWHILE while( n-- )
#define ll long long
#define ull unsigned long long
#define GET_N int n; cin >> n
#define XOR(x,secret) ( x | secret ) & ( ~x | ~secret )
#define HI(x,bits) ( ( x >> bits ) << bits )
#define LO(x, bits) ( x % pow(2,bits) )
#define pb(x,bits) bitset<bits>(x)
#define p32(x) bitset<32>(x)
#define p16(x) bitset<16>(x)
#define p8(x) bitset<8>(x)
#define ISODD(x) num & 1
#define DIV2(x) x >> 1;
#define MUL2(x) x << 1;
#define SWAP(x,y) x ^= y, y ^= x, x ^= y
#define NDIGITS(x) floor(log10(N))+1
#define ISPOW2(x) x && (!(x&(x-1)))
```
- avoid strlen(x) by using:
```
for( i=0; s[i]; i++ ) { 
  // work, loop breaks when s[i] is NULL 
}
```
- use emplace_back, not push_back to stop additional memory allocation
- use inbuilt C++ gcd ```__gcd(x,y)```
- calculate the most significant digit of the number N
```
double k = log10(N);
k = k - floor(k)
int x = pow(10,k);
```
- use C++ builtins for the following:
```
all_of( first, first+n, ispositive());
any_of( first, first+n, ispositive());
none_of( first, first+n, ispositive());
copy_n(source_array,num_to_copy,target_array);
itoa(array_start, array_end, start_value); // create sequence 10,11,12,... or 'a','b','c',....
```
- use 0b for initialising numbers in binary format



