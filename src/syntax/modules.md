## Modules

### Declaration

```ebnf
<module_declaration> ::=
    ["pub"] "mod" <ident> "{"
        [<module_devdoc>]
        (
            | <module_declaration>
            | <type_assignment>
            | <constant_assignment>
            | <item_devdoc>
            | <trait_declaration>
            | <impl_block>
        )*
    "}" ;
```

Dependencies:

- [`<ident>`](identifiers.md)
- [`<module_devdoc>`](comments.md)
- [`<type_assignment>`](type-system/assignment.md#assignment)
- [`<constant_assignment>`](comptime/constants.md#assignment)
- [`<item_devdoc>`](comments.md)
- [`<trait_declaration>`](type-system/traits.md#declaration)
- [`<impl_block>`](type-system/implementation.md#implementation-block)

The `<module_declaration>` is composed of an optional "pub" prefix, the "mod" keyword followed by an
identifier then the body of the module containing an optional devdoc, followed by a list of
declarations and module items, delimited by curly braces.

### Import

```ebnf
<module_import_item> ::=
    <ident> (
        "::" (
          | ("{" <module_import_item> ("," <module_import_item>)* [","] "}")
          | <module_import_item>
        )
    )* ;

<module_import> ::= ["pub"] "use" <ident> ["::" module_import_item] ;
```

The `<module_import_item>` is a recursive token, containing either another module import item or
a comma separated list of module import items delimited by curly braces.

The `<module_import>` is an optional "pub" annotation followed by "use", the module name, then
module import items.

### Semantics

> todo
