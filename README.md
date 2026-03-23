# Numerical Methods Library

## Description
A C++ library implementing common numerical methods.

## Structure
```
biblioteczka/
├── include/           # header files
├── src/               # implementations
├── tests/             # unit tests
├── examples/          # usage examples
├── CMakeLists.txt     # cmake
├── Makefile           # make
└── README.md          # documentation
```

## Features

### Linear Systems
- `gauss_elimination(A, b)` - Gaussian elimination
  - A: coefficient matrix
  - b: constant vector
  - returns: solution vector
- `lu_decomposition(A, b)` - LU decomposition
  - A: coefficient matrix
  - b: constant vector
  - returns: solution vector
### Interpolation
- `lagrange_interpolation(x, y, xi)` - Lagrange interpolation
  - x, y: data point vectors
  - xi: interpolation point
  - returns: interpolated value
- `newton_interpolation(x, y, xi)` - Newton interpolation
  - x, y: data point vectors
  - xi: interpolation point
  - returns: interpolated value
### Approximation
- `least_squares_approximation(x, y, degree)` - least squares approximation
  - x, y: data point vectors
  - degree: polynomial degree
  - returns: coefficient vector
### Numerical Integration
- `rectangle_method(f, a, b, n)` - rectangle rule
- `trapezoidal_method(f, a, b, n)` - trapezoidal rule
- `simpson_method(f, a, b, n)` - Simpson's rule
- `gauss_legendre_2/3/4(f, a, b)` - Gauss-Legendre quadrature
  - f: function to integrate
  - a, b: integration bounds
  - n: number of subintervals
  - returns: integral value
### Differential Equations
- `euler_method(f, x0, y0, h, n)` - Euler's method
- `heun_method(f, x0, y0, h, n)` - Heun's method
- `midpoint_method(f, x0, y0, h, n)` - midpoint method
- `runge_kutta_4(f, x0, y0, h, n)` - 4th-order Runge-Kutta
  - f: right-hand side function y' = f(x,y)
  - x0, y0: initial conditions
  - h: step size
  - n: number of steps
  - returns: vector of solution values
### Nonlinear Equations
- `newton_method(f, df, x0, tol, max_iter)` - Newton's method
  - f: function
  - df: derivative of the function
  - x0: starting point
  - tol: tolerance
  - max_iter: maximum number of iterations
  - returns: root
- `secant_method(f, x0, x1, tol, max_iter)` - secant method
  - f: function
  - x0, x1: starting points
  - tol: tolerance
  - max_iter: maximum number of iterations
  - returns: root
- `bisection_method(f, a, b, tol, max_iter)` - bisection method
  - f: function
  - a, b: interval
  - tol: tolerance
  - max_iter: maximum number of iterations
  - returns: root

  
## Building

### CMake
```bash
mkdir build && cd build
cmake ..
make
```

### Make
```bash
make all
make tests
make examples
make run-tests
```

## Usage
```cpp
#include "linear_systems.h"
#include "interpolation.h"
vector<vector<double>> A = {{2, 1}, {1, 3}};
vector<double> b = {3, 4};
vector<double> x = gauss_elimination(A, b);
vector<double> px = {0, 1, 2};
vector<double> py = {1, 2, 5};
double val = lagrange_interpolation(px, py, 1.5);
```
