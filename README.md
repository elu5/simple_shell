Unix shell

A Unix shell is a command-line interpreter or shell that provides a command line user interface for Unix-like operating systems. The shell is both an interactive command language and a scripting language, and is used by the operating system to control the execution of the system using shell scripts.

Early shells

The first Unix shell was the Thompson shell, sh, written by Ken Thompson at Bell Labs and distributed with Versions 1 through 6 of Unix, from 1971 to 1975. Though rudimentary by modern standards, it introduced many of the basic features common to all later Unix shells, including piping, simple control structures using if and go to, and filename wildcarding. Though not in current use, it is still available as part of some Ancient UNIX systems.

The PWB shell or Mashey shell, sh, was an upward-compatible version of the Thompson shell, augmented by John Mashey and others and distributed with the Programmer's Workbench UNIX, circa 1975–1977.

Bourne shell

The Bourne shell, sh, was a new Unix shell by Stephen Bourne at Bell Labs. Distributed as the shell for UNIX Version 7 in 1979, it introduced the rest of the basic features considered common to all the Unix shells, including here documents, command substitution, more generic variables and more extensive built-in control structures

The POSIX standard specifies its standard shell as a strict subset of the Korn shell, an enhanced version of the Bourne shell. From a user's perspective the Bourne shell was immediately recognized when active by its characteristic default command line prompt character, the dollar sign ($).

C shell

The C shell, csh, was modeled on the C programming language, including the control structures and the expression grammar. It was written by Bill Joy as a graduate student at University of California, Berkeley, and was widely distributed with BSD Unix.

Basic lifetime of a shell

Let’s look at a shell from the top down. A shell does three main things in its lifetime.

•Initialize: In this step, a typical shell would read and execute its configuration files. These change aspects of the shell’s behavior.

•Interpret: Next, the shell reads commands from stdin (which could be interactive, or a file) and executes them.

•Terminate: After its commands are executed, the shell executes any shutdown commands, frees up any memory,

Basic loop of a shell

So, we’ve taken care of how the program should start up. Now, for the basic pro gram logic: what does the shell do during its loop? Well, a simple way to handl

commands is with three steps:

•Read: Read the command from standard input.

•Parse: Separate the command string into a program and arguments.

•Execute: Run the parsed command.

Putting it all together

That’s all the code that goes into the shell. If you’ve read along, you should understand completely how the shell works. To try it out (on a Linux machine), you would need to copy these code segments into a file (main.c), and compile it

. Make sure to only include one implementation of lsh_read_line(). You’ll need to include the following headers at the top. I’ve added notes so that you know where each function comes from.

• #include <sys/wait.h>

o waitpid() and associated macros

• #include <unistd.h>

o chdir()

o fork()

o exec()

o pid_t

• #include <stdlib.h>

o malloc()

o realloc()

o free()

o exit()

o execvp()

o EXIT_SUCCESS, EXIT_FAILURE

• #include <stdio.h>

o fprintf()

o printf()

o stderr

o getchar()

o perror()

• #include <string.h>

o strcmp()

o strtok()

Other comparison operators you can use include:

-eq – Equal to

-ne – Not equal to

-lt – Less than

-le – Less than or equal to

-lt – Less than

-ge – Greater than or equal to

Authors

Eleni Aklilu  Github

Kelbi Zerihun Github kelbizerihun3080@gmail.com

simple_shell