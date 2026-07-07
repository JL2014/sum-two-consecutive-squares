# sum-two-consecutive-squares
Sum of the squares of two consecutive numbers

See [Fermat's theorem on sums of two squares](https://en.wikipedia.org/wiki/Fermat%27s_theorem_on_sums_of_two_squares), but here for specific case with x and y consecutive.<br>
See also [A000217 sequence](https://oeis.org/A000217).

For any $x > 0$ and $y = x + 1$, $s = x² + y²$.

Start with $x = 1$, then the first fifty terms of $s$, arranged in this way :
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
* first column : $s$ multiple of 5, [Brahmagupta–Fibonacci identity](https://en.wikipedia.org/wiki/Brahmagupta%E2%80%93Fibonacci_identity)
* second column :
  * odd lines with $s$ ending by 13 (at position $5k + 2$)
  * even lines with $s$ ending by 1 (with gap of $100n + 40$ between them), a cycle ending by 41, 81, 21, 61, 01
* third column : $s$ ending by 1

For $s$ ending by 13, if we use this form : $s = 100z + 13$, then the sequence of $z$ is :<br>
```
   0, 1, 3, 6, 10, 15, 21, 28, 36, 45, 55, 66, 78, 91, 105, 120, 136, 153, 171, 190, ...
```
We observe the terms of A000217 sequence.

### Connection to the Brahmagupta-Fibonacci identity (first column)

The first column consists of terms that always ending by 5, meaning they are all multiples of 5 (such as $5, 25, 85, 145, 265, 365, \dots$).

According to the **Brahmagupta-Fibonacci identity**, the product —or perfect quotient— of two sums of two squares is itself a sum of two squares.<br>
Since 5 can be written as $1^2 + 2^2$, it follows a property: **dividing any number from this first column by 5 will always yield a quotient that is also a sum of two squares**.

For example:
*  $85 / 5 = 17 \implies 1^2 + 4^2$
* $145 / 5 = 29 \implies 2^2 + 5^2$
* $265 / 5 = 53 \implies 2^2 + 7^2$
* $365 / 5 = 73 \implies 3^2 + 8^2$

### Connection to Fermat's theorem on sums of two squares (second column, ending by 13)

By observing the equation $s = 100z + 13$, we can deduce a mathematical property regarding the prime factors of these specific numbers.

First, since $s = 100z + 13$, it follows that $s \equiv 13 \pmod{100}$, which simplifies to $s \equiv 1 \pmod 4$.<br>
This aligns with the necessary condition in **Fermat's theorem on sums of two squares**.

Because $x$ and $y$ are consecutive integers ($y = x + 1$), they are strictly coprime ($\gcd(x, y) = 1$).<br>
A corollary of Fermat's theorem states that if a number can be expressed as the sum of two coprime squares, **every single odd prime factor of that number must be congruent to 1 modulo 4** (i.e., of the form $4k + 1$).

Then for any sum of two consecutive squares ending in 13 (where $z$ is a triangular number from the A000217 sequence), **none of its prime factors will ever be congruent to 3 modulo 4** (i.e., of the form $4k + 3$).

This guarantees that these numbers (if not primes) will never be divisible by ([non Pythagorean](https://oeis.org/A002145)) primes such as $3, 7, 11, 19, 23, \dots$<br>
All of their prime factors are strictly of the form $4k + 1$ ([Pythagorean primes](https://oeis.org/A002144) such as $5, 13, 17, 29, 37, \dots$).

### Properties of the second column (numbers ending by 1)

If we isolate the even-line terms from the second column that do not ending by 13 (such as $41, 181, 421, 761, 1201, \dots$), we can observe a predictable growth.<br>
The values of $x$ for these terms are $4, 9, 14, 19, \dots$, which can be written as $x = 5k + 4$.

By calculating the difference between consecutive terms in this sub-sequence, we find that the gap grows by exactly $100n + 40$ (where $n$ is the step index: $140, 240, 340, 440, \dots$). 

This $100n + 40$ gap leads to two deductions:
* **The 2-digit cycle:** Because the difference adds exactly $40$ to the tens and units digits (modulo 100) at each step, the last two digits of these numbers follow an infinite, repeating 5-step cycle:
   **41, 81, 21, 61, 01** (and then back to 41)
* **Triangular number formula:** just like the terms ending in 13 can be expressed using triangular numbers ($100 T_n + 13$), we can express this sub-sequence using the $k$-th triangular number ($T_k$) and the term index ($k$):
   $s = 100 T_k + 40k + 41$
