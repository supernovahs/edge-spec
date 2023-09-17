## Generics

Generics are polymorphic types enabling function and type reuse across different types.

### Type Parameters

```ebnf
<type_parameter_single> ::= <ident> <trait_constraint> ;

<type_parameters> ::= "<" <type_parameter_single> ("," <type_parameter_single>)* [","] ">" ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<trait_constraint>`](./traits.md)

The `<type_parameter_single>` is an individual type parameter for parametric polymorphic types and
functions. We define this as a type name optionally followed by a trait constraint.

The `<type_parameters>` is a comma separated list of individual type parameters delimited by angle
brackets.

Semantics and behavior of generics is defined in the
[trait solving rules](../../semantics/trait-solving.md).
