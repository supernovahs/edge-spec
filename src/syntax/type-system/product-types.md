
## Product Type

The product type is a compound type composed of none or more internal types.

### Signature

```ebnf
<struct_field_signature> ::= <ident> ":" <type_signature> ;
<struct_signature> ::=
    ["packed"] "{"
        [<struct_field_signature> ("," <struct_field_signature>)* [","]]
    "}" ;
<tuple_signature> ::= ["packed"] "(" <type_signature> ("," <type_signature>)* [","] ")" ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<type_parameters>`](./generics.md#type-parameters)
- [`<type_signature>`](./assignment.md#signature)

### Instantiation

```ebnf
<struct_field_instantiation> ::= <ident> ":" <expr> ;

<struct_instantiation> ::=
    [<data_location>] <struct_signature> "{"
        [<struct_field_instantiation> ("," <struct_field_instantiation>)* [","]]
    "}" ;

<tuple_instantiation> ::= [<data_location>] <ident> "(" [<expr> ("," <expr>)* [","]] ")" ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<expr>`](../expressions.md)
- [`<data_location>`](../data-locations.md)

The `<struct_instantiation>` is an instantiation, or creation, of a struct. It may optionally
include a data location annotation, however the semantic rules for this are in the
[data location semantic rules](../../semantics/data-locations.md#product-types). It is instantiated
by the struct identifier followed by a comma separated list of field name and value pairs delimited
by curly braces.

The `<tuple_instantiation>` is an instantiation, or creation, of a tuple. It may optionally include
a data location annotation, however the semantic rules for this are in the
[data location semantic rules](../../semantics/data-locations.md#product-types). It is instantiated
by a comma separated list of expressions delimited by parenthesis.

### Field Access

```ebnf
<struct_field_access> ::= <ident> "." <ident> ;
<tuple_field_access> ::= <ident> "." <dec> ;
```

Dependencies:

- [`<ident>`](../identifiers.md)

The `<struct_field_access>` is written as the struct's identifier followed by the field's identifier
separated by a period.

The `<tuple_field_access>` is written as the tuple's identifier followed by the field's index
separated by a period.

Behavior of each is specified under
[data location semantic rules](../../semantics/data-locations.md#product-types).
