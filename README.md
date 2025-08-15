T4A - A Theory- and Action-Oriented Course on Operating Systems and Programming
Languages
======

Right now, this is just an idea for attracting new contributors to Oils.

## Prequisites

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

### Two Quick Questions

These two questions might help you figure out if you want to spend time on
this.

(1) Write a Python function to normalize a Unix path (without using the
standard library).

Example:

    /usr/local/bin/../../sbin/chroot -> /usr/sbin/chroot

    def norm(path_str):
      # fill this in
      return ''


Hint: split the string by `/`, and use a list as a stack.

Write short unit tests that ensure the function is defined for ALL kinds of
inputs.  You can also restrict inputs with assertions.

(2)


(Note: these two questions test *interior* and *exterior* reasoning)

## Topics

See [outline.md][].

