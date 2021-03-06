Optint - Abstract type on integer between x64 and x86 architecture
==================================================================

This library provide one module `Optint` which use internally an `int` if you
are in a x64 architecture or an `int32` (boxed value) if you are in a x86
architecture. This module is __really__ unsafe and does not care some details
(like the sign bit) for any cast.

## Goal

The main difference between an `int` and an `int32` is the second is boxed.
About performance this is not the best. However, you can not ensure to be in an
x64 architecture where you can use directly an `int` instead an `int32` (and
improve performance).

So, this library provide an abstraction about a real `int32`. In a x64
architecture, internally, we use a `int` and in a x86 architecture, we use a
`int32`. By this way, we ensure to have in any platform 32 free bits in
`Optint.t`.
