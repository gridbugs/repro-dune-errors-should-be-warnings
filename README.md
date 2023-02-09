# Repro for issue: Dune treats warnings as errors according to the workspace `lang dune` version when building vendored packages with a more permissive `lang dune` version

Install dependencies for the vendored package "resource-pooling", then run `make`. In dune 3.6, you'll get an error:
```
File "vendored/resource-pooling/resource_pool.ml", line 21, characters 2-27:
21 |   mutable node_prev : 'a t;
       ^^^^^^^^^^^^^^^^^^^^^^^^^
Error (warning 69 [unused-field]): mutable record field node_prev is never mutated.
File "vendored/resource-pooling/resource_pool.ml", line 22, characters 2-27:
22 |   mutable node_next : 'a t;
       ^^^^^^^^^^^^^^^^^^^^^^^^^
Error (warning 69 [unused-field]): mutable record field node_next is never mutated.
make: *** [Makefile:2: all] Error 1
```
