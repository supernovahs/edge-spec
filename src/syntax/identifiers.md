## Identifiers

```ebnf
<ident> ::= (<alpha_char> | "_") (<alpha_char> | <dec_digit> | "_")* ;
```

Dependencies:

- [`<alpha_char>`](comptime/literals.md)
- [`<dec_char>`](comptime/literals.md)

The `<ident>` is a C-style identifier, beginning with an alphabetic character or underscore,
followed by zero or more alphanumeric or underscore characters.
