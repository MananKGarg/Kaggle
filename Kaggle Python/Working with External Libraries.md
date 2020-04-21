## Working with External Libraries

So far we talked about types and functions built in python. but there are vast number of custom libraries written in python . Some are included in standard library . Others can be easily added, if they were'nt already shipped with python.

We access the lib using **import**. we will start by importing math from standard library

```python
import math

print("It's math! It has type {}".format(type(math)))

Output - It's math! It has type <class 'module'>

````
So, math is a module, module is just a collection of variables defined by someone else.We can see all names in maths using dir()

```python
print(dir(math))

['__doc__', __file__, __loader__, __name__, __package__, __spec__, acos, acosh, asin, asinh, atan, *atan2*, atanh, ceil, copysign, cos, cosh, degrees, e, erf, erfc, exp, expm1, fabs, factorial, floor, fmod, frexp, fsum, gamma, gcd, hypot, inf, isclose, isfinite, isinf, isnan, ldexp, lgamma, log, log10, log1p, log2, modf, nan, pi, pow, radians, sin, sinh, sqrt, tan, tanh, tau, trunc]

```

We can access these variables using dot syntax. Some refer to simple values like pi

```python

print("pi to 4 significant digits = {:.4}".format(math.pi))

Output - pi to 4 significant digits = 3.142
```

But most of them are functions

```python

math.log(32,2)

output = 5.0
```
we can call help if we don't know what a function is

```python

help(math.log)

Output

Help on built-in function log in module math:

log(...)
    log(x[, base])
    
    Return the logarithm of x to the given base.
    If the base not specified, returns the natural logarithm (base e) of x.
    
```

we can also call help on module itself. This gives combined documentation for all the functions and values in the module

<br>

If we know we'll be using functions in math quite frequently, we can import it under a shorter name to save somr typing

```python

import math as mt
mt.pi

Output

3.141592653589793
```

Its a common convention to import numpy as np and pandas as pd
<br>
It would be great if we could just refer to all variables in math by themselves. pi instead of math.pi. We can do that

```python

from math import*
print (pi, log(32,2))

Output - 3.141..., 5.0

```

import * makes all the module's variables directly accessible to you but it can be harmful

```python

from math import *
from numpy import *
print(pi, log(32,2))

output - error

```
star imports can lead to difficult to debug situations. here, math and numpy both have functions called log , but have different semantics.
<br>

a good compromise is to import only the specific things we need from each module

```python

from math import log, pi
from numpy import asarray
```
Submodules

We've seen that modules contain variables which refer to functions and values. we need to be aware that thry can also contain variables referring to other modules.

```python

import numpy
print("numpy.random is a ", type(numpy.random))
print("it contains names such as...", dir(numpy.random)[-15:]

)

output- 

numpy.random is a <class 'module'>

numpy.random is a <class 'module'>
it contains names such as... ['set_state', 'shuffle', 'standard_cauchy', 'standard_exponential', 'standard_gamma', 'standard_normal', 'standard_t', 'test', 'triangular', 'uniform', 'vonmises', 'wald', 'warnings', 'weibull', 'zipf']

```

So if we import numpy as above, then calling a function in random "submodule" will require two dots.

```python

#Roll 10 dice
rolls = numpy.random.randint(low = 1, high = 6, size = 10)
rolls

output 

array([3,2,5,2,4,2,2,3,2,3])

```

### Three tools for understanding strange objects

1. type() { What is this thing? }

```python

type(rolls)
numpy.ndarray

```
2. dir() {What can I do with it?}
3. help() {tell me more}

Operator Overloading







 






































































