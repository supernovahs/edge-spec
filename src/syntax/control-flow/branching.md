## Branching

> TODO: rewrite

Branching refers to blocks of code that may be executed based on a defined condition.

### If Else If Branch

```ebnf
<if_else_if_branch> ::= "if" "(" <expr> ")" <code_block>
    ("else" "if" "(" <expr> ")" <code_block>)*
    ["else" <code_block>] ;
```

Dependencies:

- [`<expr>`](../expressions.md)
- [`<code_block>`](./code-block.md)

The `<branch>` contains an "if" keyword followed by a parenthesis delimited expression and a code
block. It may be followed by zero or more conditions under "else" "if" keywords followed by a
parenthesis delimited expression and a code block, and finally it may optionally be suffixed with an
"else" keyword followed by a code block.

Semantics and behavior are listed under the
[control flow semantics](../../semantics/control-flow.md).

### If Match

```ebnf
<if_match_branch> ::= "if" <pattern_match> <lambda> ;
```

Dependencies:

- [`<pattern_match>`](../type-system/sum-types.md#pattern-match)\

The `<if_match_branch>` contains a pattern match expression followed by an optionally typed
identifier followed by a code block.

Semantics of the "if match" statement are listed under the
[control flow semantics](../../semantics/control-flow.md).

### Match

```ebnf
<match_arm> ::= [<union_pattern>] <lambda> ;

<match> ::=
    "match" <expr> "{"
    [<match_arm> ("," <match_arm>)* [","]]
    "}" ;
```

Dependencies:

- [`<expr>`](../expressions.md)
- [`<union_pattern>`](../type-system/sum-types.md#union-pattern)
- [`<lambda>`](../functions.md)

The `<match_arm>` is a single arm of a match statement. It may optionally be prefixed with a union
pattern and contains a lambda.

The `<match>` statement is a group of match arms that may pattern match against an expression.

Semantics of the match statement are defined in the
[control flow semantics](../../semantics/control-flow.md).

### Ternary

```ebnf
<ternary> ::= <expr> "?" <expr> ":" <expr> ;
```

Dependencies:

- [`<expr>`](../expressions.md)

The `<ternary>` is a branching statement that takes an expression, followed by a question mark, or
ternary operator, followed by two colon separated expressions.

Semantics of the ternary expression are defined in the
[control flow semantics](../../semantics/control-flow.md).
