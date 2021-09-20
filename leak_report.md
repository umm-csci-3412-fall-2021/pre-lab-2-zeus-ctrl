# Leak report

_`clean_whitespace.c` has one memory leak, specifcally
at line 41 in `strip()`. This then is never freed,
creating a memory leak. This is fixed simply by calling
`free()` on line 49. This call to `free()` frees the
memory allocated by the `strip()` function._
