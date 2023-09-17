## Enumeration Type

The enumeration type is a named enumeration over an unsigned integer.

### Declaration

```ebnf
<enum_declaration> ::= "enum" <ident> "{" [<ident> ("," <ident>)* [","]] "}" ;
```

Dependencies:

- [`<ident>`](../identifiers.md)

Declaration of an enumeration is the enumeration's name followed by a comma separated list of
members delimited by curly braces. 

### Instantiation

```ebnf
<enum_instantiation> ::= <ident> "." <ident> ;
```

The instantiation of an enumeration is the enumeration's name followed by the identifier of a single
member. The behavior of the instantiation is defined in the
[data location rules](../../semantics/data-locations.md#enumeration-type).
