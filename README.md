# sum-two-consecutive-squares
Sum of the squares of two consecutive numbers

See [Fermat's theorem on sums of two squares](https://en.wikipedia.org/wiki/Fermat%27s_theorem_on_sums_of_two_squares), but here for specific case with x and y consecutive.<br>
See also [A000217 sequence](https://oeis.org/A000217).

For any x > 0 and y = x + 1, s = x² + y².

Start with x = 1, then the first fifty terms of s, arranged in this way :
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

For s ending by 13, if we use this form : s = 100z + 13, then the sequence of z is :<br>
```
   0, 1, 3, 6, 10, 15, 21, 28, 36, 45, 55, 66, 78, 91, 105, 120, 136, 153, 171, 190, ...<br>
```
We observe the terms of A000217 sequence.
