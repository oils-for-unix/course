T4A: A Course on Operating Systems and Programming Languages
===

Right now, this is just an **idea** for attracting new contributors to Oils.

(Should the course also be about writing?  Writing could help spread the
word.

And, not everyone may see this, but good writing is relatively **objective**.
There are different styles of writing, but some writing is good
and some is bad.

Typical problem: there could be too much material that takes too long.)

---

T4A stands for "theory and four actions".  That means that this course is:

- **Theory**-oriented
  - We introduce concepts with *words*, aiming to give **crisp definitions**
    that are *invariant* across technologies.
- Then we aim to express **four actions** using Unix **shell**
  - We may use **two** different technologies, like Python and C.  First we
    type the **wrong** thing, and then we come up with the **right** thing.  So
    that's a total of 4 actions:
  - (A, wrong)
  - (A, right)
  - (B, wrong)
  - (B, right)
- Another way to test your understanding is to **write** for an audience.

This course will use shell, Python, and C, but the goal is to learn the
concept/theory, rather than the specifics of these technologies.

Notes:

- On theory:
  - If you feel overwhelmed by the "tech treadmill", learning theory can be an
    antidote.
  - These words and concepts that can aid communication with other engineers
    (and with LLMs, in certain cases).
- On action:
  - You can't learn just by reading!  Reading is too passive; knowledge must be
    tested.

## Prerequisites

- This course isn't for new programmers.  A quick test: if you haven't written
  production code in 2 different languages, then this course won't be the best
  use of your time.
- This course is shell-oriented, so you'll spend most time either in a terminal
  or a plain text editor.
  - It can be a useful exercise for people who prefer to code with IDEs, but
    it's up to you to decide that.
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

### 1. Tickle a Bug in C Code

Start with this shell to create and run a C program:

    $ echo 'int main() { return 42; }' > foo.c

    $ gcc -o foo foo.c; ./foo; echo status=$?
    status=42

Now add this flag to enable [Address Sanitizer][asan], a tool that instruments
C code at runtime:

[asan]: https://github.com/google/sanitizers/wiki/AddressSanitizer

    $ gcc -fsanitize=address -o foo foo.c && ./foo; echo status=$?
    status=42

Create a new program with a **bug**:

    $ echo 'int main(int argc, char** argv) { if( *(argv[1]) ) return 1; return 42; }' > foo.c

Now, in this git repo, create a shell script `$YOUR_NAME/readme_c.sh`, with at
least 3 lines of shell:

1. Tickle the bug with ASAN on.
1. Tickle the bug without ASAN.
1. Run the program in a way that avoids the bug.

Conceptual questions / writing:

1. What's the symptom of the bug called, from the perspective of the OS / ASAN?
1. What's is the bug itself called, from the perspective of the C language?
1. What is data structure `argv` called?  Why does the bug happen?

(Note: beging precise about terminology may seem pedantic now.  But using
precise words is helpful when say writing about a bug.)

<!--
This tests shell tool usage and reading C, but not writing C.

It's a null pointer dereference, which causes a seg fault.

This is not really about memory safety.  If a null pointer dereference causes.
-->

T4A TODO: construct a Rust program that triggers an ASAN error at runtime.  You
may use `unsafe`, though you don't have to.  (Note: using LLM could be aa valid
time-saver here?  You can probably query the LLM.)

### 2. Normalize a Unix Path

In this git repo, create a Python file `solutions/readme_path.py`.

Write a Python function to normalize a Unix path (without using the
standard library).

Example:

    /usr/local/bin/../../sbin/chroot -> /usr/sbin/chroot

Template:

    def norm(path_str):
      # fill this in
      return ''

Hint: split the string by `/`, and use a list as a **stack**.

Write concise unit tests that ensure the function is defined for **all** kinds
of inputs.  You can also restrict inputs with assertions.

<!-- 
this tests data structures, coding skills, and reasoning with test cases
-->

### Publish Results

1. Create a branch `solutions-$YOURNAME`
1. `git add $YOUR_NAME/readme_*`
1. `git push`.

## Topics

See [outline.md](outline.md).
