## Constants

### Declaration

```ebnf
<constant_declaration> ::= "const" <ident> [<type_signature>] ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<type_signature>`](../type-system/assignment.md#signature)

The `<constant_declaration>` is a "const" followed by an identifier and optional type signature.

### Assignment

```ebnf
<constant_assignment> ::=
    <constant_declaration> "=" <expr> ;
```

Dependencies:

- [`<expr>`](../expressions.md)

The `<constant_assignment>` is a constant declaration followed by an assignment operator and either
an expression or a comma separated list of identifiers delimited by parentheses followed by a code
block.

> Note: The expression must be a comptime expression, but the grammar should not constrain this.

### Semantics

Constants must be resolvable at compile time either by assigning it a literal, another constant, or
an expression that can be resolved at compile time.

The type of a constant will only be inferred if its assignment is a literal with a type annotation,
another constant with a resolved type, or an expression with a resolved type such as a function
call.

```rs
const A: u8 = 1;
const B = 1u8;
const C = B;
const D = a();
const E: u8 = b();

comptime fn a() -> u8 {
    1
}

fn b() -> T {
    2
}
```
