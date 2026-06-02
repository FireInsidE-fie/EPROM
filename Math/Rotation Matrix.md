---
tags:
  - concept
  - math/geometry
---
# Multiplying by a Vector
When multiplying a rotation matrix $M$ by a vector $v$, **you scale each column of the matrix by the corresponding element of that vector**.
Then, you add all the elements of the resulting matrix lines to be left with the same amount of elements as the base vector. **That's your new, rotated vector**.
```
v = (0, 0, 1)  // Vector pointing towards Z

M (rotates 90 degrees to the left)
0 0 -1
0 1 0
1 0 0

Take column and multiply it with the right vector element
First column is multiplied by the first vector element, etc.
0 * (0, 0, 1) = (0, 0, 0)
0 * (0, 1, 0) = (0, 0, 0)
1 * (-1, 0, 0) = (-1, 0, 0)

Which gives you
0 0 -1
0 0 0
0 0 0

Then, take each line, sum it all up to end up with only 3 numbers
0 + 0 + -1 = -1
0 + 0 + 0 = 0
0 + 0 + 0 = 0
=
(-1, 0, 0)

Your vector is now looking to the left!
```
# Matrices Examples
## Identity Matrix
```
1 0 0 -> x becomes x, no change
0 1 0 -> y becomes y, no change
0 0 1 -> z becomes z, no change
```
## 90 Degrees to the Left
```
0 0 -1 -> x becomes -z; it is now on the z axis but in reverse direction
0 1 0 -> y stays y, no changes
1 0 0 -> z becomes x
```