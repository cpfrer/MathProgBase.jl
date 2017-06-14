# Solver Interface

```@meta
CurrentModule = MathProgBase
```

```@docs
AbstractMathProgModel
AbstractMathProgSolver
```

## Basic Methods

```@docs
optimize!
freemodel!
```

## Variables

```@docs
VariableReference
candelete(::AbstractMathProgModel,::VariableReference)
isvalid(::AbstractMathProgModel,::VariableReference)
delete!(::AbstractMathProgModel,::VariableReference)
addvariables!
addvariable!
```

## Constraints

How to add constraints.
```@docs
ConstraintReference
candelete(::AbstractMathProgModel,::ConstraintReference)
isvalid(::AbstractMathProgModel,::ConstraintReference)
delete!(::AbstractMathProgModel,::ConstraintReference)
addconstraint!
```

## Sets



List of sets.
```@docs
NonNegative
NonPositive
Zero
Interval
Integers
Binaries
```

## Attributes

These are used to get and set properties of the model.

```@docs
AbstractAttribute
cangetattribute
getattribute
cansetattribute
setattribute!
```

### Scalar Attributes

```@docs
ObjectiveValue
ObjectiveBound
RelativeGap
SolveTime
Sense
SimplexIterations
BarrierIterations
NodeCount
RawSolver
ResultCount
```

### Variable Attributes

These attributes are associated with variables. Calls to `getattribute` and `setattribute!` should include a single `VariableReference` or a vector of `VariableReference` objects.

```@docs
VariableStart
VariableLowerBoundDualStart
VariableUpperBoundDualStart
VariableLowerBound
VariableUpperBound
VariablePrimal
VariableLowerBoundDual
VariableUpperBoundDual
```


## Termination Status

The `TerminationStatus` attribute is meant to explain the reason why the solver stopped executing. The value of the attribute is of type `TerminationStatusCode`.

```@docs
TerminationStatusCode
```