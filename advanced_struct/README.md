# Advanced structure

In this program we first define a static unsigned long integer called `last_id` as an ID counter for people, and then
declare the type `person_t` with fields:
- `final ulong id = last_id++`: it has type `ulong`, evaluates **once** at object creation, **can't change** (per-object) and has default
value `last_id++` (increments `last_id` by 1).
- `internal uchar[] name_separator = " "`: it has type `uchar[]` (string), can only be used **inside the declaration**, 
has default value `" "` and **can be changed** by using an expression similar to namespace access (`person_t::name_separator = ...`).
- `int age`, `uchar[] name`, `uchar[] surname`: these don't have a default value and **can change** while the object isn't `null`.
- `final lazy uchar[] fullname = ...`: it has type `uchar[]` (string), is *lazy* meaning the expression (`name .. name_separator .. surname`)
will only evaluate when the value is first used and **can't change** once the expression is evaluated.

Then namespace `person` is declared, with three functions:
- `create`: for creating a new `person_t` object.
- `minor`: for checking if a `person_t` object has an age under `18`.
- `adult`: for checking if a `person_t` object has an age over/equal to `18`.

Finally, in main, a new `person_t` object is created (and it's freeing is delayed).

The ID of `p` is printed, then the `name_separator` of `person_t` is changed, meaning that when `fullname` is printed at the end
of main, the output will be `John@Doe` and `fullname` will be set to `John@Doe` (not for too long, as the object is deleted right
after).

