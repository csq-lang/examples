# Pointers

This program declares three functions:
- `increment` which increments an integer pointer (`iptr`) by 1.
- `decrement` which decrements an integer pointer (`iptr`) by 1.
- `set` which sets an integer pointer (`iptr`) to `val`.

As the address of the integer `v` is being passed to these functions, all changes made to the
dereference of `iptr` (`*iptr`) will be made to `v` too.

