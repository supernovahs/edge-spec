## Function Types

The function type is a type composed of input and output types.

### Signature

```ebnf
<function_signature> ::= <type_signature> "->" <type_signature> ;
```

Dependencies:

- [`<type_signature>`](assignment.md#signature)

The `<function_signature>` consists of an input type signature and an output type signature,
separated by an arrow.

> Note: `<type_signature>` also contains a tuple signature, therefore a function with multiple
> inputs and outputs is implicitly operating on a tuple.

### Declaration

```ebnf
<function_declaration> ::= 
    "fn" <ident> "("
        [(<ident> ":" <type_signature>) ("," <ident> ":" <type_signature>)* [","]]
    ")" ["->" "(" <type_signature> ("," <type_signature>)* [","] ")"] ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<type_signature>`](assignment.md#signature)

### Assignment

```ebnf
<function_assignment> ::= <function_declaration> <code_block> ;
```

Dependencies:

- [`<code_block>`](../control-flow/code-block.md#declaration)

The `<function_assignment>` is defined as the "fn" keyword followed by its identifier, followed
by optional comma separated pairs of identifiers and type signatures, delimited by parenthesis, then
optionally followed by an arrow and a list of comma separated return types signatures delimited by
parenthesis, then finally the code block of the function body.

#### Arrow Functions

```ebnf
<arrow_function> ::= (<ident> | ("(" <ident> ("," <ident>)* [","] ")")) "=>" <code_block> ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<code_block>`](../control-flow/code-block.md)

The `<arrow_function>` is defined as either a single identifier or a comma separated,
parenthesis delimited list of identifiers, followed by the "=>" bigram, followed by a code block.

### Call

```ebnf
<function_call> ::= <ident> "(" [<expr> ("," <expr>) [","]] ")" ;
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<expr>`](../expressions.md)

The `<function_call>` is an identifier followed by a comma separated list of expressions delimited
by parenthesis.

### Semantics

> todo
