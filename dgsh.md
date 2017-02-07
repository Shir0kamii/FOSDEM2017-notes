DgSh
====

Problematic
-----------

You're forced to use dirty methods to make pipelines as DAG.

Solution
--------

DgSh allow a new construct.

A channel is a text stream.
A shell command can take input from or output to multiples channels.

With this, you can implement any DAG as a shell pipeline

It can allow for very powerful constructions, as a map reduce or a listing of
duplicate files.

Conclusion
----------

DgSh is a very powerful tool but it's only useful to people using their shell
to a big extent.
