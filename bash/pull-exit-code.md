# Pull exit code

To access the exit code of the last command, you can use `echo $?`. This is useful for when your program crashes with "Killed" or just silently and you aren't sure where to start debugging.

### Exit code catalog

- 0: Ran fine
- 137: Out of memory