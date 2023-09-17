## Type Alias

The type alias is a named alias for another type. Behavior is identical to the underlying type.

### Declaration

```ebnf
<type_alias_declaration> ::= "type" <ident> "is" <ident> ;
```

Dependencies:

- [`<ident>`](../identifiers.md)

The `<type_alias_declaration>` declares a new type alias. The first identifier is the name of the
type alias while the second identifier is the underlying type.
