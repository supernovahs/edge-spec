## Traits

Traits are interface-like declarations that constrain [generic types](generics.md) to implement
specific methods or contain specific properties.

### Declaration

```ebnf
<trait_declaration> ::=
    ["pub"] "trait" <ident> [<type_parameters>] [<trait_constraints>] "{"
    (
        | <type_declaration>
        | <type_assignment>
        | <constant_declaration>
        | <constant_assignment>
        | <function_declaration>
        | <function_assignment>
    )*
    "}" ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<type_parameters>`](generics.md#type-parameters)
- [`<trait_constraints>`](#constraints)
- [`<type_declaration`](assignment.md#declaration)
- [`<type_assignment>`](assignment.md#assignment)
- [`<constant_declaration>`](../comptime/constants.md#declaration)
- [`<constant_assignment>`](../comptime/constants.md#assignment)
- [`<function_declaration>`](function-types.md#declaration)
- [`<function_assignment>`](function-types.md#assignment)

The `<trait_declaration>` is a declaration of a set of associated types, constants, and functions
that may itself take type parameters and may be constrained to a super type. Semantics of the
declaration are listed under [trait solving rules](../../semantics/trait-solving.md).

### Constraints

```ebnf
<trait_constraints> ::= ":" <ident> ("&" <ident>)* ;
```

Dependencies:

- [`<ident>`](../identifiers.md)

The `<trait_constraints>` contains a colon followed by an ampersand separated list of identifiers of
implemented traits. The ampersand is meant to indicate that all of the trait identifiers are
implemented for the type.

### Semantics

Traits can be defined with associated types, constants, and functions. The trait declaration itself
allows for optional assignment for each item as a default. Any declarations in the trait that are
not assigned in the trait declaration must be assigned in the [implementation](implementation.md) of
the trait for the data type. Additionally, any assignments in the trait declaration can be
overridden in the trait implementation.

While types can depend on trait constraints, traits can also depend on other trait constraints.
These assert that types that implement a given trait also implement its "super traits".

#### Solving

Trait solving involves asserting that required trait constraints are satisfied for types in
polymorphic types and functions that require it. It must also assert that there are no cycles in
trait constraints. Once cycle detection resolves to false, trait bounds may be represented as a
directed acyclic graph (DAG). Recursive, depth-first traversal of the DAG traces sub traits to their
super traits until terminal super traits (traits with no super traits) are found. If no instance of
the super trait is found, the trait constraint is not satisfied and a compiler error is thrown.

```
Certainty ->
    | Proven
    | Ambiguous
    | Disproven
```

```rs
// D impl A? yes ; proof D -> (B | C) -> A
// D impl B? yes ; proof D -> B
// D impl C? yes ; proof D -> C
// D impl D? yes ; proof D -> D
trait A {}
trait B: A {}
trait C: A {}
trait D: B + C {}

// a<A>() ? yes ; proof A --> A
// a<B>() ? yes ; proof B --> A
// a<C>() ? yes ; proof C --> A
// a<D>() ? yes ; proof D --> (B | C) --> A
fn a<T: A>(arg: T) {}

// b<A>() ? yes ; proof A --> A
// b<B>() ? yes ; proof B --> A
// b<C>() ? yes ; proof C --> A
// b<D>() ? yes ; proof D --> (B | C) --> A
fn b<T: A>(arg: u8) -> T {}

// c<A>() ? no  ; proof A ->! B
// c<B>() ? yes ; proof B --> B
// c<C>() ? no  ; proof C ->! B
// c<D>() ? yes ; proof D --> B
fn c<T: B>(arg: T) {}

// A ; yes ; proof
fn do() -> B {
    return A(0);
}

// d<A>() ? 
fn d<T: B>(arg) -> T {}
```
