# Exploring Rake

Rake is a build system for Ruby, created by Jim Weirich.

These are some test cases and extension ideas for Rake.

None of these tests are automated, this is mainly for documentation purposes.

## test/env_parallel
Demonstrate the perils of setting ENV vars in rake in conjunction with parallel execution

## test/error_recovery

An example of how to recover from fails to <tt>sh()</tt>

## test/faster_dump_tasks

If the Rakefile calls some code that takes a long time to run (every time you run it), it can take a while to run <tt>rake -T</tt>.  An example of how to shortcut that.

## test/make_vs_rake_inconsistent

Behavior not consistent with gnumake.  Needs a better explanation.

## test/multitask_threadpool

An attempt to build a new task-type that allocates a thread pool on a per task basis.  Indended for cases where certain tasks are license-limited

## test/recovery_from_badredirect

One common mistake is to call a shell script sends data to stdout, but then the script fails, leaving the redirected file empty.  Future builds see that zero-byte file as up-to-date.  This renders


## test/task_concatatention

Unexpected behavior, presumably related to task concatentation.

This is visible when running <tt>drake -j</tt> or <tt>rake -m</tt>.

## test/dbquery_timestamp
An unfinished attempt at trying to get appropriate timestamps from a hierarchical multi-file based database.  Not yet suitable for human or animal consumption.

