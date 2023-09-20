
## Product Type

The product type is a compound type composed of none or more internal types.

### Signature

```ebnf
<struct_signature> ::= <ident> [<type_parameters>] ;
<tuple_signature> ::= "(" <type_signature> ("," <type_signature>)* [","] ")" ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<type_parameters>`](./generics.md)
- [`<type_signature>`](../signature.md)

The `<struct_signature>` is a struct identifier followed by optional type parameters.

The `<tuple_signature>` is a comma separated list of type signatures delimited by parenthesis.

### Declaration

```ebnf
<struct_field_declaration> ::= ["pub"] <ident> ":" <type_signature> ;
<struct_declaration> ::=
    ["pub"] ["packed"] "struct" <struct_signature> "{"
    [<struct_field_declaration> ("," <struct_field_declaration>)* [","]]
    "}" ;

<tuple_declaration> ::= ["pub"] ["packed"] <tuple_signature> ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<type_parameters>`](./generics.md)
- [`<type_signature>`](../signature.md)

The `<struct_declaration>` is a declaration of a product type, or a data structure that contains all
of its internally declared types. Each struct field is named with an assigned type.

The `<tuple_declaration>` is a declaration of an anonymous product type, or a tuple that contains
all of its internally declared types. Each tuple field is unnamed and contains only a 

The optional "pub" keyword in the struct, tuple, and field declarations indicate visibility, more on
visibility in the [visibility semantics documentation](../../semantics/visibility.md).

### Instantiation

```ebnf
<struct_field_instantiation> ::= <ident> ":" <expression> ;

<struct_instantiation> ::=
    [<data_location>] <struct_signature> "{"
        [<struct_field_instantiation> ("," <struct_field_instantiation>)* [","]]
    "}" ;

<tuple_instantiation> ::= [<data_location>] <ident> "(" [<expr> ("," <expr>)* [","]] ")" ;
```

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
