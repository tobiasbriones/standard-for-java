# Draft

I'll write points I come out with here to start documenting the standard.

## Motivation

Java apps are very stable and have a good ecosystem, so I use Java for those
use cases so that I will be able to keep writing Java apps and have minimum
maintenance costs.

In addition to be a stable language, Java use cases are for boring apps like
enterprise systems, that is, cheap software that works well with the OOP
paradigm and general purpose languages.

Java is best qualified for these use cases in general and for me than any other
popular general-purpose language because the tradeoffs among features, breaking
changes, maintainability, etc., are well-balanced in the Java ecosystem. 

## Points

- Don't use final for local variables as it should be the default so skip it 
  and use effectively final instead. Mostly everything must be final by 
  default, but it's more wrong to copy the `final` boilerplate 100% of the 
  time than using effectively final.
- Never use `final` on end-user classes like executable modules or tests 
  that will never be imported into a different app. `final` should be the 
  default for classes too, so is the same as the "effectively final" point. 
  If we remove the `final` modifier from all classes then we don't have the 
  advantage of effectively final for local variables, so only apply this 
  point to end classes. Public classes are more vulnerable to be extended, 
  so add `final` to all public classes, but make `package-private` classes 
  inside packages, so we take advantage of this point. If we remove `final` 
  from public classes that also leads the user think they should extend it. 
  Use `final` on all utility classes too, even if they are not public.
- Never use the LHS variable type when using `new` on the RHS.
- Try to use type inference most of the time.
