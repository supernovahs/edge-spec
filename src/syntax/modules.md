## Modules

### Declaration

```ebnf
<module_declaration> ::= ["pub"] "mod" <ident> "{" [<module_devdoc>] (<stmt>)* "}" ;
```

Dependencies:

- [`<ident>`](identifiers.md)
- [`<module_devdoc>`](comments.md)
- [`<stmt>`](statements.md)

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

Dependencies:

- [`<ident>`](identifiers.md)

The `<module_import_item>` is a recursive token, containing either another module import item or
a comma separated list of module import items delimited by curly braces.

The `<module_import>` is an optional "pub" annotation followed by "use", the module name, then
module import items.

### Semantics

> todo
