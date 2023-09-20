## Signature

```ebnf
<type_signature> ::=
    | <primitive_data_type>
    | <struct_signature>
    | <tuple_signature>
    | (<ident> [<type_parameters>])
```

Dependencies:

- [`<primitive_data_type>`](./primitive-types.md)
- [`<struct_signature>`](./product-types.md)
- [`<tuple_signature>`](./sum-types.md)
- [`<ident>`](../identifiers.md)
- [`<type_parameters>`](./generics.md)

The `<type_signature>` is a collection of data type signatures. Primitive and product type
signatures require unique syntax, however, everything else is an identifier flowed by an optional
type parameter list.
