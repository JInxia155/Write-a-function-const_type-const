# Write-a-function-const_type-const
Write a function const_type : const


Download Link :https://programming.engineering/product/write-a-function-const_type-const/

Problem Background

Problem

• Write a function const_type : const —> exp_type that gives the expression type (exp_type) for each constant in Cmm.

• Write a function typed_exp_of_untyped_exp : (string * declarable_type) list —> (untyped_monop, untyped_binop) exp —> ( (typed_monop, typed_binop) exp * exp_type) option that is given a type environment supplying the declarable_type of a variable of a given name, and an untyped expression. It returns the translation of the untyped expression into a type-checked typed expression paired with its type, assuming such a translation is possible. The tranlation is done as follows: O If the untyped expression is a constant, the resulting typed expression is the same constant, and its type is given by const_type. O If the untyped expression is a variable, the resulting typed expression is the same variable, and its type is looked up in the given type environment, provided it does not have array type or function type. O If the untyped expression is an expression for an array element (a [e]), check that the array name is the name of a variable of an array type. If it is, translate the index expression (e) to a typed expression, and promote that to type int. Return the typed expression that is the array expression with the given array name, and the promoted type expression for the index, paired with the type for the elements in the array. O If the expression is the application of a monadic, binary or relational operator, first translate the arguments, then find the maximum of the types of the arguments, find the typed operator among the overloaded variants of the given untyped operator with the least input type to which that maximum can be promoted, promote all arguments to that type, apply the typed version of the operator to the promoted arguements to get the needed typed expression, which then is the translation of the given untyped expression, and return that typed expression paired with the output type of the operator. (Note that strings are represented as arrays containing char elements.) O If the expression is the application of a logical operator, i.e. && or II, translate the arguments, check that they have boolean type, reapply the logical operator to the typed versions of the arguments to get the typed translation of the original expression, and return this typed expression paired with the type of booleans. O If the expression is a function call

f(e.,•.•,en)

), look up the signature of the function in the environment to get the types of the input arguments and the return type of the function. Translate the untyped arguments into the typed versions, and then promote them as needed to have the required input type given by the function type signature. Apply the function to the resulting list of typed arguments and return the resulting typed expression paired with the return type of the function.

Note: • ► You will be given in Plsolutions the functions from the cmm_promote and cmm_overload questions:
Solution
