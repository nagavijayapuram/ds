# ds
ds is the programming language geared for distributed systems

## laal
lal stands for "language atop (or using) another language"

It can be implemented using (or atop) any of these languages -
1. C/C++
2. Rust
3. Golang
4. Node
5. Java
6. Scala
7. Ruby
8. Python

*Note*: A language that provides metaprogramming feature is recommended

## Features
- () is the root object
- person1 = ().named("person") # yields the named object called person1
- person1 = person1.set(name:"joe", age:17) # person1 object now has two data fields
- person2 = ().named("person2") # yields the named object called person2
- person2 = person2.set(name:"joe", age:19) # person2 object now has two data fields
- person3 = ().named("person3") # yields the named object called person3
- person3 = person3.set(name:"joe", age:23) # person3 object now has two data fields
- person2.listen(person1) # person2 listens to state changes of person1
- person2.emit(person3) # person2 informs state changes to person3
- add = do(n1, n2) {n1 + n2} # a function that adds two numbers; do is reserved keyword, but can be redefined  
- person2.set(fn: add) # person2 is now enhanced; fn is reserved keyword, but can be redefined

- Each object is meant to do a very specific task on a data particle (quantum of data)
- Upon doing the task it quickly exits
- Before exiting it preserves the result in a data store
- The data store itself is an object and has its own listeners
- One of the listeners picks up the next task from the chain of tasks
- Objects come and go; this is for scalability
- Some objects are schedulers; some others are monitors; some are both schedulers and monitors
- The data in the data store goes through transformation as needed by the use cases -
  - filtering (aka contraction based on a boolean function)
  - transformation
    - lesser number of fields (like the filtering above)
    - same set of fields (but in a different mould based on a function)
    - more number of fields (based on a function)

- The collation of data stores is a larger data store; can be as tiny or as large depending on the use case; well, generally huge in case of distributed systems

- The objects are open in the sense the data fields and functions within the objects can be expanded, modified or contracted at any time; the overseer (yet another object) exercises control on what goes in/out/modified by way of security/control features (rules - yet another object)
 
- Objects behave like threads or processes when called upon to do something based on the functions it has (added from time to time)
