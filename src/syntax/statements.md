## Statements

```ebnf
<stmt> ::=
    | <variable_declaration>
    | <variable_assignment>
    | <type_declaration>
    | <type_assignment>
    | <trait_declaration>
    | <impl_block>
    | <function_declaration>
    | <function_assignment>
    | <abi_declaration>
    | <contract_declaration>
    | <contract_impl_block>
    | <core_loop>
    | <for_loop>
    | <while_loop>
    | <do_while_loop>
    | <code_block>
    | <if_else_if_branch>
    | <if_match_branch>
    | <match>
    | <constant_assignment>
    | <comptime_branch> 
    | <comptime_function>
    | <module_declaration>
    | <module_import> ;
```

Dependencies:

- [`<use_directive>`](modules.md)
- [`<variable_declaration>`](variables.md#declaration)
- [`<variable_assignment>`](variables.md#assignment)
- [`<constant_definition>`](comptime/constants.md)
- [`<branch>`](control-flow/branching.md)
- [`<loop>`](control-flow/loops.md)
- [`<match>`](control-flow/pattern-matching.md)

The `<stmt>` is similar to an expression, however the item does not return[^ret] a value.

[^ret]: See [Disambiguation: Return vs Return™️](../introduction.md#return-vs-return™️)
