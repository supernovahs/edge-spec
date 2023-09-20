## Type Alias

The type alias is a named alias for another type. Behavior is identical to the underlying type.

### Declaration

```ebnf
<type_alias_declaration> ::= "type" <ident> ;
```

Dependencies:

- [`<ident>`](../identifiers.md)

The `<type_alias_declaration>` declares a new type alias.

### Definition

```ebnf
<type_alias_definition> ::= <type_alias_declaration> "=" <type_signature> ;
```

Dependencies:

- [`<type_signature>`](./signature.md)

The `<type_alias_definition>` defines the new type alias to another type. The first identifier is
the name of the type alias while the second identifier is the underlying type.
