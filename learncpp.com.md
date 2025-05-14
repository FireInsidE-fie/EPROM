---
tags:
  - Tutorial
  - cpp
---
[[C++]] tutorials and learning materials.

# Progress
1.5 - `std::cin`
# Bookmarks - Stuff to remember
## 0 - Introduction
### 0.1
Don't code when you're tired or stressed out. Sort out the things that stress you out or go sleep or something. Then come back and write good code.
Tired/stressed out programmers often write bad code. Sometimes they don't, but most of the time they do. **You aren't that guy.**
### 0.2
> Platforms often provide useful services for the programs running on them. For example, a desktop application might request the operating system give them a chunk of free memory, create a file over there, or play a sound. The running program doesn’t have to know how this is actually facilitated. If a program uses capabilities or services provided by the platform, it becomes dependent on that platform, and cannot be run on other platforms without modification. A program that can be easily transferred from one platform to another is said to be **portable**. The act of modifying a program so that it runs on a different platform is called **porting**.

> Some cool info to be added to [[Assembly]].
> An **assembly language** (often called **assembly** for short) is a programming language that essentially functions as a more human-readable machine language.
> Just like each CPU family has its own machine language, each CPU family also has its own assembly language (which is designed to be assembled into machine language for that same CPU family). This means there are many different assembly languages. Although conceptually similar, different assembly languages support different instructions, use different naming conventions, etc…

> Some cool info to be added to [[Interpreter]].
> Alternatively, an **interpreter** is a program that directly executes the instructions in the source code without requiring them to be compiled first. Interpreters tend to be more flexible than compilers, but are less efficient when running programs because the interpreting process needs to be done every time the program is run. This also means the interpreter must be installed on every machine where an interpreted program will be run.
> A good comparison of the advantages of compilers vs interpreters can be found [here](https://stackoverflow.com/a/38491646).
### 0.4
Take some time to design solutions to problems before diving right in. Go to the drawing board, so to say, and conceptualize.
Maybe make an Obsidian Canvas.
Defining the problem is just as important as designing as solution.
On how to design good solutions to problems :
> Typically, good solutions have the following characteristics:
- They are straightforward (not overly complicated or confusing).
- They are well documented (especially around any assumptions being made or limitations).
- They are built modularly, so parts can be reused or changed later without impacting other parts of the program.
- They can recover gracefully or give useful error messages when something unexpected happens.\

> When you sit down and start coding right away, you’re typically thinking “I want to do ”, so you implement the solution that gets you there the fastest. This can lead to programs that are fragile, hard to change or extend later, or have lots of bugs.
## 1 - C++ Basics
### 1.2 - Comments
There are several types of comments, like the [[Doxygen]] comments found at a function's start for librairies, or the inline comments for specific parts of the code.

> [!WARNING] Good and bad comments
> In general, you'll want as a rule to not so much describe what's happening (what is already understandable by just reading the code), but rather explain **why** a line of code is the way it is.

You can also use comments to explain why a certain approach was used and not another. This prevents you from coming back to your code after a while and going "well why didn't we do it that way?".

> [!SUCCESS] Best practice
> Comment your code liberally, and write your comments as if speaking to someone who has no idea what the code does. Don’t assume you’ll remember why you made specific choices.
> - At the library, program, or function level, use comments to describe _what_.
> - Inside the library, program, or function, use comments to describe _how_.
> - At the statement level, use comments to describe _why_.
### 1.4
Apparently in [[C++]], initialization of variables is a whole thing. It's not just about saying `x = 4` anymore, you can do crazy stuff with braces, parentheseses and more.
### 1.5
Keep in mind `std::cout` is buffered, which means some output might only appear past a certain point.

# The tutorial
https://www.learncpp.com/