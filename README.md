Advanced Java, October 29-31 2012
=================================

Contracts and Inheritance
-------------------------

Liskov Substitutability Principle (LSP)

  - Given a Base and Derived class, a program that works with the Base class should also work with the Derived class.

Specification-based testing

  - establish invariants (contracts) and assert that those invariants hold for *all* possible arbitrary sample data

Value Classes vs. Service Classes
---------------------------------

  - Value classes have structural identity, final fields, getters. They shouldn't have anything else (no other methods), otherwise you end up with unnecessary coupling in your architecture.
  - Service classes usually only have reference identity, and mutable state.

Object Identity
---------------

  - Referential Identity: determined uniquely by address in memory, e.g. a == b
  - Structural Identity (or "Value" Identity): determined by an object's properties, e.g. a.equals(b)
  - Only use immutable fields to determine structural identity

Immutability
------------

Benefits

  - Fewer tests
  - Less code
  - Correct code
  - Safe inheritance (code reuse)
  - Stable object identity
  - Obviates need for synchronization, resulting in correct, high performance concurrent code

Design Patterns
---------------

  - Composite: multiple implementations of a common interface, some of which may recursively contain instances of the interface. Example: expressions with sub-expressions in a parse tree.

  - Visitor: avoid polluting a composite (above) data structure with orthogonal concerns. Define a "Visitor" interface with visit() methods for each composite implementation case, and define an accept() method in the composite interface which takes a visitor. Example: multiple serializers and evaluators for expressions.