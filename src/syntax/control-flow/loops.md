## Loops

Loops are blocks of code that may be executed repeatedly based on some conditions.

### Loop Control

```ebnf
<loop_break> ::= "break" ;
<loop_continue> ::= "continue" ;
```

The `<loop_break>` keyword "breaks" the loop's execution, jumping to the end of the loop
immediately.

The `<loop_continue>` keyword "continues" the loop's execution from the start, short circuiting the
remainder of the loop.

### Loop Block

```ebnf
<loop_block> ::= "{" ((<expr> | <stmt> | <loop_break> | <loop_continue>) ";")* "}" ;
```

Dependencies:

- [`<expr>`](../expressions.md)
- [`<stmt>`](../statements.md)

The `<loop_block>` is a block of code to be executed repeatedly. All other loops are derived from
this single loop block.

### Core Loop

```ebnf
<core_loop> ::= "loop" <loop_block> ;
```

The core loop block is the simplest of blocks, it contains no code to be injected anywhere else. All
other loops are syntactic sugar over the core loop. The "desugaring" step for each loop is in the
[control flow semantic rules](../../semantics/control-flow.md).

### For Loop

```ebnf
<for_loop> ::= "for" "(" [(<stmt> | <expr>)]";" [<expr>] ";" [(<stmt> | <expr>)] ")" <loop_block> ;
```

Dependencies:

- [`<expr>`](../expressions.md)
- [`<stmt>`](../statements.md)

The `<for_loop>` is a loop block prefixed with three individually optional items. The first may be a
statement or expression, the second may only be an expression, and the third may be an expression or
statement.

### While Loop

```ebnf
<while_loop> ::= "while" "(" <expr> ")" <loop_block> ;
```

Dependencies:

- [`<expr>`](../expressions.md)

The `<while_loop>` is a loop block prefixed with one required expression.

### Do While Loop

```ebnf
<do_while_loop> ::= "do" "while" <loop_block> "(" <expr> ")" ;
```

Dependencies:

- [`<expr>`](../expressions.md)

The `<do_while_loop>` is a loop block suffixed with one required expression.

### Semantics

> todo
