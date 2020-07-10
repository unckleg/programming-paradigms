Array Oriented
============
In computer science, array programming refers to solutions which allow the application of operations to an entire set of values at once. Such solutions are commonly used in scientific and engineering settings.

Modern programming languages that support array programming (also known as vector or multidimensional languages) have been engineered specifically to generalize operations on scalars to apply transparently to vectors, matrices, and higher-dimensional arrays. These include APL, J, Fortran 90, Mata, MATLAB, Analytica, TK Solver (as lists), Octave, R, Cilk Plus, Julia, Perl Data Language (PDL), Wolfram Language, and the NumPy extension to Python. In these languages, an operation that operates on entire arrays can be called a vectorized operation, regardless of whether it is executed on a vector processor (which implements vector instructions) or not. Array programming primitives concisely express broad ideas about data manipulation. The level of concision can be dramatic in certain cases: it is not uncommon to find array programming language one-liners that require more than a couple of pages of object-oriented code.

Concepts of array
-----
The fundamental idea behind array programming is that operations apply at once to an entire set of values. This makes it a high-level programming model as it allows the programmer to think and operate on whole aggregates of data, without having to resort to explicit loops of individual scalar operations.

Kenneth E. Iverson described the rationale behind array programming (actually referring to APL) as follows:

Most programming languages are decidedly inferior to mathematical notation and are little used as tools of thought in ways that would be considered significant by, say, an applied mathematician.

The thesis is that the advantages of executability and universality found in programming languages can be effectively combined, in a single coherent language, with the advantages offered by mathematical notation. it is important to distinguish the difficulty of describing and of learning a piece of notation from the difficulty of mastering its implications. For example, learning the rules for computing a matrix product is easy, but a mastery of its implications (such as its associativity, its distributivity over addition, and its ability to represent linear functions and geometric operations) is a different and much more difficult matter.

Indeed, the very suggestiveness of a notation may make it seem harder to learn because of the many properties it suggests for explorations.

Users of computers and programming languages are often concerned primarily with the efficiency of execution of algorithms, and might, therefore, summarily dismiss many of the algorithms presented here. Such dismissal would be short-sighted since a clear statement of an algorithm can usually be used as a basis from which one may easily derive a more efficient algorithm.

The basis behind array programming and thinking is to find and exploit the properties of data where individual elements are similar or adjacent. Unlike object orientation which implicitly breaks down data to its constituent parts (or scalar quantities), array orientation looks to group data and apply a uniform handling.

Function rank is an important concept to array programming languages in general, by analogy to tensor rank in mathematics: functions that operate on data may be classified by the number of dimensions they act on. Ordinary multiplication, for example, is a scalar ranked function because it operates on zero-dimensional data (individual numbers). The cross product operation is an example of a vector rank function because it operates on vectors, not scalars. Matrix multiplication is an example of a 2-rank function, because it operates on 2-dimensional objects (matrices). Collapse operators reduce the dimensionality of an input data array by one or more dimensions. For example, summing over elements collapses the input array by 1 dimension.

Uses
-----
Array programming is very well suited to implicit parallelization; a topic of much research nowadays. Further, Intel and compatible CPUs developed and produced after 1997 contained various instruction set extensions, starting from MMX and continuing through SSSE3 and 3DNow!, which include rudimentary SIMD array capabilities. Array processing is distinct from parallel processing in that one physical processor performs operations on a group of items simultaneously while parallel processing aims to split a larger problem into smaller ones (MIMD) to be solved piecemeal by numerous processors. Processors with two or more cores are increasingly common today.

Languages
-----
The canonical examples of array programming languages are Fortran, APL, and J. Others include: A+, Analytica, Chapel, IDL, Julia, K, Klong, Q, Mata, Wolfram Language, MATLAB, MOLSF, NumPy, GNU Octave, PDL, R, S-Lang, SAC, Nial and ZPL.

Scalar languages
-----
In scalar languages such as C and Pascal, operations apply only to single values, so a+b expresses the addition of two numbers. In such languages, adding one array to another requires indexing and looping, the coding of which is tedious.
```
for (i = 0; i < n; i++)
    for (j = 0; j < n; j++)
        a[i][j] += b[i][j];
```
In array-based languages, for example in Fortran, the nested for-loop above can be written in array-format in one line,

```
a = a + b
```
or alternatively, to emphasize the array nature of the objects,
```
a(:,:) = a(:,:) + b(:,:)
```

Array languages
-----
In array languages, operations are generalized to apply to both scalars and arrays. Thus, a+b expresses the sum of two scalars if a and b are scalars, or the sum of two arrays if they are arrays.

An array language simplifies programming but possibly at a cost known as the abstraction penalty. Because the additions are performed in isolation from the rest of the coding, they may not produce the optimally most efficient code. (For example, additions of other elements of the same array may be subsequently encountered during the same execution, causing unnecessary repeated lookups.) Even the most sophisticated optimizing compiler would have an extremely hard time amalgamating two or more apparently disparate functions which might appear in different program sections or sub-routines, even though a programmer could do this easily, aggregating sums on the same pass over the array to minimize overhead).

Ada
-----
The previous C code would become the following in the Ada language, which supports array-programming syntax.

```
A := A + B;
```

APL
-----
APL uses single character Unicode symbols with no syntactic sugar.
```
A ← A + B
```
This operation works on arrays of any rank (including rank 0), and on a scalar and an array. Dyalog APL extends the original language with augmented assignments:

```
A +← B
```

Analytica
-----
Analytica provides the same economy of expression as Ada.
```
A := A + B;
```

Basic
-----
Dartmouth BASIC had MAT statements for matrix and array manipulation in its third edition (1966).
```
DIM A(4),B(4),C(4)
MAT A = 1
MAT B = 2 * A
MAT C = A + B
MAT PRINT A,B,C
```

Mata
-----
Stata's matrix programming language Mata supports array programming. Below, we illustrate addition, multiplication, addition of a matrix and a scalar, element by element multiplication, subscripting, and one of Mata's many inverse matrix functions.

```
. mata:

: A = (1,2,3) \(4,5,6)

: A
       1   2   3
    +-------------+
  1 |  1   2   3  |
  2 |  4   5   6  |
    +-------------+

: B = (2..4) \(1..3)

: B
       1   2   3
    +-------------+
  1 |  2   3   4  |
  2 |  1   2   3  |
    +-------------+

: C = J(3,2,1)           // A 3 by 2 matrix of ones

: C
       1   2
    +---------+
  1 |  1   1  |
  2 |  1   1  |
  3 |  1   1  |
    +---------+

: D = A + B

: D
       1   2   3
    +-------------+
  1 |  3   5   7  |
  2 |  5   7   9  |
    +-------------+

: E = A*C

: E
        1    2
    +-----------+
  1 |   6    6  |
  2 |  15   15  |
    +-----------+

: F = A:*B

: F
        1    2    3
    +----------------+
  1 |   2    6   12  |
  2 |   4   10   18  |
    +----------------+

: G = E :+ 3

: G
        1    2
    +-----------+
  1 |   9    9  |
  2 |  18   18  |
    +-----------+

: H = F[(2\1), (1, 2)]    // Subscripting to get a submatrix of F and

:                         // switch row 1 and 2
: H
        1    2
    +-----------+
  1 |   4   10  |
  2 |   2    6  |
    +-----------+

: I = invsym(F'*F)        // Generalized inverse (F*F^(-1)F=F) of a

:                         // symmetric positive semi-definite matrix
: I
[symmetric]
                 1             2             3
    +-------------------------------------------+
  1 |            0                              |
  2 |            0          3.25                |
  3 |            0         -1.75   .9444444444  |
    +-------------------------------------------+

: end
```

MATLAB
-----
The implementation in MATLAB allows the same economy allowed by using the Fortran language.
```
A = A + B;
```
A variant of the MATLAB language is the GNU Octave language, which extends the original language with augmented assignments:
```
A += B;
```

Both MATLAB and GNU Octave natively support linear algebra operations such as matrix multiplication, matrix inversion, and the numerical solution of system of linear equations, even using the Moore–Penrose pseudoinverse.

The Nial example of the inner product of two arrays can be implemented using the native matrix multiplication operator. If a is a row vector of size [1 n] and b is a corresponding column vector of size [n 1].
```
a * b;
```
The inner product between two matrices having the same number of elements can be implemented with the auxiliary operator (:), which reshapes a given matrix into a column vector, and the transpose operator ':
```
A(:)' * B(:);
```

rasql
-----
The rasdaman query language is a database-oriented array-programming language. For example, two arrays could be added with the following query:
```
SELECT A + B
FROM   A, B
```

R
-----
The R language supports array paradigm by default. The following example illustrates a process of multiplication of two matrices followed by an addition of a scalar (which is, in fact, a one-element vector) and a vector:
```
> A
     [,1] [,2] [,3]
[1,]    1    3    5
[2,]    2    4    6
> B <- t( matrix(6:1, nrow=2) )  # t() is a transpose operator                           !!this has nrow=2 ... and B has 3 rows --- a clear contradiction to the definition of A
> B
     [,1] [,2]
[1,]    6    5
[2,]    4    3
[3,]    2    1
> C <- A %*% B
> C
     [,1] [,2]
[1,]   28   19
[2,]   40   28
> D <- C + 1
> D
     [,1] [,2]
[1,]   29   20
[2,]   41   29
> D + c(1, 1)  # c() creates a vector
     [,1] [,2]
[1,]   30   21
[2,]   42   30
```
