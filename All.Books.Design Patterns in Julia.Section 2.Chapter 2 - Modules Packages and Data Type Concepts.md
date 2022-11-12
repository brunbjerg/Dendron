---
id: aze24cxz854zt4nvvefa6zl
title: Chapter 2 - Modules Packages and Data Type Concepts
desc: ''
updated: 1668182183167
created: 1667919195265
---

Datascience project: What I got. 
Data engineering: What I need for preprocessing
* Collection
* Cleaning
* Analysis
* Visualization (Important)

Model development, then model deployment. 

Data engineering and model development is interactive at the beginning but then usually gets automated. 

Webservice: Product gets a life cycle and then needs to be maintained. Technology stack, available programs, software, database etc. 

Enterprise systems are hooked up to different systems. Trading systems are connected to accounting systems, trade-settlements systems etc.

Handle data-in-rest and data-in-motion. 

Adapting to growth. Signs:
* I am scrolling to much! Important, scrolling up and down to understand what I am duringl 
* Too many variables created in between things and I am losing track of what they mean and their used
* Data structure is too complex. I was working on a data frame and have transformed it in ten different ways. I have lost track of which represents what I want. 
* I have many models and I have lost track of how each one was trained and what assumptions were made for each of those models.
* I cannot achive consistent results, code parts are all tweaked for a slighty different result.

### For a enterprise system:
* Application logic ts too complicated and there is a huge component performing too many functions.
* I cannot add new features without breaking existing ones. 
* I newly employed person cannot easily understand and work on the system

## Rethink strategy and refactor

## Namesspaces, modules and packagese
* Namespaces are ud=sed to logically separate fragments of source code so that they can be developed independently. Functions with the same name. Julia creates namespaces using modules and submodules. To manage distribution and dependencies modules are generally organized as packages. THere is a standard directory structure for Julia packages. Although the top level directory structure is well defined the programmer still has a lot of freedom in organizing source files. 

Topics
* Understanding and using namespaces 
* How to create modules and packages 
* How to create submodules
* How to organize files in a module


## Understanding namespaces
Names are important to avoid misconceptions and ambiguities. In programming we solve this by adding a prefix to distinguish two different meanings for a single word, we can just prefix the word with the respextive context. 

### Examples
* Pool: Facility.pool and Grouping.poop
* Vegetable. squash and sport. squash
* Electricity.current and liqiid.current

The predix is known as a namespace. Leaving no ambihuity.. In Julia we create namespaces using modules. 

Modules are created for the purpose of sharing and reuse. The best way to do this is by creating a package. Package contains:
* module definitions
* test scripts
* documentation
* data


## Organizing files in a module
* Coupling: Highly coupled functions should be placed in the same file. Doing so allows less context weitching when editing source files. For example, when you change the signature of a function, all callers of that function may need to be updated. Ideally, you would want to minimize the blast rafius and not have to change many files. 
* File size: Having more than a few hundred lines of code in a single file could be a warning sign. If the code inside the file is all tightly coupled, then it may be better to redesign the system to reduce coupling.
* Ordering: Julia loads the source files in the order in which you include them. As data types and utility functions are usually sjared, it is better to save them in a types.jl and utils.jl file respectively and include them at the beginning of the module.


# Managing package dependencies
Packages should preferably have a single objective since it makes them easier to reuse. 

## Topics
* Understanding the semantic versioning scheme
* Specifuing dependencies for Julia packages
* Avoiding circular dependencies

Semantic versioning conveys information about whether or not an update is breaking. Major version number of zero is special in that in it means that every release is breaking. 

### Specifing dependencies for Julia packages.

using and import keywords can be used to gauge dependencies. This information is stored in the Project.toml file. Mainfest.toml file contains more information about the complete dependency tree. 

Some files do not have a version number in the Manifest.tolm since they are released with the Julia binaries. Their version number is determined by the Julia version. 

This means that Calculator can work with all versions of SaferIntegers from 1.1.1 to the latest 1.x.y version. Mathematical notation: [1.1.1, 2,0,0[

The project.toml should be used to manage package dependencies. 

### Avoiding circular dependencies
* A depends on B and C
* C depends on D and E
* E depends on A

Problem: We have to test every packages that is dependent on A therefore all packages have to be tested.

### How to fix this?
The acyclic dependency principle states that dependencies between packages must be a directed acyclic graph (DAG) that is, the dependency graph must have no cycle. If we do see a cycle in the graph, then it is a sign of a design problem.

#### We need to refactor code
The code that is used in the node of the dependency tree should be put in a new file so that the upper and lower nodes that are both dependent on the code both refer to the same new file. 



# Designing abstract and concrete types
Julia's type system is the foundation of many of its language features, such as multiple dispatches. In this section, we will learn about both abstract types and concrete types, how to design and use them, and how they are different from other mainstream object-oriented programming languages. 

Topics 
* Designing abstract types
* Designing concrete types
* Understanding isa and <: operators
* Understanding the difference between abstract and concrete types


## Designing abstract types
Julia supports a hierarchy of abstract types. Abstract types are typically used to model real-world data concepts; for example, an Animal could be an abstract type for a cat or dog, and a Vehicle canbe an abstract type for a car, truck or bus. Being able to group types together and give the group a single name allows Julia programmers to apply generic code that is common to those types. Generic code to those types. 

Abstract types are often conveniently defined in a type hierarchy for a specigic domain. A parent child relationship between the types, technically an is-a-subtype-of relationship. Parent type is called supertype and child is called subtype.

Types can, unlike many other languages be defined without fields. For this reason, abstract types do not specify how data is actually stored in the memory. It may seem somewhat restrictive at first glance, but as we learn more about Julia, it will seem more natural when used in this design. As a result, abstract types are used solely to model behaciors for a set of objects rather than to specify how data is stored. Abstract types are used to model behavior of objects or set of objects. Inheriting in the square-rectangle case does not make sense, since square only has one field and rectangle has two. 


## A personal asset type hierarchy example.

Any is always a supertype. Top-level supertype. 

Associate abstract types with functions. 

### Defining functions for abstract types
Defining an error function can be a good idea. When concrete types are called later they will throw an error. Good point. 

## Interaction between objects
We are able to develop generic code going forward because we have the generic type and behaviors defined on them.

If we could not do this for abstract type we would have to develop a method for each combination of subtypes for the Property type. 

## Concrete types
A concrete type is used to define hwo data is organized. In Julia, there are two kinds of concrete types.
* Primitive type: Int, Float
* Composite type: Set of named fields, struct (good)

Primitive types carry pure bits. 

Initialize element by using a constructor. Simply meaning that the constructor takes the fieldnames as arguments. This is cool, stop questioning it never, just do it! Yes! 

Push through CRAP, critisism, rejection, assholes and peerpresure! Cool that you have remembered that. 

Composites are by default immutable. This means that their fields are not changable after the object is created. Immutability is good as it eliminates surprises when system behavior changes unexpectedly because of data modification. 

## Mutable or immutable? 
Why isn't everything mutable by default? 
* Immutable objects are easier to handle. Functions operating on data will always return consistent results. No surprises. 
* Mutable objects become difficult when multi-threading. 

Mutable structs lets us reuse allocated memory over and over again. 

## Supporting miltiple types using Union types
Sometimes, we need to support multiple types in a field. This can be done using a Union type, which is defined as a type that can accept any specified types. To define a Union type, we can just enclose the types within curly braces afer the Union keyword. 

Union is useful when we want to incorporate data types that come from different data type hierarchies. Extending types for example. Exotics items for example.

Give complex types a variable for example if you have a Union of types. We can keep adding things to the Union. Thereby easily incorporate new type in our system. This makes the code easier to maintain. 

Union{T, nothing}


## Working with type operators
<: is-a-subtype-of

isa checks a value against a type.

<: checks a type against a type

Both are useful for type checking. 