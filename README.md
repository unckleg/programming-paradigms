![Programming paradigms](assets/programming-paradigms.jpg)

Programming paradigms are a way to classify programming languages based on their features. Languages can be classified into multiple paradigms.

# Overview
![Programming paradigms](assets/peter-van-roy.jpg)

Overview of the various programming paradigms according to Peter Van Roy.

Just as software engineering (as a process) is defined by differing methodologies, so the programming languages (as models of computation) are defined by differing paradigms. Some languages are designed to support one paradigm (Smalltalk supports object-oriented programming, Haskell supports functional programming), while other programming languages support multiple paradigms (such as Object Pascal, C++, Java, JavaScript, C#, Scala, Visual Basic, Common Lisp, Scheme, Perl, PHP, Python, Ruby, Wolfram Language, Oz, and F#). For example, programs written in C++, Object Pascal or PHP can be purely procedural, purely object-oriented, or can contain elements of both or other paradigms. Software designers and programmers decide how to use those paradigm elements.

In object-oriented programming, programs are treated as a set of interacting objects. In functional programming, programs are treated as a sequence of stateless function evaluations. When programming computers or systems with many processors, in process-oriented programming, programs are treated as sets of concurrent processes that act on a logical shared data structures.

Many programming paradigms are as well known for the techniques they forbid as for those they enable. For instance, pure functional programming disallows use of side-effects, while structured programming disallows use of the goto statement. Partly for this reason, new paradigms are often regarded as doctrinaire or overly rigid by those accustomed to earlier styles. Yet, avoiding certain techniques can make it easier to understand program behavior, and to prove theorems about program correctness.

Programming paradigms can also be compared with programming models which allow invoking an execution model by using only an API. Programming models can also be classified into paradigms, based on features of the execution model.

For parallel computing, using a programming model instead of a language is common. The reason is that details of the parallel hardware leak into the abstractions used to program the hardware. This causes the programmer to have to map patterns in the algorithm onto patterns in the execution model (which have been inserted due to leakage of hardware into the abstraction). As a consequence, no one parallel programming language maps well to all computation problems. It is thus more convenient to use a base sequential language and insert API calls to parallel execution models, via a programming model. Such parallel programming models can be classified according to abstractions that reflect the hardware, such as shared memory, distributed memory with message passing, notions of place visible in the code, and so forth. These can be considered flavors of programming paradigm that apply to only parallel languages and programming models.

# Programming paradigms
<!--ts-->
   * [Action](#action-language)
   * [Agent-oriented](#agent-oriented)
   * [Array-oriented](#array-oriented)
   * [Automata-based](#automata-based)
   * [Concurrent computing](#concurrent-computing)
     * [Relativistic programming](#relativistic-programming)
   * [Data-driven](#data-driven)
   * [Declarative (contrast: Imperative)](#declarative)
     * [Functional](#functional)
       * [Functional logic](#functional-logic)
       * [Purely functional](#purely-functional)
     * [Logic](#logic)
         * [Abductive logic](#abductive-logic)
         * [Answer set](#answer-set)
         * [Concurrent logic](#concurrent-logic)
         * [Functional Logic](#functional-logic)
         * [Inductive logic](#inductive-logic)
     * [Constraint](#constraint)
         * [Constraint logic](#constraint-logic)
           * [Concurrent constraint logic](#concurrent-constraint-logic)
     * [Dataflow](#dataflow)
       * [Flow based](#flow-based)
       * [Reactive](#reactive)
     * [Ontology](#ontology)
   * [Differentiable](#differentiable)
   * [Dynamic/scripting](#dynamic-scripting)
   * [Event-driven](#event-driven)
   * [Function-level (contrast: Value-level)](#function-level)
     * [Point-free style](#point-free-style)
       * [Concatenative](#concatenative)
   * [Generic](#generic)
   * [Imperative (contrast: Declarative)](#imperative)
     * [Procedural](#procedural)
     * [Object-oriented](#object-oriented)
       * [Polymorphic](#polymorphic)
   * [Intentional](#intentional)
   * [Language-oriented](#language-oriented)
     * [Domain-specific](#domain-specific)
   * [Literate](#literate)
   * [Natural-language programming](#natural-language-programming)
   * [Metaprogramming](#metaprogramming)
     * [Automatic](#domain-specific)
       * [Inductive programming](#inductive-programming)
     * [Reflective](#domain-specific)
       * [Attribute-oriented](#attribute-oriented)
     * [Macro](#macro)
     * [Template](#template)
   * [Non-structured (contrast: Structured)](#non-structured)
     * [Array](#array)
   * [Nondeterministic](#Nondeterministic)
     * [Process-oriented](#process-oriented)
   * [Probabilistic](#probilistic)
   * [Quantum](#quantum)
   * [Set-theoretic](#set-theoretic)
   * [Stack-based](#stack-based)
   * [Structured (contrast: Non-structured)](#structured)
     * [Block-oriented](#block-oriented)
       * [Structured concurrency](#structured-concurrency)
     * [Object-oriented](#object-oriented)
       * [Actor-based](#actor-based)
       * [Class-based](#class-based)
       * [Concurrent](#concurrent)
       * [Prototype-based](#prototype-based)
       * [By separation of concerns](#by-separation-of-concerns)
         * [Aspect-oriented](#process-oriented)
         * [Role-oriented](#process-oriented)
         * [Subject-oriented](#process-oriented)
     * [Recursive](#recursive)
   * [Symbolic](#symbolic)
   * [Value-level (contrast: Function-level)](#value-level)
<!--te-->

Action Language
============
In computer science, an action language is a language for specifying state transition systems, and is commonly used to create formal models of the effects of actions on the world. Action languages are commonly used in the artificial intelligence and robotics domains, where they describe how actions affect the states of systems over time, and may be used for automated planning.

Action languages fall into two classes: action description languages and action query languages. Examples of the former include STRIPS, PDDL, Language A (a generalization of STRIPS; the propositional part of Pednault's ADL), Language B (an extension of A adding indirect effects, distinguishing static and dynamic laws) and Language C (which adds indirect effects also, and does not assume that every fluent is automatically "inertial"). There are also the Action Query Languages P, Q and R. Several different algorithms exist for converting action languages, and in particular, action language C, to answer set programs. Since modern answer-set solvers make use of boolean SAT algorithms to very rapidly ascertain satisfiability, this implies that action languages can also enjoy the progress being made in the domain of boolean SAT solving.

Agent Oriented
============
Agent-oriented programming (AOP) is a programming paradigm where the construction of the software is centered on the concept of software agents. In contrast to object-oriented programming which has objects (providing methods with variable parameters) at its core, AOP has externally specified agents (with interfaces and messaging capabilities) at its core. They can be thought of as abstractions of objects. Exchanged messages are interpreted by receiving "agents", in a way specific to its class of agents.

Historically, the concept of agent-oriented programming and the idea of centering software around the concept of an Agent was introduced by Yoav Shoham within his Artificial Intelligence studies in 1990. His agents are specific to his own paradigm as they have just one method, with a single parameter. To quote Yoav Shoham from his paper in 1990 for a basic difference between AOP and OOP:

...agent-oriented programming (AOP), which can be viewed as a specialization of object-oriented programming. ...

![Agent Oriented Table](assets/agent-oriented-table.png)

Frameworks
-----
There are multiple AOP 'frameworks', also called agent platforms, that implement Shoham's programming paradigm. The following examples illustrate how a basic agent is programmed as a hello-world program.

**JADE**

For the Java-platform one of the frameworks is JADE (https://web.archive.org/web/20100621141053/http://jade.tilab.com/). Here is a very basic example of an agent that runs code

```jade
package helloworld;
import jade.core.Agent;

public class Hello extends Agent {

    protected void setup() { 
        System.out.println("Hello World. ");
        System.out.println("My name is "+ getLocalName()); 
    }
	
    public Hello() {
        System.out.println("Constructor called");
    }
}
```
At the core of JADE's AOP model is that its API supports the standard FIPA Agent Communication Language

**Agent Speak (Jason)**

For a literal translation of agent-oriented concepts into a scheme unobfuscated as is JADE, behind Java and Object Orientedness, Agent Speak (Jason) provides a "natural" language for agents.

```
    started.
    +started <- .print("Hello World. ").
```

**GOAL**

GOAL is an agent programming language for programming cognitive agents. GOAL agents derive their choice of action from their beliefs and goals. The language provides the basic building blocks to design and implement cognitive agents by programming constructs that allow and facilitate the manipulation of an agent's beliefs and goals and to structure its decision-making. The language provides an intuitive programming framework based on common sense or practical reasoning.

**SARL Language**

SARL provides the fundamental abstractions for coding multi-agent systems. It uses a script-like syntax (inspired by Scala and Ruby).

```jade
package helloworld
import io.sarl.core.Initialize

agent HelloWorldAgent {
    on Initialize {	
        println("Hello World.")
    }
}
```

Middleware
-----
One way to implement modular or extensible AOP support is to define standard AOP APIs to middleware functions that are themselves implemented as software agents. For example, a directory service can be implemented as a FIPA directory facilitator or DF software agent; life-cycle management to start, stop, suspend and resume agents can be implemented as a FIPA Agent Management Service or AMS agent. A benefit of the AOP approach is that it supports more dynamic roles between different users and providers of applications, services and networks. For example, traditionally, networks and services were usually managed by the network and service provider on behalf of the customer and offered as a single virtual network service but customers themselves are becoming more empowered to integrate and manage their own services. This can be achieved via AOP and APIs to middleware agents that can flexibly and dynamically manage communication.


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

Automata-based programming
============
Automata-based programming is a programming paradigm in which the program or part of it is thought of as a model of a finite-state machine (FSM) or any other (often more complicated) formal automaton (see automata theory). Sometimes a potentially infinite set of possible states is introduced, and such a set can have a complicated structure, not just an enumeration.

Finite-state machine-based programming is generally the same, but, formally speaking, does not cover all possible variants, as FSM stands for finite-state machine, and automata-based programming does not necessarily employ FSMs in the strict sense.

The following properties are key indicators for automata-based programming:

The time period of the program's execution is clearly separated down to the automaton steps. Each step is effectively an execution of a code section (same for all the steps) which has a single entry point. That section might be divided down to subsections to be executed depending on different states, although this is not necessary.
Any communication between the automaton steps is only possible via the explicitly noted set of variables named the automaton state. Between any two steps, the program cannot have implicit components of its state, such as local variables' values, return addresses, the current instruction pointer, etc. That is, the state of the whole program, taken at any two moments of entering an automaton step, can only differ in the values of the variables being considered as the automaton state.
The whole execution of the automata-based code is a cycle of the automaton steps.

Another reason for using the notion of automata-based programming is that the programmer's style of thinking about the program in this technique is very similar to the style of thinking used to solve mathematical tasks using Turing machines, Markov algorithms, etc.

Example task
-----
Consider the task of reading a text from standard input line-by-line and writing the first word of each line to standard output. First we skip all leading whitespace characters, if any. Then we print all the characters of the first word. Finally we skip all the trailing characters until a newline character is encountered. Whenever a sequence of newline characters is encountered not at the beginning of the stream, we print only the first one and skip the remaining ones; else, we skip all. Next we restart the process at the following line. Upon encountering the end-of-file condition (regardless of the stage), we stop.

Traditional program
-----
A traditional program in C which performs the above task could look like this:
```
#include <ctype.h>
#include <stdio.h>


int main(void) {
  int c;

  do {
    do {
      c = getchar();
    } while (isspace(c));

    while (!isspace(c) && c != EOF) {
      putchar(c);
      c = getchar();
    }
    
    while (c != '\n' && c != EOF) {
      c = getchar();
    }
    
    if (c == '\n') {
      putchar(c);
    }
  } while (c != EOF);

  return 0;
}
```
For instance, compiling and running the above program on this input:
```
$ clang program.c && (printf "\t\v\f\r \n\n\t\v\f\r foo bar baz\n\n\t\v\f\r qux quux corge" | ./a.out)
```
yields:
```
foo
qux
```

Automata-based program
-----

Procedural
-----
The same task can be solved by thinking in terms of finite-state machines. Note that the parsing of a line has three stages: skipping the leading whitespace characters, printing the characters of the first word and skipping the trailing characters. Let's call these automaton states BEFORE, INSIDE and AFTER. An automata-based version of the program could look like this:
```
#include <ctype.h>
#include <stdio.h>

enum State {BEFORE, INSIDE, AFTER};

int main(void) {
  int c;
  enum State s = BEFORE;

  while ((c = getchar()) != EOF) {
    switch (s) {
      case BEFORE:
        if (!isspace(c)) {
          putchar(c);
          s = INSIDE;
        }
        
        break;
      case INSIDE:
        if (c == '\n') {
          putchar(c);
          s = BEFORE;
        } else if (isspace(c)) {
          s = AFTER;
        } else {
          putchar(c);
        }
          
        break;
      case AFTER:
        if (c == '\n') {
          putchar(c);
          s = BEFORE;
        }
        
        break;
    }
  }

  return 0;
}
```
Although the program now looks longer, it has at least one significant advantage: there is only one reading (that is, call to the getchar function) instruction. Besides that, there is only one loop instead of the four the traditional version had. The body of the while loop is the automaton step and the loop itself is the cycle of the automaton step. The program implements the work of a finite-state machine shown in the state diagram.

The most important property of the program is that the automaton step code section is clearly localized. With an explicit function step for the automation step, the program better demonstrates this property:

```
#include <stdio.h>

enum State {BEFORE, INSIDE, AFTER};

void step(enum State* const s, int const c) {
  switch (*s) {
    case BEFORE:
      if (!isspace(c)) {
        putchar(c);
        *s = INSIDE;
      }
      
      break;
    case INSIDE:
      if (c == '\n') {
        putchar(c);
        *s = BEFORE;
      } else if (isspace(c)) {
        *s = AFTER;
      } else {
        putchar(c);
      }
        
      break;
    case AFTER:
      if (c == '\n') {
        putchar(c);
        *s = BEFORE;
      }
      
      break;
  }
}


int main(void) {
  int c;
  enum State s = BEFORE;

  while ((c = getchar()) != EOF) {
    step(&s, c);
  }

  return 0;
}
```

The program now clearly demonstrates the basic properties of automata-based code:

- time periods of automaton step executions may not overlap;
- the only information passed from the previous step to the next is the explicitly specified automaton state.

A finite automaton can be defined by a state-transition table whose rows stand for the current states, columns stand for the inputs, and cells stand for the next states and actions to perform.

State-transition table
-----
![State-transition table](assets/state-transition-table.png)

State diagram
-----
![State diagram](assets/state-machine-diag.png)

Generally speaking, an automata-based program can naturally use this approach. With an explicit two-dimensional array transitions for the state-transition table, the program uses this approach:
```
#include <ctype.h>
#include <stdio.h>

enum State {BEFORE, INSIDE, AFTER};


void nop(int const c) {}


void print(int const c) {
  putchar(c);
}


struct Branch {
  enum State const next_state;
  void (*action)(int);
};


struct Branch const transitions[3][3] = {
  //   newline         whitespace         other             Inputs/States
  {{BEFORE,   &nop}, {BEFORE, &nop}, {INSIDE, &print}},  // before
  {{BEFORE, &print}, {AFTER,  &nop}, {INSIDE, &print}},  // inside
  {{BEFORE, &print}, {AFTER,  &nop}, {AFTER,    &nop}}   // after
};


void step(enum State* const s, int const c) {
  int const row = (*s == BEFORE) ? 0 : (*s == INSIDE) ? 1 : 2;
  int const column = (c == '\n') ? 0 : isspace(c) ? 1 : 2;
  struct Branch const* const b = &transitions[row][column];
  *s = b->next_state;
  b->action(c);
}


int main(void) {
  int c;
  enum State s = BEFORE;

  while ((c = getchar()) != EOF) {
    step(&s, c);
  }

  return 0;
}
```

Object-oriented
-----
If the implementation language supports object-oriented programming, a simple refactoring of the program is to encapsulate the automaton into an object, thus hiding its implementation details. The program in C++ using object-oriented style could look like this:
```
#include <stdio.h>

enum State {BEFORE, INSIDE, AFTER};


struct Branch {
  enum State const next_state;
  void (*action)(int);
};


class StateMachine {
  public:
    StateMachine();
    void feedChar(int);

  protected:
    static void nop(int);
    static void print(int);

  private:
    enum State _state;
    static struct Branch const _transitions[3][3];
};


StateMachine::StateMachine(): _state(BEFORE) {}


void StateMachine::feedChar(int const c) {
  int const row = (_state == BEFORE) ? 0 : (_state == INSIDE) ? 1 : 2;
  int const column = (c == '\n') ? 0 : isspace(c) ? 1 : 2;
  struct Branch const* const b = &_transitions[row][column];
  _state = b->next_state;
  b->action(c);
}


void StateMachine::nop(int const c) {}


void StateMachine::print(int const c) {
  putchar(c);
}


struct Branch const StateMachine::_transitions[3][3] = {
  //   newline         whitespace         other             Inputs/States
  {{BEFORE,   &nop}, {BEFORE, &nop}, {INSIDE, &print}},  // before
  {{BEFORE, &print}, {AFTER,  &nop}, {INSIDE, &print}},  // inside
  {{BEFORE, &print}, {AFTER,  &nop}, {AFTER,    &nop}}   // after
};


int main() {
  int c;
  StateMachine m;

  while ((c = getchar()) != EOF) {
    m.feedChar(c);
  }

  return 0;
}
```
Note. — To minimize changes not directly related to the subject of the article, the input/output getchar and putchar functions from the standard library of C are being used.

The state design pattern is a way for an object to change its behavior at runtime according to its internal state without resorting to large conditional statements or table lookups thanks to virtual function calls. Its main advantage over code using large conditional statements is that state-specific code is distributed across different objects rather than localized in a monolithic block, which improves maintainability. Its main advantages over code using state-transition tables are that virtual function calls are often more efficient than table lookups, that state-transition criteria are more explicit than in tabular format, and that it is easier to add actions accompanying state transitions. However it introduces a new problem: the number of classes makes the code less compact than the other approaches. The program using the state design pattern could look like this:
```
#include <stdio.h>

class StateMachine;


class State {
  public:
    virtual void feedChar(StateMachine*, int) const = 0;
};


class Before: public State {
  public:
    static State const* instantiate();
    virtual void feedChar(StateMachine*, int) const override;

  protected:
    Before() = default;

  private:
    static State const* _instance;
};


class Inside: public State {
  public:
    static State const* instantiate();
    virtual void feedChar(StateMachine*, int) const override;

  protected:
    Inside() = default;

  private:
    static State const* _instance;
};


class After: public State {
  public:
    static State const* instantiate();
    virtual void feedChar(StateMachine*, int) const override;

  protected:
    After() = default;

  private:
    static State const* _instance;
};


class StateMachine {
  public:
    StateMachine();
    void feedChar(int);

  protected:
    void setState(State const*);

  private:
    State const* _state;
    friend class Before;
    friend class Inside;
    friend class After;
};


State const* Before::instantiate() {
  if (!_instance) {
    _instance = new Before;
  }

  return _instance;
}


void Before::feedChar(StateMachine* const m, int const c) const {
  if (!isspace(c)) {
    putchar(c);
    m->setState(Inside::instantiate());
  }
}


State const* Before::_instance = nullptr;


State const* Inside::instantiate() {
  if (!_instance) {
    _instance = new Inside;
  }

  return _instance;
}


void Inside::feedChar(StateMachine* const m, int const c) const {
  if (c == '\n') {
    putchar(c);
    m->setState(Before::instantiate());
  } else if (isspace(c)) {
    m->setState(After::instantiate());
  } else {
    putchar(c);
  }
}


State const* Inside::_instance = nullptr;


State const* After::instantiate() {
  if (!_instance) {
    _instance = new After;
  }

  return _instance;
}


void After::feedChar(StateMachine* const m, int const c) const {
  if (c == '\n') {
    putchar(c);
    m->setState(Before::instantiate());
  }
}


State const* After::_instance = nullptr;


StateMachine::StateMachine(): _state(Before::instantiate()) {}


void StateMachine::feedChar(int const c) {
  _state->feedChar(this, c);
}


void StateMachine::setState(State const* const s) {
  _state = s;
}


int main() {
  int c;
  StateMachine m;

  while ((c = getchar()) != EOF) {
    m.feedChar(c);
  }

  return 0;
}
```

Automation and automata
-----
Automata-based programming indeed closely matches the programming needs found in the field of automation.

A production cycle is commonly modelled as:

- a sequence of stages stepping according to input data (from captors);
- a set of actions performed depending on the current stage.

Various dedicated programming languages allow expressing such a model in more or less sophisticated ways.

Automation program
-----
The example presented above could be expressed according to this view like in the following pseudo-code ('set' activates a logic variable, 'reset' inactivates a logic variable, ':' assigns a variable, and '=' tests for equality):
```
newline: '\n'
whitespace: ('\t', '\n', '\v', '\f', '\r', ' ')
states: (before, inside, after)


setState(c) {
  if before and (c != newline and c not in whitespace) then set inside
  if inside then (if c in whitespace then set after else if c = newline then set before)
  if after and c = newline then set before
}


doAction(c) {
  if before and (c != newline and c not in whitespace) then write(c)
  if inside and c not in whitespace then write(c)
  if after and c = newline then write(c)
}


cycle {
  set before

  loop until (c: readCharacter) = EOL {
    setState(c)
    doAction(c)
  }
}
```
The separation of routines expressing cycle progression on one side, and actual action on the other (matching input and output) allows clearer and simpler code.

Events
-----
In the field of automation, stepping from step to step depends on input data coming from the machine itself. This is represented in the program by reading characters from a text. In reality, those data inform about position, speed, temperature, etc. of critical elements of a machine.

Like in GUI programming, changes in the machine state can thus be considered as events causing the passage from a state to another, until the final one is reached. The combination of possible states can generate a wide variety of events, thus defining a more complex production cycle. As a consequence, cycles are usually far to be simple linear sequences. There are commonly parallel branches running together and alternatives selected according to different events, schematically represented below:
```
   s:stage   c:condition
   
   s1
   |
   |-c2
   |
   s2
   |
   ----------
   |        |
   |-c31    |-c32
   |        |
  s31       s32
   |        |
   |-c41    |-c42
   |        |
   ----------
   |
   s4
```

Applications
-----
Automata-based programming is widely used in lexical and syntactic analyses.

Besides that, thinking in terms of automata (that is, breaking the execution process down to automaton steps and passing information from step to step through the explicit automaton state) is necessary for event-driven programming as the only alternative to using parallel processes or threads.

The notions of states and state machines are often used in the field of formal specification. For instance, UML-based software architecture development uses state diagrams to specify the behaviour of the program. Also various communication protocols are often specified using the explicit notion of state (e.g., RFC 793).

Thinking in terms of automata (steps and states) can also be used to describe semantics of some programming languages. For example, the execution of a program written in the Refal language is described as a sequence of steps of a so-called abstract Refal machine; the state of the machine is a view (an arbitrary Refal expression without variables).

Continuations in the Scheme language require thinking in terms of steps and states, although Scheme itself is in no way automata-related (it is recursive). To make it possible for the call/cc feature to work, implementation needs to be able to catch a whole state of the executing program, which is only possible when there is no implicit part in the state. Such a caught state is the very thing called continuation, and it can be considered as the state of a (relatively complicated) automaton. The automaton step is deducing the next continuation from the previous one, and the execution process is the cycle of such steps.

Alexander Ollongren in his book explains the so-called Vienna method of programming languages semantics description which is fully based on formal automata.

The STAT system is a good example of using the automata-based approach; this system, besides other features, includes an embedded language called STATL which is purely automata-oriented.

History
-----
Automata-based techniques were used widely in the domains where there are algorithms based on automata theory, such as formal language analyses.

One of the early papers on this is by Johnson et al., 1968.

One of the earliest mentions of automata-based programming as a general technique is found in the paper by Peter Naur, 1963. The author calls the technique Turing machine approach, however no real Turing machine is given in the paper; instead, the technique based on steps and states is described.

Comparison with imperative and procedural programming
-----
The notion of state is not exclusive property of automata-based programming. Generally speaking, state (or program state) appears during execution of any computer program, as a combination of all information that can change during the execution. For instance, a state of a traditional imperative program consists of

- values of all variables and the information stored within dynamic memory;
- values stored in registers;
- stack contents (including local variables' values and return addresses);
- current value of the instruction pointer.

These can be divided to the explicit part (such as values stored in variables) and the implicit part (return addresses and the instruction pointer).

Having said this, an automata-based program can be considered as a special case of an imperative program, in which implicit part of the state is minimized. The state of the whole program taken at the two distinct moments of entering the step code section can differ in the automaton state only. This simplifies the analysis of the program.

Object-oriented programming relationship
-----
In the theory of object-oriented programming, an object is said to have an internal state and is capable of receiving messages, responding to them, sending messages to other objects and changing its internal state during message handling. In more practical terminology, to call an object's method is considered the same as to send a message to the object.

Thus, on the one hand, objects from object-oriented programming can be considered as automata (or models of automata) whose state is the combination of private fields, and one or more methods are considered to be the step. Such methods must not call each other nor themselves, neither directly nor indirectly, otherwise the object can not be considered to be implemented in an automata-based manner.

On the other hand, object is good for implementing a model of an automaton. When the automata-based approach is used within an object-oriented language, an automaton model is usually implemented by a class, the state is represented with private fields of the class, and the step is implemented as a method; such a method is usually the only non-constant public method of the class (besides constructors and destructors). Other public methods could query the state but don't change it. All the secondary methods (such as particular state handlers) are usually hidden within the private part of the class.
