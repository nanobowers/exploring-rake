Bash is a pretty common interactive shell.  It does things that the bourne-shell cannot, like process substitution, e.g: 
```sh
cat <(echo foo) <(echo bar) > baz
```
This rakefile shows a tweak that can be used to make *all* 'sh' commands run bash instead of sh.

The root of the sh function Kernel.system, but we can hide "bash -c #{command}" inside.

The idea to use the 'shellwords' module to escape special-chars came from this blog:

http://greyblake.com/blog/2013/09/21/how-to-call-bash-not-shell-from-ruby/

