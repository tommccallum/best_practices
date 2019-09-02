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
```


