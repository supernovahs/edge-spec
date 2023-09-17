## Syntax

Conceptually, all EVM contracts are single-entry point executables and at compile time, __lang__
programs are no different.

Other languages have established a convention of contract-as-an-object, treating contracts as
stateful objects, optionally with inheritance to separate and modularize interfaces. We support this
abstraction, but with a clear path to the underlying executable for informational and debugging
purposes using meta-programming techniques detailed under the
[compile time code execution](#compile-time-code-execution) section.

Treating EVM contracts as single entry point executables aligns the __lang__ program model to the
general purpose language model where the single 'main' function serves as the entry point which
handles dispatching internal functions.
