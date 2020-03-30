# Let and Const
* `let` and `const` are alternatives to var when declaring variables
* `let` is block-scoped instead of lexically scoped to a function
* `let` is hoisted to the top of the block, while `var` declarations are hoisted to top of the function
* "Temporal Dead Zone" -- TDZ for short
	* Starts at the beginning of the block where `let foo` was declared
	* Ends where the `let foo` statement was placed in user code (hoisiting is irrelevant here)
	* Attempts to access or assign to foo within the TDZ (before the let foo statement is reached) result in an error
	* Helps prevent mysterious bugs when a variable is manipulated before its declaration is reached
* `const` is also block-scoped, hoisted, and constrained by TDZ semantics
* `const` variables must be declared using an initializer, `const foo = 'bar'`
* Assigning to `const` after initialization fails silently (or loudly -- with an exception -- under strict mode)
* `const` variables don’t make the assigned value immutable
* `const foo = { bar: 'baz' }` means foo will always reference the right-hand side object
* `const foo = { bar: 'baz' }; foo.bar = 'boo'` won't throw
* Declaration of a variable by the same name will throw
* Meant to fix mistakes where you reassign a variable and lose a reference that was passed along somewhere else
* In ES6, functions are block scoped
* Prevents leaking block-scoped secrets through hoisting, `{ let _foo = 'secret', bar = () => _foo; }`
* Doesn't break user code in most situations, and typically what you wanted anyways
* Read ES6 Let, Const and the “Temporal Dead Zone” (TDZ) in Depth
