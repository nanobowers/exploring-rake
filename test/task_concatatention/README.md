# Task Concatenation

Those new to Rake may not quite grok the difference between adding additional command-blocks to tasks and defining newly named tasks.

If adding command-blocks to an existing task, if all is defined in the appropriate sequence and run serially, the Rakefile may appear to do the right thing.  When run in parallel, it will still run in a series.

## task-concat example:

```sh
  rake -m -f Rakefile.parallel_bad
  ## operates serially
```

## separate task example:

```sh
  rake -m -f Rakefile.parallel_ok
  ## parallel operation is correct
```
