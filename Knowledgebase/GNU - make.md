---
summary: a utility used to build executables from source code by following rules in a Makefile.
href:
  - https://www.gnu.org/software/make/manual/make.html
aliases:
  - Makefile
  - make
---
# Overview

From the official documentation:

> The make utility automatically determines which pieces of a large program need to be recompiled, and issues commands to recompile them.

So `make` is a simple way to manage build complexities where some files depend on others and need to be built or processed in a specific way can be conditioned to meet certain prerequisites before running to reduce the amount of time building or rebuilding a project.

## History

Make was invented by Stuart Feldman in 1976 at Bell Labs, initially, as a build automation tool for executable programs. Even today, it is built into Unix, Linux and MacOS.

## Benefits and Drawbacks 

### I. Pros
- Is is a proven solution that is available everywhere.
- It is consistent across local and CI builds.
- It is relatively easy to learn.
- Never out of sync with documentation since it can act as one (if it is well-written).

### II. Cons
- It can be hard to master.
- Its syntax is dependent on tabs and spaces.
- Bugs can be tricky to figure out.

# Beyond C/C++ projects

While `make` and `Makefile` have roots in C and C++ development, their utility as general-purpose build tools and task runners makes them relevant and helpful in various development ecosystems.

- **Generic Task Runner**: `Makefile` can serve as a simple task runner. Targets can represent tasks, and this makes it easy to define and run common development tasks (like `clean`, `test`, `build`, `deploy`, etc.).

- **Ubiquity**: `make` is ==available on almost every Unix-like system by default==, which makes it a handy tool regardless of the project type.

- **Efficiency**: `make` checks the timestamp of files to ensure only the necessary parts of a project are rebuilt. This concept is beneficial in many domains, not just C/C++ compilation.

- **Extensibility**: While it has a simple core, `make` is extensible and can be used in conjunction with other tools and scripts to perform a wide variety of tasks.

# Makefile: `make`'s Blueprint

Although, the make command has a lot of built-in knowledge, it can’t know how to build your application all by itself. You must provide a file that tells `make` how your application is constructed.This file is called the `Makefile`.

Just as a blueprint gives instructions about how to construct a building, a `Makefile` ==provides instructions== (in the form of rules) to `make` on how to build or process certain files or tasks.

## Syntax

- A Makefile consists of a set of dependencies and rules.
- A dependency has a **target** (a file to be created) and a set of source files upon which it is dependent.
- The **rules** describe how to create the target from the dependent files. Typically, the target is a single executable file.
- Makefiles allow you to use macros (`MACRONAME=value`) so that you can write rules in a more generalised form to reduce duplication. 
- A comment in a `Makefile` starts with `#` and continues to the end of the line.

> [!DANGER] Rules MUST start with a Tab!
> In Makefiles, every command that's part of a recipe (i.e., the action to be taken) must be preceded by a tab.
> 
> Because most editors do not distinguish the difference between spaces and a tab, most novice users encounter many problems when building a Makefile.

> [!BUG]
> A space at the end of a line in the `Makefile` may cause a make command to fail.

## Debugging

To enable debugging, run:
```sh
make -d <target>
```
To see the command before running, run 
```sh
make -n <target>
```
To do both, and output to a log file, run:
```sh
make -dn <target> > ./debug.log 2>&1
```

## Macros (i.e. "variables")

You define a macro in a `Makefile` by writing **`MACRONAME=value`** , then accessing the value of **`MACRONAME`** by writing either `$(MACRONAME)` or `${MACRONAME}`.

# EOF
___

%%
#note
related: [[Linux]], [[Build Tools|Build automation]]
created:: 2023-09-28
%%