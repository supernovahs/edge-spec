## Traits

> TODO: rewrite this after constants

Traits are interface-like declarations that constrain [generic types](./generics.md) to implement
specific methods or contain specific properties.

### Declaration

```ebnf
<trait_declaration> ::=
    ["pub"] "trait" <ident> [<type_parameters>] [<trait_constraints>] "{"
    (
        | <type_alias_declaration>
        | <type_alias_definition>
        | <constant_declaration>
        | <constant_definition>
        | <fn_declaration>
        | <fn_definition>
    )*
    "}" ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<type_parameters>`](./generics.md)
- [`<trait_constraints>`](#constraints)
- [`<type_alias_declaration`](./type-alias.md)
- [`<type_alias_definition`](./type-alias.md)
- [`<constant_declaration>`](../comptime/constants.md)
- [`<constant_definition>`](../comptime/constants.md)
- [`<fn_declaration>`](../functions.md)
- [`<fn_definition>`](../functions.md)

The `<trait_declaration>` is a declaration of a set of associated types, constants, and functions
that may itself take type parameters and may be constrained to a super type. Semantics of the
declaration are listed under [trait solving rules](../../semantics/trait-solving.md).

### Implementation

```ebnf
<trait_implementation> ::=
    "impl" <ident> "for" <ident> [<type_parameters>] "{"
    (
        | <type_alias_definition>
        | <constant_definition>
        | <fn_definition>
    )*
    "}" ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<type_parameters>`](./generics.md)
- [`<type_alias_definition`](./type-alias.md)
- [`<constant_definition>`](../comptime/constants.md)
- [`<fn_definition>`](../functions.md)

The `<trait_implementation>` is an implementation of a trait for a given type. The only valid tokens
within the trait implementation's curly braces are the definition of associated type aliases,
constants, and functions. Semantics of the implementation are listed under
[trait solving rules](../../semantics/trait-solving.md).

### Constraints

```ebnf
<trait_constraints> ::= ":" <ident> ("&" <ident>)* ;
```

Dependencies:

- [`<ident>`](../identifiers.md)

The `<trait_constraints>` contains a colon followed by an ampersand separated list of identifiers of
implemented traits. The ampersand is meant to indicate that all of the trait identifiers are
implemented for the type.

Semantics of trait constraints are listed under
[trait solving rules](../../semantics/trait-solving.md).
