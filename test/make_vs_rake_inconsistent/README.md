# Inconsistent behavior w/ GNUmake and Rake:

```sh
## GNUmake example

make build      ## initial file build
make            ## nothing to do, files built
make rm_middle  ## removes file b,c
make            
## this reruns filetask b,c,d (even though they dont produce any output)
```

```sh
## Rake example

rake build      ## initial file build
rake            ## nothing to do, files built
rake rm_middle  ## removes file b,c
rake            
## difference: this reruns filetask b,c but not d.
```

(footnote: I believe this was documented in a change request to Jim Weirich, and a patch was offered but declined)