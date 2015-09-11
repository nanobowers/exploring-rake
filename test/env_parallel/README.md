# env_parallel

This testcase shows the perils of setting ENV[] vars with a contrived example.
In many real-world cases, people use rake to call unix scripts and tools - utilities that sometimes use environment variables to control operation.

Parallelizing the task using <tt>drake</tt> or <tt>rake -m</tt> exposes this, as the use of the global ENV is not thread safe.

This should give correct output in <tt>x.tmp</tt>:
  rake clean
  rake

Parallel rake will produce incorrect output:
  rake clean
  rake -m

One workaround is to set the ENV variable in the sh() call itself.

Parallel rake will produce incorrect output:
  rake clean
  rake -m -f Rakefile.fix

Other workarounds might be to use command line arguments instead, or wrap the utility in a shell script that takes a command line argument and sets the env local to that script.

