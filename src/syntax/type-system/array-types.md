## Array Types

The array type is a list of elements of a single type.

### Signature

```ebnf
<array_signature> ::= "[" <type_signature> ";" <expr> "]" ;
```

The `<array_signature>` consists of a type signature and expression separated by a colon, delimited
by brackets.

### Instantiation

```ebnf
<array_instantiation> ::= [<data_location>] "[" <expr> ("," <expr>)* [","] "]" ;
```

The `<array_instantiation>` is an optional data location annotation followed by a comma separated
list of expressions delimited by brackets.

### Element Access

```ebnf
<array_element_access> ::= <ident> "[" <expr> [":" <expr>] "]" ;
```

The `<array_element_access>` is the array's identifier followed a bracket-delimited expression and
optionally a second expression, colon separated.

### Semantics

#### Instantiation

Instantiation semantics depend on the data location.

In map data locations, the array is 

#### Access

Array element access depends on whether the second expression is included. If a single expression is
inside the access brackets, the single element is returned from the array. If a second expression
follows the first with a colon in between, a pointer of the same data location is returned. The type
of the new array pointer is the same type but the size is now the size of the second expression's
value minus the first expression's value. If the index values are known at compile time and are
greater than or equal to the array's length, a compiler error is thrown, else a bounds check against
the array's length is added into the runtime bytecode.
