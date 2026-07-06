# sum-two-consecutive-squares
Sum of the squares of two consecutive numbers

See [Fermat's theorem on sums of two squares](https://en.wikipedia.org/wiki/Fermat%27s_theorem_on_sums_of_two_squares), but here for specific case with x and y consecutive.<br>
See also [A000217 sequence](https://oeis.org/A000217).

For any $x > 0$ and $y = x + 1$, $s = x² + y²$.

Start with $x = 1$, then the first fifty terms of s, arranged in this way :
```
  1² +  2² =    5,    2² +  3² =   13,
  3² +  4² =   25,    4² +  5² =   41,   5² +  6² =   61,
  6² +  7² =   85,    7² +  8² =  113,
  8² +  9² =  145,    9² + 10² =  181,  10² + 11² =  221,
 11² + 12² =  265,   12² + 13² =  313,
 13² + 14² =  365,   14² + 15² =  421,  15² + 16² =  481,
 16² + 17² =  545,   17² + 18² =  613,
 18² + 19² =  685,   19² + 20² =  761,  20² + 21² =  841,
 21² + 22² =  925,   22² + 23² = 1013,
 23² + 24² = 1105,   24² + 25² = 1201,  25² + 26² = 1301,
 26² + 27² = 1405,   27² + 28² = 1513,
 28² + 29² = 1625,   29² + 30² = 1741,  30² + 31² = 1861,
 31² + 32² = 1985,   32² + 33² = 2113,
 33² + 34² = 2245,   34² + 35² = 2381,  35² + 36² = 2521,
 36² + 37² = 2665,   37² + 38² = 2813,
 38² + 39² = 2965,   39² + 40² = 3121,  40² + 41² = 3281,
 41² + 42² = 3445,   42² + 43² = 3613,
 43² + 44² = 3785,   44² + 45² = 3961,  45² + 46² = 4141,
 46² + 47² = 4325,   47² + 48² = 4513,
 48² + 49² = 4705,   49² + 50² = 4901,  50² + 51² = 5101, ...
```

We can observe :
* first column : s multiple of 5
* second column : odd lines with s ending by 13, even lines with s ending by 1
* third column : s ending by 1

For s ending by 13, if we use this form : $s = 100z + 13$, then the sequence of z is :<br>
```
   0, 1, 3, 6, 10, 15, 21, 28, 36, 45, 55, 66, 78, 91, 105, 120, 136, 153, 171, 190, ...
```
We observe the terms of A000217 sequence.

### Connection to Fermat's theorem on sums of two squares

By observing the equation $s = 100z + 13$, we can deduce a mathematical property regarding the prime factors of these specific numbers.

First, since $s = 100z + 13$, it follows that $s \equiv 13 \pmod{100}$, which simplifies to $s \equiv 1 \pmod 4$.<br>
This aligns with the necessary condition in **Fermat's theorem on sums of two squares**.

Because $x$ and $y$ are consecutive integers ($y = x + 1$), they are strictly coprime ($\gcd(x, y) = 1$). <br>
A corollary of Fermat's theorem states that if a number can be expressed as the sum of two coprime squares, **every single odd prime factor of that number must be congruent to 1 modulo 4** (i.e., of the form $4k + 1$).

Then for any sum of two consecutive squares ending in 13 (where $z$ is a triangular number from the A000217 sequence), **none of its prime factors will ever be congruent to 3 modulo 4** (i.e., of the form $4k + 3$).<br>
This guarantees that these numbers (if not primes) will never be divisible by primes such as 3, 7, 11, 19, 23, ...<br>
All of their prime factors are strictly of the form $4k + 1$ (e.g., 5, 13, 17, 29, 89, ...).
