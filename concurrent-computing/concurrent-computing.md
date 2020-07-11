Concurrent computing
============

Concurrent computing is a form of computing in which several computations are executed concurrently—during overlapping time periods—instead of sequentially, with one completing before the next starts.

This is a property of a system—whether a program, computer, or a network—where there is a separate execution point or "thread of control" for each process. A concurrent system is one where a computation can advance without waiting for all other computations to complete.

Concurrent computing is a form of modular programming. In its paradigm an overall computation is factored into subcomputations that may be executed concurrently. Pioneers in the field of concurrent computing include Edsger Dijkstra, Per Brinch Hansen, and C.A.R. Hoare.

Introduction
-----
The concept of concurrent computing is frequently confused with the related but distinct concept of parallel computing, although both can be described as "multiple processes executing during the same period of time". In parallel computing, execution occurs at the same physical instant: for example, on separate processors of a multi-processor machine, with the goal of speeding up computations—parallel computing is impossible on a (one-core) single processor, as only one computation can occur at any instant (during any single clock cycle).
 
By contrast, concurrent computing consists of process lifetimes overlapping, but execution need not happen at the same instant. The goal here is to model processes in the outside world that happen concurrently, such as multiple clients accessing a server at the same time. Structuring software systems as composed of multiple concurrent, communicating parts can be useful for tackling complexity, regardless of whether the parts can be executed in parallel.

For example, concurrent processes can be executed on one core by interleaving the execution steps of each process via time-sharing slices: only one process runs at a time, and if it does not complete during its time slice, it is paused, another process begins or resumes, and then later the original process is resumed. In this way, multiple processes are part-way through execution at a single instant, but only one process is being executed at that instant.

Concurrent computations may be executed in parallel, for example, by assigning each process to a separate processor or processor core, or distributing a computation across a network. In general, however, the languages, tools, and techniques for parallel programming might not be suitable for concurrent programming, and vice versa.

The exact timing of when tasks in a concurrent system are executed depend on the scheduling, and tasks need not always be executed concurrently. For example, given two tasks, T1 and T2:

- T1 may be executed and finished before T2 or vice versa (serial and sequential)
- T1 and T2 may be executed alternately (serial and concurrent)
- T1 and T2 may be executed simultaneously at the same instant of time (parallel and concurrent)

The word "sequential" is used as an antonym for both "concurrent" and "parallel"; when these are explicitly distinguished, concurrent/sequential and parallel/serial are used as opposing pairs. A schedule in which tasks execute one at a time (serially, no parallelism), without interleaving (sequentially, no concurrency: no task begins until the prior task ends) is called a serial schedule. A set of tasks that can be scheduled serially is serializable, which simplifies concurrency control.

Coordinating access to shared resources
-----
The main challenge in designing concurrent programs is concurrency control: ensuring the correct sequencing of the interactions or communications between different computational executions, and coordinating access to resources that are shared among executions. Potential problems include race conditions, deadlocks, and resource starvation. For example, consider the following algorithm to make withdrawals from a checking account represented by the shared resource balance:
```
bool withdraw(int withdrawal)
{
    if (balance >= withdrawal)
    {
        balance -= withdrawal;
        return true;
    } 
    return false;
}
```
Suppose balance = 500, and two concurrent threads make the calls withdraw(300) and withdraw(350). If line 3 in both operations executes before line 5 both operations will find that balance >= withdrawal evaluates to true, and execution will proceed to subtracting the withdrawal amount. However, since both processes perform their withdrawals, the total amount withdrawn will end up being more than the original balance. These sorts of problems with shared resources benefit from the use of concurrency control, or non-blocking algorithms.

The advantages of concurrent computing include:

- Increased program throughput—parallel execution of a concurrent program allows the number of tasks completed in a given time to increase proportionally to the number of processors according to Gustafson's law
- High responsiveness for input/output—input/output-intensive programs mostly wait for input or output operations to complete. Concurrent programming allows the time that would be spent waiting to be used for another task.
- More appropriate program structure—some problems and problem domains are well-suited to representation as concurrent tasks or processes.

Models
-----
- Models for understanding and analyzing concurrent computing systems include:
  - Actor model
- Object-capability model for security
- Input/output automaton
- Software transactional memory (STM)
- Petri nets
- Process calculi such as
  - Ambient calculus
  - Calculus of communicating systems (CCS)
  - Communicating sequential processes (CSP)
  - Join-calculus
  - π-calculus

Implementation
-----
A number of different methods can be used to implement concurrent programs, such as implementing each computational execution as an operating system process, or implementing the computational processes as a set of threads within a single operating system process.

Interaction and communication
-----
In some concurrent computing systems, communication between the concurrent components is hidden from the programmer (e.g., by using futures), while in others it must be handled explicitly. Explicit communication can be divided into two classes:

Shared memory communication
-----
Concurrent components communicate by altering the contents of shared memory locations (exemplified by Java and C#). This style of concurrent programming usually needs the use of some form of locking (e.g., mutexes, semaphores, or monitors) to coordinate between threads. A program that properly implements any of these is said to be thread-safe.

Message passing communication
-----
Concurrent components communicate by exchanging messages (exemplified by MPI, Go, Scala, Erlang and occam). The exchange of messages may be carried out asynchronously, or may use a synchronous "rendezvous" style in which the sender blocks until the message is received. Asynchronous message passing may be reliable or unreliable (sometimes referred to as "send and pray"). Message-passing concurrency tends to be far easier to reason about than shared-memory concurrency, and is typically considered a more robust form of concurrent programming. A wide variety of mathematical theories to understand and analyze message-passing systems are available, including the actor model, and various process calculi. Message passing can be efficiently implemented via symmetric multiprocessing, with or without shared memory cache coherence.

Shared memory and message passing concurrency have different performance characteristics. Typically (although not always), the per-process memory overhead and task switching overhead is lower in a message passing system, but the overhead of message passing is greater than for a procedure call. These differences are often overwhelmed by other performance factors.

History
-----
Concurrent computing developed out of earlier work on railroads and telegraphy, from the 19th and early 20th century, and some terms date to this period, such as semaphores. These arose to address the question of how to handle multiple trains on the same railroad system (avoiding collisions and maximizing efficiency) and how to handle multiple transmissions over a given set of wires (improving efficiency), such as via time-division multiplexing (1870s).

The academic study of concurrent algorithms started in the 1960s, with Dijkstra (1965) credited with being the first paper in this field, identifying and solving mutual exclusion.

Prevalence
-----
Concurrency is pervasive in computing, occurring from low-level hardware on a single chip to worldwide networks. Examples follow.

At the programming language level:
- Channel
- Coroutine
- Futures and promises

At the operating system level:

- Computer multitasking, including both cooperative multitasking and preemptive multitasking
  - Time-sharing, which replaced sequential batch processing of jobs with concurrent use of a system
- Process
- Thread

At the network level, networked systems are generally concurrent by their nature, as they consist of separate devices.

Languages supporting concurrent programming
-----
Concurrent programming languages are programming languages that use language constructs for concurrency. These constructs may involve multi-threading, support for distributed computing, message passing, shared resources (including shared memory) or futures and promises. Such languages are sometimes described as concurrency-oriented languages or concurrency-oriented programming languages (COPL).

Today, the most commonly used programming languages that have specific constructs for concurrency are Java and C#. Both of these languages fundamentally use a shared-memory concurrency model, with locking provided by monitors (although message-passing models can and have been implemented on top of the underlying shared-memory model). Of the languages that use a message-passing concurrency model, Erlang is probably the most widely used in industry at present.

Many concurrent programming languages have been developed more as research languages (e.g. Pict) rather than as languages for production use. However, languages such as Erlang, Limbo, and occam have seen industrial use at various times in the last 20 years. Languages in which concurrency plays an important role include:

- Ada—general purpose, with native support for message passing and monitor based concurrency
- Alef—concurrent, with threads and message passing, for system programming in early versions of Plan 9 from Bell Labs
- Alice—extension to Standard ML, adds support for concurrency via futures
- Ateji PX—extension to Java with parallel primitives inspired from π-calculus
- Axum—domain specific, concurrent, based on actor model and .NET Common Language Runtime using a C-like syntax
- BMDFM—Binary Modular DataFlow Machine
- C++—std::thread
- Cω (C omega)—for research, extends C#, uses asynchronous communication
- C#—supports concurrent computing using lock, yield, also since version 5.0 async and await keywords introduced
- Clojure—modern, functional dialect of Lisp on the Java platform
- Concurrent Clean—functional programming, similar to Haskell
- Concurrent Collections (CnC)—Achieves implicit parallelism independent of memory model by explicitly defining flow of data and control
- Concurrent Haskell—lazy, pure functional language operating concurrent processes on shared memory
- Concurrent ML—concurrent extension of Standard ML
- Concurrent Pascal—by Per Brinch Hansen
- Curry
- D—multi-paradigm system programming language with explicit support for concurrent programming (actor model)
- E—uses promises to preclude deadlocks
- ECMAScript—uses promises for asynchronous operations
- Eiffel—through its SCOOP mechanism based on the concepts of Design by Contract
- Elixir—dynamic and functional meta-programming aware language running on the Erlang VM.
- Erlang—uses asynchronous message passing with nothing shared
- FAUST—real-time functional, for signal processing, compiler provides automatic parallelization via OpenMP or a specific work-stealing scheduler
- Fortran—coarrays and do concurrent are part of Fortran 2008 standard
- Go—for system programming, with a concurrent programming model based on CSP
- Haskell—concurrent, and parallel functional programming language
- Hume—functional, concurrent, for bounded space and time environments where automata processes are described by synchronous channels patterns and message passing
- Io—actor-based concurrency
- Janus—features distinct askers and tellers to logical variables, bag channels; is purely declarative
- Java—thread class or Runnable interface
- Julia—"concurrent programming primitives: Tasks, async-wait, Channels."
- JavaScript—via web workers, in a browser environment, promises, and callbacks.
- JoCaml—concurrent and distributed channel based, extension of OCaml, implements the join-calculus of processes
- Join Java—concurrent, based on Java language
- Joule—dataflow-based, communicates by message passing
- Joyce—concurrent, teaching, built on Concurrent Pascal with features from CSP by Per Brinch Hansen
- LabVIEW—graphical, dataflow, functions are nodes in a graph, data is wires between the nodes; includes object-oriented language
- Limbo—relative of Alef, for system programming in Inferno (operating system)
- MultiLisp—Scheme variant extended to support parallelism
- Modula-2—for system programming, by N. Wirth as a successor to Pascal with native support for coroutines
- Modula-3—modern member of Algol family with extensive support for threads, mutexes, condition variables
- Newsqueak—for research, with channels as first-class values; predecessor of Alef
- occam—influenced heavily by communicating sequential processes (CSP)
- occam-π—a modern variant of occam, which incorporates ideas from Milner's π-calculus
- Orc—heavily concurrent, nondeterministic, based on Kleene algebra
- Oz-Mozart—multiparadigm, supports shared-state and message-passing concurrency, and futures
- ParaSail—object-oriented, parallel, free of pointers, race conditions
- Pict—essentially an executable implementation of Milner's π-calculus
- Raku includes classes for threads, promises and channels by default
- Python using Stackless Python
- Reia—uses asynchronous message passing between shared-nothing objects
- Red/System—for system programming, based on Rebol
- Rust—for system programming, using message-passing with move semantics, shared immutable memory, and shared mutable memory.
- Scala—general purpose, designed to express common programming patterns in a concise, elegant, and type-safe way
- SequenceL—general purpose functional, main design objectives are ease of programming, code clarity-readability, and automatic parallelization for performance on multicore hardware, and provably free of race conditions
- SR—for research
- SuperPascal—concurrent, for teaching, built on Concurrent Pascal and Joyce by Per Brinch Hansen
- Unicon—for research
- TNSDL—for developing telecommunication exchanges, uses asynchronous message passing
- VHSIC Hardware Description Language (VHDL)—IEEE STD-1076
- XC—concurrency-extended subset of C language developed by XMOS, based on communicating sequential processes, built-in constructs for programmable I/O

Many other languages provide support for concurrency in the form of libraries, at levels roughly comparable with the above list.
