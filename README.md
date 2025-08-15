T4A: A Course on Operating Systems and Programming Languages
===

Right now, this is just an idea for attracting new contributors to Oils.

---

This course is:

- *Theory-oriented* - we introduce concepts with *words*, aiming to give
  **crisp definitions** that are *invariant* across technologies.
  - That is, this course will use shell, Python, and C, but the ideas are
    **not** specific to those technologies.
  - If you feel overwhelmed by the "tech treadmill", learning theory can be an
    antidote.
  - These words and concepts that can aid communication with other engineers
    (and with LLMs, in certain cases).
- *Action-oriented* - you can't learn just by reading!  Reading is too passive;
  knowledge must be tested.
  - We use **Unix shell** to express and test our actions.
  - Another way to test your understanding is to **write** for an audience.

T4A stands for "theory and four actions":

- We introduce the theory
- Then we use **two** different technologies, invoked from shell, to type the **wrong**
  thing first, and then we come up with the **right** thing.  So that's a total of 4 actions:
  - (A, wrong)
  - (A, right)
  - (B, wrong)
  - (B, right)

The goal is to learn the concept/theory, rather than the specific technology.

## Prerequisites

- This course isn't for new programmers.  A quick test: if you have *not*
  written production code in 2 different languages, this course won't be the
  best use of your time.
- This course is shell-oriented, so you'll spend most time either in a terminal
  or a plain text editor.  I think it can be a useful exercise for people who
  prefer to code with IDEs, but this isn't universally true.
  - [Where Contributors Have Problems](https://github.com/oils-for-unix/oils/wiki/Where-Contributors-Have-Problems)
    has similar caveats.
- A computer science education isn't a strict requirement, but the ideas are
  helpful.
  - We use basic logic and reasoning by sets.  We care about *exhaustive*
    reasoning, not just making things work for the happy path.
  - Some basic familiarity with operating systems and C.  

## Two Questions

These two questions might help you figure out if you want to spend time on
this.

### 1. Normalize a Unix Path

In this git repo, create a Python file `solutions/readme_path.py`.

Write a Python function to normalize a Unix path (without using the
standard library).

Example:

    /usr/local/bin/../../sbin/chroot -> /usr/sbin/chroot

    def norm(path_str):
      # fill this in
      return ''

Hint: split the string by `/`, and use a list as a stack.

Write short unit tests that ensure the function is defined for **all** kinds of
inputs.  You can also restrict inputs with assertions.

<!-- this tests data structures and coding skills -->

### Create Bugs in C

Start with this shell to create and run a C program:

    $ echo 'int main() { return 42; }' > foo.c

    $ gcc -o foo foo.c; ./foo; echo status=$?
    status=42

Now add this flag to enable [Address Sanitizer][asan]:

    $ gcc -fsanitize=address -o foo foo.c && ./foo; echo status=$?
    status=42

Create a new program with a **bug**:

    $ echo 'int main(int argc, char** argv) { if( *(argv[1]) ) return 1; return 42; }' > foo.c

Now create a shell script `solutions/readme_c.sh`, with  2 lines of shell:

1. One where the bug happens
1. One where the bug does NOT happen

<!-- this tests shell tool usage and reading C, but not writing C -->

### Publish Results

Create a branch `solutions-$YOURNAME`, and add `solutions/readme_*`, and `git
push`.

## Topics

See [outline.md]().
