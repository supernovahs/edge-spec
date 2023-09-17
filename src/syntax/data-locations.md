## Data Locations

```ebnf
<storage_pointer> ::= "&s" ;
<transient_storage_pointer> ::= "&t" ;
<memory_pointer> ::= "&m" ;
<calldata_pointer> ::= "&cd" ;
<returndata_pointer> ::= "&rd" ;
<internal_code_pointer> ::= "&ic" ;
<external_code_pointer> ::= "&ec" ;

<data_location> ::=
    | <storage_pointer>
    | <transient_storage_pointer>
    | <memory_pointer>
    | <calldata_pointer>
    | <returndata_pointer>
    | <internal_code_pointer>
    | <external_code_pointer> ;
```

The `<location>` is a data location annotation indicating to which data location a pointer's data
exists. We define seven distinct annotations for data location pointers. This is a divergence from
general purpose programming languages to more accurately represent the EVM execution environment.

- `&s` persistent storage
- `&t` transient storage
- `&m` memory
- `&cd` calldata
- `&rd` returndata
- `&ic` internal (local) code
- `&ec` external code

Semantics are beyond the scope of the syntax specification, for more on their behavior see the
[data location semantics document](../semantics/data-locations.md).
