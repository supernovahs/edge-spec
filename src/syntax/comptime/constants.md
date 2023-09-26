## Constants

### Declaration

```ebnf
<constant_declaration> ::= "const" <ident> [<type_signature>] ;
```

The `<constant_declaration>` is a "const" followed by an identifier and optional type signature.

### Assignment

```ebnf
<constant_assignment> ::= <constant_declaration> "=" <expr> ";" ;
```

The `<constant_assignment>` is a constant declaration followed by an assignment operator and an
expression.

> Note: The expression must be a comptime expression, but the grammar should not constrain this.
