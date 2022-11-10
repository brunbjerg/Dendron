---
id: aze24cxz854zt4nvvefa6zl
title: Chapter 2 - Modules Packages and Data Type Concepts
desc: ''
updated: 1668076238521
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


