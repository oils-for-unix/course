Outline
=======

Reverse order.  We don't start with lexing and parsing; we *end* with parsing and lexing.

- Points of reference
  - Learn Code the Hard Way - focuses on drills
  - Crafting Interpreters - the same language Lox is implemented in both Java
    and C
  - Recurse Center / John Holt - building mental structures
  - Task files / externalizing your thought process into shell / git

- End goal
  - Implement catbrain interpreter in an appropriate language?  Languages that
    expose Unix / libc calls: Python, C, C++, Rust, ... Ruby

## Exterior Topics

### Networking / SSH Keys

### Hardware: CPU, memory, disk

### Kernel Syscalls

Shell runtime:

- Simple Commands
  - builtin
  - external
  - YSH procs / shell functions
  - YSH funcs
- Pipelines 
- Command Sub
- Process Sub
- Subshell `fork` or `( )`

And:

- Redirects

### Process State

- What's inherited, what's not inherited?

### libc calls

### Data Languages / UTF-8

## Interior Topics

### Memory Safety / ASAN

### Garbage Collection

### Dictionary Data Structure

### Tree Representation

### Evaluation

### Parsing

### Lexing

## Human Topics

### UI

Completion and history?  This is exterior again

## Coding Tactics

### Task Files

- Externalizing your brain / thought processes
- Automate everything: "no script is too small"
  - semi-automation

### Dependency Inversion

(I make a distinction with "dependency injection", which implies a framework)

- This is how we create testable and modular code 
- No global variables, except in special cases, e.g.
  - signal handlers are inherently process-global
  - the GC heap is process global (although that could be changed)

## Shell Concepts

- Task Files
- Bernstein chaining 
- `$0` Dispatch pattern - sudo, xargs, find, etc.
- Pipelines
  - vectorized
  - point-free
  - imperative
