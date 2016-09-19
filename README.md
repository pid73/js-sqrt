# Algorithm to compute square root in Javascript

This is the [Babylonian or Heron's method](https://en.wikipedia.org/wiki/Methods_of_computing_square_roots#Babylonian_method).

It iterates until the precision underflow limit of the IEEE 754 standard is hit.

On Chrome this method always yields exactly the same result as `Math.sqrt()`, with one exception.
The square root of 2 has one additional digit of precision.
It is a 1 instead of a 0.
This value is impossible to obtain on IEEE 754.

An explanation may be that this very notable value is hard-coded for precision and performance reasons.

Another explanation is that Chrome uses a higher precision standard, and then down-casts it to IEEE 754.
That makes perfectly sense, a native C implementation also is surely faster.
In the latter case more discrepancies may occur (but, admittedly, none were detected in several tests).
