## Traits

Traits are interface-like declarations that constrain [generic types](./generics.md) to implement
specific methods or contain specific properties.

### Declaration

```ebnf
<trait_declaration> ::=
    ["pub"] "trait" <ident> [<type_parameters>] [<trait_constraints>] "=" "{"
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
- [`<type_parameters>`](./generics.md#type-parameters)
- [`<trait_constraints>`](#constraints)
- [`<type_declaration`](./assignment.md#declaration)
- [`<type_assignment>`](./assignment.md#assignment)
- [`<constant_declaration>`](../comptime/constants.md#declaration)
- [`<constant_assignment>`](../comptime/constants.md#assignment)
- [`<function_declaration>`](./function-types.md#declaration)
- [`<function_assignment>`](./function-types.md#assignment)

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

Semantics of trait constraints are listed under
[trait solving rules](../../semantics/trait-solving.md).
