---
layout: post
title: Scripting languages and IDEs
---

Nikolai Bezroukov has written about the efficacy of scripting languages <a href="http://www.softpanorama.org/People/Scripting_giants/scripting_languages_as_vhll.shtml">here</a>
and believes them to be the primary achievement of the open source movement. Their advantages over "system" languages such as C include compactness of code, weak (or no) typing where 
strings and numbers are easily interchangeable, and lack of need for explicit system management, such as garbage collection or memory allocation. 

The primary weakness of scripting languages is allegedly their lack of efficiency. Since they're typically interpreted, they often require the overhead of starting up the interpreter
and shutting it down. Ande since resource management is usually done behind the scenes, it may be difficult or impossible to make much improvement in this regard. Facilities that aren't
"baked into" the scripting language may also make some tasks infeasible.

To counteract this disadvanges, John Ousterhout has suggested a dual strategy of building components in a system language like C and then "gluing" them together with a scripting language.
His own language, Tcl embodies this approach.

Having said all of this, the 21st century is an era where computing resources are usually plentiful. So the argument against anything except scripting languages these days appears weaker
than ever. Why even bother C, C++, C#, and Java which require a lot more code and explicit declarations when you can use a language like Python and do metaprogramming?   

I believe that this <a href="http://wiresong.ca/air/2006/10/20/scripting-languages-and-ides">essay</a> offers at least part of the answer to this question. Languages that are strong in 
metaprogramming such as Python tend to have IDEs or IDE facilities that are more poorly developed, if they're present at all. While languages such as C#, Delphi, and Java tend to have 
very rich IDEs, with GUI tools available. They require explicit type declaration, explicit type conversion, and forbid runtime class and module definitions. But the static nature of these
languages has one important advantage - it allows an IDE that can build a compile-time model of the program, and write it back out as source code. This is literally impossible to do with
languages that allow metaprogramming since you must execute the program first to get a complete model of its structure.  

VBA falls somewhere in the middle of this classification scheme. It allows the building of sophisticated GUI widgets and compile-time generation of code. But it also tolerates usage of variables without
explicit declarations, like Python. However, it you don't declare a variable's type explicitly, the IDE is unable to offer suggestions of method or code completion. If an object has dozens of
methods with complex parameter invocation, avoiding type declarations may result in shorter code, but at the expense of cutting the developer off from one of the major advantages of IDEs.

Is there any easy way to combine the simplicity and ease of a scripting language with the IDE, sophisticated debugging facilities, and other facilities of a "system" language with explicit typing?
I believe that building a simple macro language such as CFE is a way to do this. It combines the advantages of simple syntax, ease of parameter passing, and the ability to have as much or as little
complexity as needed to get the job done with the IDE, extensive library of tools, and GUI widgets available in the Excel VBA development environment.

