# Vector2

This program declares the type `vec2_t` with two fields:
- `int x`: the X-coordinate as an integer.
- `int y`: the Y-coordinate as an integer.

Then, it declares *namespace* `vec2` for `vec2_t` operations.

One function is defined inside `vec2`, `new`, which creates a new
`vec2_t` pointer. The function has type `vec2_t*!`, which means it
propagates errors caused by `new`.

Then, in main, there are three main things that happen:
- A variable of type `vec2_t*`, called `v`, is declared and the value
is assigned to `vec2::create(5, 5)`.
- A delay is made (equivalent of `defer` in Zig), which delays the call
of `delete v` to the end of the block.
- The X and Y of `v` are printed, modified and then printed again.
