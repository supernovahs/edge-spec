## Constants

### Declaration

```ebnf
<constant_declaration> ::= "const" <ident> [<type_signature>] ;
```

The `<constant_declaration>` is a "const" followed by an identifier and optional type signature.

### Assignment

```ebnf
<constant_assignment> ::=
    <constant_declaration> "="
    (
        | <expr>
        | ("(" <ident> ("," <ident>)* [","] ")" "{" <code_block> "}")
    ) ;
```

The `<constant_assignment>` is a constant declaration followed by an assignment operator and either
an expression or a comma separated list of identifiers delimited by parentheses followed by a code
block.

> Note: The expression must be a comptime expression, but the grammar should not constrain this.
