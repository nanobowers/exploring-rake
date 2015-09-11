# thread-pool per task

When using rake for jobflow control, parallel execution is a must.  Unfortunately, when using license-limited or memory/cpu intensive applications running rake -m for a heterogeneous task set may not be an option.  Often, license locked software will not exit gracefully or wait for available licenses if the license limit is exceeded.

One may think to just limit the max parallel execution to the license limit (e.g. <tt> drake -j 5 </tt> ).  If our rakeflow runs 100 widgets through three programs (A,B,C) in succession, and we have 3 licenses of A, 20 licenses of B and 10 licenses of C, it makes the most sense to set the limit on a per-task basis and not globally.

Here, I attempt to superclass MultiTask to allow for a per-task thread-pool.  Not sure if i did this the right way, but the example seems to work and limit itself.  This will require more testing.

It is worth noting that gnumake does not have the capability to enforce max parallelization on a per-task basis, AFAICT.

```sh
rake top_nolimit    ## regular multitask
rake top_limit      ## limit task internally
```
