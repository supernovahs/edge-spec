## Sum Types

The sum type is a union of multiple types where the data type represents one of the inner types.

### Declaration

```ebnf
<union_member> ::= <ident> ["(" [<ident> ("," <ident>)* [","]] ")"] ;

<union_declaration> ::= "union" <ident> "{" <union_member> ["," <union_member>] [","] "}" ;
```

Dependencies:

- [`<ident>`](../identifiers.md)

The `<union_declaration>` is a declaration of a sum type, or data structure that contains one of its
internally declared members. Each `<union_member>` is named by an identifier, optionally followed by
a number of comma separated types delimited by parenthesis.

### Instantiation

```ebnf
<union_instantiation> ::= <ident> "::" <ident> "(" [<expr> ("," <expr>)* [","]] ")" ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<expr>`](../expressions.md)

The `<union_instantiation>` instantiates, or creates, the sum type. This consists of the union's
identifier, followed by the member's identifier, followed by an optional comma separated list of
expressions.

Behavior of instantiation is defined in the [data location rule](../../semantics/data-locations.md).

### Union Pattern

```ebnf
<union_pattern> ::= <ident> "::" <ident> ;
```

The `<union_pattern>` is a pattern consisting of the union's name and a member's name separated by a
double colon.

### Pattern Match

```ebnf
<pattern_match> ::= <ident> "matches" <union_pattern> ;
```
