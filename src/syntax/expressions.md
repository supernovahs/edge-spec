## Expressions

```ebnf
<binary_operation> ::= <expr> <binary_operator> <expr> ;
<unary_operation> ::= <unary_operator> <expr> ;

<expr> ::=
    | <array_instantiation>
    | <array_element_access>
    | <struct_instantiation>
    | <tuple_instantiation>
    | <struct_field_access>
    | <tuple_field_access>
    | <union_instantiation>
    | <pattern_match>
    | <arrow_function>
    | <function_call>
    | <binary_operation>
    | <unary_operation>
    | <ternary>
    | <literal>
    | <ident>
    | ("(" <expr> ")");
```

Dependencies:

- [`<binary_operator>`](operators.md#binary)
- [`<unary_operator>`](operators.md#unary)
- [`<array_instantiation>`](type-system/array-types.md#instantiation)
- [`<array_element_access>`](type-system/array-types.md#element-access)
- [`<struct_instantiation>`](type-system/product-types.md#instantiation)
- [`<tuple_instantiation>`](type-system/product-types.md#instantiation)
- [`<struct_field_access>`](type-system/product-types.md#field-access)
- [`<tuple_field_access>`](type-system/product-types.md#field-access)
- [`<union_instantiation>`](type-system/sum-types.md#instantiation)
- [`<pattern_match>`](type-system/sum-types.md#pattern-match)
- [`<arrow_function>`](type-system/function-types.md#arrow-functions)
- [`<function_call>`](type-system/function-types.md#call)
- [`<ternary>`](control-flow/branching.md#ternary)
- [`<literal>`](comptime/literals.md)
- [`<ident>`](identifiers.md)

The `<expr>` is defined as an item that returns[^ret] a value.

The `<binary_operation>` is an expression composed of two sub-expressions with an infixed binary
operator. Semantics are beyond the scope of the syntax specification, see
[operator precedence semantics](operators.md) for more.

The `<unary_operation>` is an expression composed of a prefixed unary operator and a sub-expression.

[^ret]: See [Disambiguation: Return vs Return™️](../introduction.md#return-vs-return™️)
