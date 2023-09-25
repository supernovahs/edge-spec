## Function Types

The function type is a type composed of input and output types.

### Signature

```ebnf
<function_signature> ::= <type_signature> "->" <type_signature> ;
```

The `<function_signature>` consists of an input type signature and an output type signature,
separated by an arrow.

> Note: `<type_signature>` also contains a tuple signature, therefore a function with multiple
> inputs and outputs is implicitly operating on a tuple.

### Assignment

```ebnf
<function_assignment> ::=
    "fn" <ident> "("
        [(<ident> ":" <type_signature>) ("," <ident> ":" <type_signature>)* [","]]
    ")" ["->" "(" <type_signature> ("," <type_signature>)* [","] ")"]
    <code_block> ;
```

The core `<function_assignment>` is defined as the "fn" keyword followed by its identifier, followed
by optional comma separated pairs of identifiers and type signatures, delimited by parenthesis, then
optionally followed by an arrow and a list of comma separated return types signatures delimited by
parenthesis, then finally the code block of the function body.
