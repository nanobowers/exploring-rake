# rake clean

## When to not use the builtin clean function

It's pretty common to use the clean function in rake:

```ruby
  require 'rake/clean'
  CLEAN.add("my.file")
```

What new users may not realize is that this builtin clean task has default behavior that may not be desired:
* Clean auto-removes temp-files (emacs style, files ending in "~")
* Clean works hierarchically.

The hierarchical behavior can be bad news if the rakefile is low enough in the directory tree.  I once setup a rakefile in a directory that had a subdirectory tree that recursively contained tens of thousands of files.  

It took several minutes to do a <tt>rake clean</tt>, even though all of the CLEAN.add's were at the root level where the rakefile lived.
