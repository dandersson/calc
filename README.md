calc
====
A _very_ minimalistic Python calculator. Actually, it's only the standard Python interpreter with `import * from math` and some physical constants defined. In practice, I feel that more than that (GUIs, special syntax, …) is just unnecessary for a quick and simple calculator.

Not especially groundbreaking stuff, but I've been using it for years, so maybe someone will find its simplicity useful.

Requirements
------------
* A shell
* Python

Usage
-----
* `calc` by itself goes to interactive mode by starting the interpreter.
*  Expressions can be given as an argument:

        $ calc e**pi-pi
        19.9990999792
        $
* …or as `STDIN`:
    
        $ echo 'ln(-e*cos(pi))*sqrt(256)' | calc
        >>> -16.0
        >>> 
        $


Notes
-----
* Tab completion is enabled:
    
        >>> def extension(L, E, h, A, q):
        ...     return q*L**3/(8*h*E*A)*(1+16*h**2/(3*L))
        ... 
        >>> alvsborgsbron=(417.6, 190e9, 52.6, .22, 210e3)
        >>> golden_gate=(1280, 198e9, 143, .54, 185e3)

    Now, `ext` `<Tab>` `(*alv` `<Tab>` `)` `<Enter>` gives:

        >>> extension(*alvsborgsbron)
        31.5920944757691

    and so on. If one is used to the shell, this is as intuitive as can be.

* `↑`/`↓` walks through command history, and other standard text navigation idioms are followed (`Ctrl`+`W`, `Ctrl`+`U`, `Home`, `End`, `Ctrl`+`←`/`→`, etc.).

* `_` holds the previously returned result in the interpreter. Useful in many respects, e.g.:
    
        >>> m = 80
        >>> v = 20
        >>> m*v**2
        32000
        >>> E_k = _
        >>> E_k
        32000

* `x^y` is not "_x_ to the power of _y_" in Python, but the [binary XOR operator](http://docs.python.org/2/reference/expressions.html#binary-bitwise-operations). `x**y`, however, is exactly "_x_ to the power of _y_". This can be overridden, but I'd rather stay close to the Python syntax.

* Make use of Python's standard language features where it fits. Variable declaration, lists, built-in functions (`sum()`, `divmod()`, `range()`, …), defining quick functions, etc. Also check what the `math` module provides by e.g. running `import math; help(math)` in a Python interpreter.

* Using [Fluxbox](http://fluxbox.org/), I have defined

        Mod4 c    :ExecCommand urxvtc -e calc

    in my `~/.fluxbox/keys` to start a terminal with `calc` via a simple keyboard shortcut. Useful enough that it should be a standard feature in most window managers, I believe :-) .

* Extra modules can easily be imported when needed, e.g. `itertools`, `random`, [NumPy](http://www.numpy.org/) or [matplotlib](http://matplotlib.org/).

And remember that everything is just Python, so after noting how powerful and easy to use the Python interpreter is in this respect, just write script files for more complicated calculations. One can come a long way without [Matlab](http://www.mathworks.se/products/matlab/).

Upstream
--------
<https://github.com/dandersson/calc>

License
-------
[GPL version 2](http://www.gnu.org/licenses/gpl-2.0.html) or later.
