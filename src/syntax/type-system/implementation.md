## Implementation

Implementation blocks enable method-call syntax.

### Implementation Block

```ebnf
<impl_block> ::=
    "impl" <ident> [<type_parameters>] [":" <ident> [<type_parameters>]] "{"
        (
            | <function_assignment>
            | <constant_assignment>
            | <type_assignment>
        )*
    "}"
```

Dependencies:

- [`<ident>`](../identifiers.md)
- [`<type_parameters>`](generics.md#type-parameters)
- [`<function_assignment>`](function-types.md#assignment)
- [`<constant_assignment>`](../comptime/constants.md)
- [`<type_assignment>`](assignment.md#assignment)

The `<impl_block>` is the implementation block for a given type. The type identifier is optionally
followed by type parameters then optionally followed by a "for" clause. The "for" clause contains
trait identifiers and optional type parameters for the traits. Followed by this is a list of
function, constant, and type assignments delimited by curly braces.
