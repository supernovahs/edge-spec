## Contract Objects

Contract objects serve as an object-like interface to contract constructs.

### Declaration

```ebnf
<contract_declaration> ::=
    "contract" <ident> [":" <ident> ("&" <ident>)*] "{"
        [<ident> ":" <type_signature> ("," <ident> ":" <type_signature>)* [","]]
    "}" ;
```

> TODO: finish
