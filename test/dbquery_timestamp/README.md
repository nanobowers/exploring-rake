# Unfinished business.

What i'm trying to do here:

We often have hierarchical databases that break the traditional 'check a file timestamp' protocol of make-based flows.  checking the top-block timestamp is insufficient, as it has an include to another block which could've changed.

These databases are large and may contain lots and lots of top-level blocks and sub-level blocks, (and sub-sub-level, etc) such that we cannot afford to aggregate all cells.

I need a way to load the database as needed to look for timestamps of the hierarchy tree, then create a file-task like task to do some work.

This needs to integrate with Tasks and FileTasks fairly seamlessly as well.

note: This code is not fully functional.  the "database" in this case is very contrived and is built with json files.

