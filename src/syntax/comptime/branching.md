## Branching

```ebnf
<comptime_branch> ::=
    "comptime" (
        | <if_else_if_branch>
        | <if_match>
        | <match>
        | <ternary>
    ) ;
```

Dependencies:

- [`<if_else_if_branch>`](../control-flow/branching.md#if-else-if)
- [`<if_match>`](../control-flow/branching.md#if-match)
- [`<match>`](../control-flow/branching.md#match)
- [`<ternary>`](../control-flow/branching.md#ternary)

The `<comptime_branch>` is a branch that is evaluated at compile time where only the truthy branch
is compiled. It is defined as the "comptime" keyword followed by any of the branches.

### Semantics

> todo
