## Type Assignment

### Signature

```ebnf
<type_signature> ::=
    | <struct_signature>
    | <tuple_signature>
    | <union_signature>
    | <function_signature>
    | (<ident> [<type_parameters>]) ;
```

Dependencies:

- [`<struct_signature>`](product-types.md#signature)
- [`<tuple_signature>`](product-types.md#signature)
- [`<union_signature>`](sum-types.md#signature)
- [`<function_signature>`](function-types.md#signature)
- [`<ident>`](../identifiers.md)
- [`<type_parameters>`](generics.md#type-parameters)

Type assignments assign identifiers to type signatures. It may have a struct, tuple, union, or
function signature as well as an identifier followed by optional type parameters.

### Declaration

```ebnf
<type_declaration> ::= "type" <ident> [<type_parameters>] 
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<type_parameters>`](generics.md#type-parameters)

The `<type_declaration>` is prefixed with "type" and contains an identifier with optional type
parameters.

### Assignment

```ebnf
<type_assignment> ::= <type_declaration> "=" <type_signature> ;
```

The `<type_assignment>` is a type declaration followed by a type signature separated by an
assignment operator.
