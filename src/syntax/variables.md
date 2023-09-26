## Variables

### Declaration

```ebnf
<variable_declaration> ::= "let" ((<ident> ";") | <variable_assignment>) ;
```

Dependencies:

- [`<ident>`](./identifiers.md)

The `<variable_declaration>` marks the declaration of a variable, it may optionally be assigned at
the time of declaration.

### Assignment

```ebnf
<variable_assignment> ::= <ident> "=" <expression> ;
```

Dependencies:

- [`<ident>`](./identifiers.md)
- [`<expression>`](./expressions.md)

The `<variable_assignment>` is the assignment of a variable. Its identifier is assigned the returned
value of an expression using the assignment operator.
