# sum-two-consecutive-squares
Sum of the squares of two consecutive numbers

See [Fermat's theorem on sums of two squares](https://en.wikipedia.org/wiki/Fermat%27s_theorem_on_sums_of_two_squares), but here for specific case with x and y consecutive.<br>
See [this conversation](https://groups.google.com/g/seqfan/c/Kq_n-Jj-qxk) on SeqFan mailing list.

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
  * odd lines with $s$ ending by 13 (at position $5j + 2$)
  * even lines with $s$ ending by 1 (with gap of $100n + 40$ between them), a cycle ending by 41, 81, 21, 61, 01
* third column : $s$ ending by 1 (with gap of $100n + 60$ between them), a cycle ending by 61, 21, 81, 41, 01

For $s$ ending by 13, if we use this form : $s = 100z + 13$, then the sequence of $z$ is :<br>
```
   0, 1, 3, 6, 10, 15, 21, 28, 36, 45, 55, 66, 78, 91, 105, 120, 136, 153, 171, 190, ...
```
We observe the terms of [OEIS A000217 sequence](https://oeis.org/A000217).

### Connection to the Brahmagupta-Fibonacci identity (first column)

The first column consists of terms that always ending by 5, meaning they are all multiples of 5 (such as $5, 25, 85, 145, 265, 365, \dots$).

According to the **Brahmagupta-Fibonacci identity**, the product —or perfect quotient— of two sums of two squares is itself a sum of two squares.<br>
Since 5 can be written as $1^2 + 2^2$, it follows a property: **dividing any number from this first column by 5 will always yield a quotient that is also a sum of two squares**.

For example:
*   $5 / 5 =  1 \implies 0^2 + 1^2$
*  $25 / 5 =  5 \implies 1^2 + 2^2$
*  $85 / 5 = 17 \implies 1^2 + 4^2$
* $145 / 5 = 29 \implies 2^2 + 5^2$
* $265 / 5 = 53 \implies 2^2 + 7^2$
* $365 / 5 = 73 \implies 3^2 + 8^2$

For the first column (where $s$ is a multiple of 5), the relationship $s/5 = x'^2 + y'^2$ reveals two linear structures (one for the odd-numbered lines and one for even-numbered lines).<br>
By tracking the resulting pairs $(x', y')$, we observe an arithmetic progression:

* The values of $x'$ follow the sequence $k$ (for $k=0, 1, 2, 3 \dots$)
* The values of $y'$ follow the sequence $3k + 1$

| x  | y | s | s/5 | x′^2+y′^2 | (x′, y′) |
|:-:|:-:|:-:|:-:|:-:|:-:|
|1|2|5|1|0²+1²|(0, 1)|
|6|7|85|17|1²+4²|(1, 4)|
|11|12|265|53|2²+7²|(2, 7)|
|16|17|545|109|3²+10²|(3, 10)|

This proves that every term in the first column is linked to a specific Gaussian integer transition.<br>
Specifically, each sum $s/5$ can be expressed as: $s/5 = k^2 + (3k+1)^2 = 10k^2 + 6k + 1$

This confirms that the first column is not just a collection of multiples of 5, but a structured sequence of sums of squares where the base values $(x', y')$ evolve linearly. This regularity is a direct consequence of the Brahmagupta-Fibonacci identity applied to the prime factor 5.

### Connection to Fermat's theorem on sums of two squares (second column, ending by 13)

By observing the equation $s = 100z + 13$, we can deduce a mathematical property regarding the prime factors of these specific numbers.

First, since $s = 100z + 13$, it follows that $s \equiv 13 \pmod{100}$, which simplifies to $s \equiv 1 \pmod 4$.<br>
This aligns with the necessary condition in **Fermat's theorem on sums of two squares**.

Because $x$ and $y$ are consecutive integers ($y = x + 1$), they are strictly coprime ($\gcd(x, y) = 1$).<br>
A corollary of Fermat's theorem states that if a number can be expressed as the sum of two coprime squares, **every single odd prime factor of that number must be congruent to 1 modulo 4** (i.e., of the form $4k + 1$).

Then for any sum of two consecutive squares ending by 13 (where $z$ is a triangular number from the OEIS A000217 sequence, **none of its prime factors will ever be congruent to 3 modulo 4** (i.e., of the form $4k + 3$).

This guarantees that these numbers (if not primes) will never be divisible by [non Pythagorean primes](https://oeis.org/A002145) (such as $3, 7, 11, 19, 23, \dots$).<br>
All of **the prime factors of these s** are strictly of the form $4k + 1$ as [Pythagorean primes](https://oeis.org/A002144) (such as $5, 13, 17, 29, 37, \dots$).

### Properties of the second column (numbers ending by 1)

If we isolate the even-line terms from the second column that do not ending by 13 (such as $41, 181, 421, 761, 1201, \dots$), we can observe a predictable growth.<br>
The sum becomes $s_k = 50k^2 + 90k + 41$.
The values of $x$ for these terms are $4, 9, 14, 19, \dots$, which can be written as $x = 5k + 4$.

By calculating the difference between consecutive terms in this sub-sequence, we find that the gap grows by exactly $100n + 40$ (where $n$ is the step index: $140, 240, 340, 440, \dots$). 

This $100n + 40$ gap leads to two deductions:
* **The 2-digit cycle:** Because the difference adds exactly $40$ to the tens and units digits (modulo 100) at each step, the last two digits of these numbers follow an infinite, repeating 5-step cycle:
   **41, 81, 21, 61, 01** (and then back to 41)
* **Triangular number formula:** just like the terms ending by 13 can be expressed using triangular numbers ($100 T_n + 13$), we can express this sub-sequence using the $k$-th triangular number ($T_k$) and the term index ($k$):
   $s_k = 100 T_k + 40k + 41$

### Properties of the third column (numbers ending by 1)

The third column consists of terms where $x$ is a multiple of 5 ($x = 5, 10, 15, 20 \dots$).<br>
If we write $x = 5k$ (for $k \ge 1$), the sum becomes $s_k = 50k^2 + 10k + 1$.

By analyzing the difference between consecutive terms in this column ($61, 221, 481, 841, 1301, \dots$), we find that the gap grows by exactly $100k + 60$ (the gaps being $160, 260, 360, 460 \dots$). 

This $100k + 60$ progression creates a mirror image of the second column's properties:

* **The reversed 2-digit cycle:** because the difference adds $60$ to the tens and units digits (modulo 100) at each step, the last two digits follow an infinite 5-step cycle that is the **exact reverse** of the second column's cycle:
   **61, 21, 81, 41, 01** (and then back to 61)
2. **Triangular number formula:** we can express this sequence using the $(k-1)$-th triangular number ($T_{k-1}$):
   $s_k = 100 T_{k-1} + 60k + 1$

### Prime numbers of s values and Bunyakovsky's conjecture

If we expand our initial equation $s = x^2 + (x+1)^2$, we obtain the quadratic polynomial $s = 2x^2 + 2x + 1$. 

By factoring it, we can rewrite the equation as $s = 2x(x+1) + 1$, or simply **$s = 2xy + 1$** (since $y = x+1$).<br>
This factored form provides proof that $s$ is **always an odd number** ($2 \times \text{integer} + 1$), meaning 2 will never be a prime factor in this sequence.

This quadratic polynomial satisfies the three strict conditions of **Bunyakovsky's conjecture**:
* its leading coefficient is positive ($2 > 0$)
* it is irreducible over the integers (it cannot be factored into two linear polynomials with rational coefficients)
* the generated values share no common divisor greater than 1 for all $x$ (for example, the first two terms, 5 and 13, are strictly coprime)

Because it meets all these criteria, Bunyakovsky's conjecture dictates that **this sequence should generate an infinite number of primes**.<br>
While this remains one of the unproven problems in mathematics (no one has yet been able to prove that *any* polynomial of degree 2 or higher generates infinitely many primes), the mathematical structure of $s = 2xy + 1$ strongly implies that prime numbers will never stop appearing throughout this sequence.

### Combining squares and Triangular numbers (extended symmetries)

The Daniel's contribution highlighted additional layers of symmetry connecting this sequence to the broader world of triangular numbers.<br>
While we have already established how our specific sums of squares generate triangular patterns, there are further fundamental properties at play. 

The relationship flows in both directions: just as our sums are linked to triangular numbers, **the sum of any two consecutive triangular numbers forms a perfect square** ($T_{n} + T_{n-1} = n^2$). 
By combining these geometric properties, we can extract two new observations about our sequences:

#### 1. The $100k^2 + 26$ identity
If we group specific pairs of sums from our sequence —specifically, the sums of consecutive squares originating from base numbers symmetrically offset around multiples of 5— their combined total yields a clean equation.<br>
For any integer $k$, adding these two distinct sums of two consecutive squares gives:

$$(5k-3)^2 + (5k-2)^2 + (5k+2)^2 + (5k+3)^2 = 100k^2 + 26$$

*(For example, with $k=1$, we evaluate the bases $x=2$ and $x=7$. Their respective sums of consecutive squares are $2^2+3^2=13$ and $7^2+8^2=113$. Adding them together gives $13 + 113 = 126$, which matches the formula $100(1^2) + 26$.)*

#### 2. Connection to [OEIS A016802 sequence](https://oeis.org/A016802)
As a natural extension of how squares and triangular numbers interact, there is a strict rule regarding specific pairs of even triangular numbers.<br>
If we sum $T_{4n-1}$ and $T_{4n}$ (which are consecutive even triangular numbers), the result is always a perfect square strictly of the form $16n^2$. 

* For $n=1$: $T_3 + T_4 = 6 + 10 = 16 \implies 16(1^2)$
* For $n=2$: $T_7 + T_8 = 28 + 36 = 64 \implies 16(2^2)$
* For $n=3$: $T_{11} + T_{12} = 66 + 78 = 144 \implies 16(3^2)$

This progression ($16, 64, 144, 256 \dots$) maps directly to the **OEIS A016802** sequence, further demonstrating the deep, infinite arithmetic ties between sums of squares and triangular geometries.
