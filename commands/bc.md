## Basic Usage

Basic arythmetic operations in the `bc` interactive shell:
<details>
<summary>Shell examples</summary>

```bash
$ bc
# bc 1.07.1
# Copyright ...
3+2
5
6-4
2
5*2
10
10/3
3
# To use dicimal representation of numbers, set the presicion first.
scale=2
10/3
3.33
# Exit the shell with the 'quit' command or press 'Ctrl+C'
quit
```

</details>
<br>

Another approach to perform calculations is by using the echo command and piping `(|)` the expression to `bc`:
```bash
$ echo "scale=10; 4*a(1)" | bc -l
3.1415926532
```
Note the usage of `a(1)`. It is a _predefined math function_ from the standard math library, enabled by using the `-l` option with the `bc` command.

## Advanced Usage

1. [Utilize mathematical functions in `bc`](#bc_math_funcs).
2. [Use `bc` within Bash scripts](#bc_bash_scripts).

<a name="bc_math_funcs"></a>
### 1. Utilize mathematical functions in `bc`

Square Root:
```bash
# Calculate the square root of a number
$ echo "sqrt(2)" | bc -l
1.41421356237309504880
```

Exponential:
```bash
# Calculate the exponential value of a number
$ echo "e(2)" | bc -l
7.38905609893065022723
```

Sine:
```bash
# Calculate the sine of an angle (in radians)
$ echo "s(1.5)" | bc -l
.99749498660405443094
```

Logarithm:
```bash
# Calculate the logarithm of a number
$ echo "l(10)" | bc -l
2.30258509299404568401
```

Function definition within the `bc`:
```bash
# Calculate the factorial of 5
$ echo "define factorial(n) { if (n <= 1) return (1); return (n * factorial(n-1)); } factorial(5)" | bc
120
```

<a name="bc_bash_scripts"></a>
### 2. Use `bc` within Bash scripts

```bash
#!/bin/bash

function calculate_area() {
    radius=\$1
    area=$(echo "scale=2; 3.14 * $radius * $radius" | bc)
    echo "The area of the circle with radius $radius is $area"
}

calculate_area 5
```
