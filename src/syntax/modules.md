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

Namespace semantics in modules are defined in the [namespace document](../semantics/namespaces.md).

Visibility semantics in modules are defined in the
[visibility document](../semantics/visibility.md).

Modules can contain developer documentation, declarations, and assignments. If the module contains
developer documentation, it must be the first item in the module. This is for readability.

Files are implicitly modules with a name equivalent to the file name.

> todo: should this sanitize file names or require filenames to contain only valid ident chars?

Type, function, abi, and contract declarations must be assigned in the same module. However, trait
are declared without assignment and submodules may be declared without a block only if there is a
file with a matching name.

The `super` identifier represents the direct parent module of teh module in which it's invoked.
