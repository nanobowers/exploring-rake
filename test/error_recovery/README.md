# Error Recovery

Some examples of error recovery

```sh
## default error handling, if sh() return-code != 0, then quit.
rake pass
rake fail

## custom error handling
rake pass_gracefully
rake fail_gracefully
```
