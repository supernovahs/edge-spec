## Statements

> TODO: rewrite

```ebnf
<stmt> ::=
    | <use_directive>
    | <variable_declaration>
    | <variable_assignment>
    | <constant_definition>
    | <branch>
    | <loop>
    | <match> ;
```

Dependencies:

- [`<use_directive>`](./modules.md)
- [`<variable_declaration>`](./variables.md#declaration)
- [`<variable_assignment>`](./variables.md#assignment)
- [`<constant_definition>`](./comptime/constants.md)
- [`<branch>`](./control-flow/branching.md)
- [`<loop>`](./control-flow/loops.md)
- [`<match>`](./control-flow/pattern-matching.md)

The `<stmt>` is similar to an expression, however the item does not return[^ret] a value.

[^ret]: See [Disambiguation: Return vs Return™️](../introduction.md#return-vs-return™️)
