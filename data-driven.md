Data Driven
============
In computer programming, data-driven programming is a programming paradigm in which the program statements describe the data to be matched and the processing required rather than defining a sequence of steps to be taken. Standard examples of data-driven languages are the text-processing languages sed and AWK, where the data is a sequence of lines in an input stream – these are thus also known as line-oriented languages – and pattern matching is primarily done via regular expressions or line numbers.

Related paradigms
-----
Data-driven programming is similar to event-driven programming, in that both are structured as pattern matching and resulting processing, and are usually implemented by a main loop, though they are typically applied to different domains. The condition/action model is also similar to aspect-oriented programming, where when a join point (condition) is reached, a pointcut (action) is executed. A similar paradigm is used in some tracing frameworks such as DTrace, where one lists probes (instrumentation points) and associated actions, which execute when the condition is satisfied.

Adapting abstract data type design methods to object-oriented programming results in a data-driven design. This type of design is sometimes used in object-oriented programming to define classes during the conception of a piece of software.

Another interpretation
-----
In some programming communities, rather than programming that is oriented to processing text, data-driven programming is programming that receives some of its instructions in data form, rather than code form.

A common example is error messages. Rather than have the Product Owner maintain a spreadsheet of error codes and error messages that the programmer refers to when s/he writes his code, the program reads the spreadsheet when it starts up, and uses the error messages that it finds.

Another common example is a state machine. The programmer writes a state machine engine, but the states and the transitions between them are specified by a data file that is loaded in.

Applications
-----
Data-driven programming is typically applied to streams of structured data, for filtering, transforming, aggregating (such as computing statistics), or calling other programs. Typical streams include log files, delimiter-separated values, or email messages, notably for email filtering. For example, an AWK program may take as input a stream of log statements, and for example send all to the console, write ones starting with WARNING to a "WARNING" file, and send an email to a sysadmin in case any line starts with "ERROR". It could also record how many warnings are logged per day. Alternatively, one can process streams of delimiter-separated values, processing each line or aggregated lines, such as the sum or max. In email, a language like procmail can specify conditions to match on some emails, and what actions to take (deliver, bounce, discard, forward, etc.).

Some data-driven languages are Turing-complete, such as AWK and even sed, while others are intentionally very limited, notably for filtering. An extreme example of the latter is pcap, which only consists of filtering, with the only action being “capture”. Less extremely, sieve has filters and actions, but in the base standard has no variables or loops, only allowing stateless filtering statements: each input element is processed independently. Variables allow state, which allow operations that depend on more than one input element, such as aggregation (summing inputs) or throttling (allow at most 5 mails per hour from each sender, or limiting repeated log messages).

Data-driven languages frequently have a default action: if no condition matches, line-oriented languages may print the line (as in sed), or deliver a message (as in sieve). In some applications, such as filtering, matching is may be done exclusively (so only first matching statement), while in other cases all matching statements are applied. In either case, failure to match any pattern may be "default behavior" or can be seen as an error, to be caught by a catch-all statement at the end.

Benefits and issues
-----
While the benefits and issues may vary between implementation, there are a few big potential benefits of and problems with this paradigm. Functionality simply requires that it knows the abstract data type of the variables it is working with. Functions and interfaces can be used on all objects with the same data fields, for instance the object's "position". Data can be grouped into objects or "entities" according to preference with little to no consequence.

While data-driven design does prevent coupling of data and functionality, in some cases, data-driven programming has been argued to lead to bad object-oriented design, especially when dealing with more abstract data. This is because a purely data-driven object or entity is defined by the way it is represented. Any attempt to change the structure of the object would immediately break the functions that rely on it.

As an example, one might represent driving directions as a series of intersections (two intersecting streets) where the driver must turn right or left. If an intersection (in the United States) is represented in data by the zip code (5-digit number) and two street names (strings of text), bugs may appear when a city where streets intersect multiple times is encountered. While this example may be oversimplified, restructuring of data is a fairly common problem in software engineering, either to eliminate bugs, increase efficiency, or support new features.

Data-driven programming languages
-----
- AWK
- Oz
- Perl – data-driven programming as in AWK and sed is one paradigm supported by Perl
- sed
- Lua
- Clojure
- Tab (language)

Mail filtering languages
- fdm
- maildrop
- procmail
- Sieve
