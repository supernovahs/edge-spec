## Built-In

Built-in functionality refers to functionality that is only available during the compiler runtime
and not the EVM runtime that is otherwise inaccessible through the language's syntax.

Macros contain their own syntax and semantics, however, comptime functionality and built-in
assistants cover most of the use cases for macros without leaving the language's native syntax.

### Types

#### `PrimitiveType`

```rs
type PrimitiveType;
```

#### `StructType`

```rs
type StructType;
```

#### `EnumType`

```rs
type EnumType;
```

#### `UnionType`

```rs
type UnionType;
```

#### `FunctionType`

```rs
type FunctionType;
```

#### `TypeInfo`

```rs
type TypeInfo =
    | Primitive(PrimitiveType)
    | Struct(StructType)
    | Enum(EnumType)
    | Union(UnionType)
    | Function(FunctionType);
```

### Functions

#### `@typeInfo`

```rs
@typeInfo(typeSignature) -> TypeInfo;
```

The `typeInfo` function takes a single
[`<type_signature>`](syntax/type-system/assignment.md#signature) as an argument and returns a union
of types, [`TypeInfo`](#typeinfo).

#### `@bitsize`

```rs
@bitsize(typeSignature) -> u256;
```

The `bitsize` function takes a single
[`<type_signature>`](syntax/type-system/assignment.md#signature) as an argument and returns an
integer indicating the bitsize of the underlying type.

#### `@fields`

```rs
@fields(structType) -> [T, N];
```

The `fields` function takes a single [`StructType`](#structtype) as an argument and returns an array
of type signatures of length `N` where `N` is the number of fields in the struct.

#### `@compilerError`

```rs
@compilerError(errorMessage);
```

The `compilerError` function takes a single string as an argument and throws an error at compile
time with the provided message.
