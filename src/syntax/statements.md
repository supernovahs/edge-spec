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

- [`<variable_declaration>`](variables.md#declaration)
- [`<variable_assignment>`](variables.md#assignment)
- [`<type_declaration>`](type-system/assignment.md#declaration)
- [`<type_assignment>`](type-system/assignment.md#assignment)
- [`<trait_declaration>`](type-system/traits.md#declaration)
- [`<impl_block>`](type-system/implementation.md#implementation-block)
- [`<function_declaration>`](type-system/function-types.md#declaration)
- [`<function_assignment>`](type-system/function-types.md#assignment)
- [`<abi_declaration>`](type-system/abi.md#declaration)
- [`<contract_declaration>`](type-system/contract-objects.md#declaration)
- [`<contract_impl_block>`](type-system/contract-objects.md#implementation)
- [`<core_loop>`](control-flow/loops.md#core-loop)
- [`<for_loop>`](control-flow/loops.md#for-loop)
- [`<while_loop>`](control-flow/loops.md#while-loop)
- [`<do_while_loop>`](control-flow/loops.md#do-while-loop)
- [`<code_block>`](control-flow/code-block.md#declaration)
- [`<if_else_if_branch>`](control-flow/branching.md#if-else-if-branch)
- [`<if_match_branch>`](control-flow/branching.md#if-match)
- [`<match>`](control-flow/branching.md#match)
- [`<constant_assignment>`](comptime/constants.md#assignment)
- [`<comptime_branch>`](comptime/branching.md#branching)
- [`<comptime_function>`](comptime/functions.md#functions)
- [`<module_declaration>`](modules.md#declaration)
- [`<module_import>`](modules.md#import)

The `<stmt>` is similar to an expression, however the item does not return[^ret] a value.

[^ret]: See [Disambiguation: Return vs Return™️](../introduction.md#return-vs-return™️)
