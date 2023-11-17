## Variables

### Declaration

```ebnf
<variable_declaration> ::= "let" <ident> [":" <type_signature>] ;
```

Dependencies:

- [`<ident>`](identifiers.md)
- [`<type_signature>`](type-system/assignment.md#signature)

The `<variable_declaration>` marks the declaration of a variable, it may optionally be assigned at
the time of declaration.

### Assignment

```ebnf
<variable_assignment> ::= <ident> "=" <expr> ;
```

Dependencies:

- [`<ident>`](identifiers.md)
- [`<expr>`](expressions.md)

The `<variable_assignment>` is the assignment of a variable. Its identifier is assigned the returned
value of an expression using the assignment operator.
