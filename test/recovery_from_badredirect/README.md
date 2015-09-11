# recovery_from_badredirect

Calling shell scripts that send data to stdout and then redirecting to an output file is a common gotcha when using Make systems.

If when run the first time, the shell script fails (possibly due to illegal command line setting, etc), the redirected output will be an empty file.

Then if make/rake is rerun, the file-task will be up to date even though the previous run failed and output was empty.

Example of what not to do:

  rake fail_to_redirect

  ## shell command failed, rake quits
  ## let's try to run again

  rake fail_to_redirect
  ## nothing to do here, no fails.

Example of what to do:

  rake fail_with_cleanup
  ##  shell command failed, cleanup bad redirect, rake quits
  ## let's try to run again

  rake fail_to_redirect
  ## reruns, still fails.


This case is more dangerous if this is part of a pipeline of file-tasks, though the example would be a bit longer.



