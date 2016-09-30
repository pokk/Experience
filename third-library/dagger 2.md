# Dagger 2

Provider vs Inject

There are two way for providing objects to,
1. Declare a __method with return data type__ in the component interface.
2. Directly using __@Inject__ or __@Provider__ annotation in front of the method you wanna provide and using the same @Scope as the component.

** Provider : Using the __@Inject__ or __@Provider__ in front of the method.

** Injected : Using the __@Inject__ in front of the variable.

---
### Role of each keyword
Module: A factory to provide vary methods. You might call it "Injector".
<br>
Component: A bridge between a module and injects.
<br>
Injects: Two role of it, one is _Inject_ when it's front of a variable, the other one is Provider when it's front of a _method_.

Providers: Just provide an object.

Singleton: Here just the same as singleton pattern.

Scope:

---

### Three ways for injecting
---
1. Inject to __*Constructor*__
2. Inject to __*Public Variable*__
3. Inject to __*Method*__
