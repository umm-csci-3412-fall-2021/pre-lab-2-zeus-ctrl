# Leak report

_`clean_whitespace.c` has one memory leak, specifcally
in the `is_clean()` function where the result of `strip()`
is assigned to `cleaned`. This result has an allocated char
array and is never freed, creating the leak. To remedy this we
simply free the `cleaned` variable after using it, but because
the return of `strip()` is a bit wonky, we have to account for
being given an empty string, making our comparator very simple._
