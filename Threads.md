---
tags:
  - Unix
  - programming_concept
  - C
---
Threading is the concept of splitting the load of a particular [[Process]] across multiple [[CPU]] cores. You can have more threads than cores on most [[Operating system]]s, it's usually the OS itself that will balance the threads between the cores.

# How it works
In [[C]] programming, for example, you create a new thread using the `pthreads` library (make sure to link it with your executable using `-lpthreads`~) by specifying the function that that thread will run. Kind of like your program starts at `main`, the thread will start a function YOU specify. Within limits, of course.
You then let the thread run while the parent thread (the `main`) still works in parallel.
You can then wait for the thread to complete, by *joining* it.
A thread can `exit()` or also end its own life by returning from the "main" function you gave it.
A thread can also sleep for a period of time, not hindering other threads of a [[process]].
Threads have shared memory, allowing easy but dangerous (see below) communication between different threads.
## C Program example
Threads are identified with variables of type `thrd_t`, basically the ID of the thread (though it is an [[Opaque variable]]).
You create threads with `thrd_create()` and join them with `thrd_join()`. Pretty straightforward, except the first one takes in a pointer to the function the new thread is supposed to execute once it starts.
# Thread safety and race conditions
Since threads share their memory spaces, you can easily end up in something known as a "race condition", or "data race". In a nutshell, this is when two or more threads are trying to access and/or modify the same value at the same time. This can very easily cause said value to become completely corrupted with part of the first thread's modification and part of the second's.
Thing is, **this isn't limited to only conventional variables you might set in your code.** This is pretty much to take into account for any resource that might be shared between threads. Ring any bells? That's right! Enter the standard input and output. What if two threads try to write something to stdout at the same time? You'll end up with two outputs mixed together, resulting in a garbled output. Not something we want. That's why we have concepts such as [[Mutex]]es.

> [!WARNING] The [[C]] standard library and race conditions
> Careful with some functions in the standard library that may keep a variable somewhere to keep states! If a standard libc function keeps a state between calls, it's probably not thread safe and needs protection set around that function.

# Resources
Chapter 39 of Beej's guide to C programming
