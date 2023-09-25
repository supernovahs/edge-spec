## Operators

Operators are syntax sugar over a narrow range of trait functions.

### Binary

```ebnf
<arithmetic_binary_operator> ::=
    | "+" | "+="
    | "-" | "-="
    | "*" | "*="
    | "/" | "/="
    | "%" | "%="
    | "**" | "**=" ;
<bitwise_binary_operator> ::=
    | "|" | "|="
    | ">>" | ">>="
    | "<<" | "<<="
    | "&" | "&="
    | "^" | "^=" ;

<logical_binary_operator> ::=
    | "=="
    | "!="
    | "&&"
    | "||"
    | ">" | ">="
    | "<" | "<=" ;

<binary_operator> ::=
    | <arithmetic_binary_operator>
    | <bitwise_binary_operator>
    | <logical_binary_operator> ;
```

### Unary

```ebnf
<arithmetic_unary_operator> ::= "-" ;

<bitwise_unary_operator> ::= "~" ;

<logical_unary_operator> ::= "!" ;

<unary_operator> ::=
    | <arithmetic_unary_operator>
    | <bitwise_unary_operator>
    | <logical_unary_operator> ;
```
