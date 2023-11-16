## Expressions

> TODO: rewrite

```ebnf
<binary_operation> ::= <expr> <binary_operator> <expr> ;
<unary_operation> ::= <unary_operator> <expr> ;

<expression> ::= ["("] (
        <fn_call>
        | <match>
        | <binary_operation>
        | <unary_operation>
        | <ternary>
        | <ident>
    ) [")"] ;
```

Dependencies:

- [`<binary_operator>`](operators.md#binary)
- [`<unary_operator>`](operators.md#unary)
- [`<ternary>`](control-flow/ternary.md)
- [`<fn_call>`](functions.md)
- [`<match>`](control-flow/pattern-matching.md)
- [`<ident>`](identifiers.md)

The `<expression>` is defined as an item that returns[^ret] a value.

The `<binary_operation>` is an expression composed of two sub-expressions with an infixed binary
operator. Semantics are beyond the scope of the syntax specification, see
[operator precedence semantics](../semantics/operator-precedence.md) for more.

The `<unary_operation>` is an expression composed of a prefixed unary operator and a sub-expression.

[^ret]: See [Disambiguation: Return vs Return™️](../introduction.md#return-vs-return™️)
