---
id: j9md8wupr0clj9x1609fgdi
title: Dendron - User Guide
desc: ''
updated: 1668269848097
created: 1668268527614
---
Here I will keep notes and explore concepts that will allow me to use Dendron more efficiently.



## Concepts that are good to know
Frontmatter: 
* Extra information; metadata; structure used is called YAML
* It will not show up in the markdown file itself

Workspace:
* Collection of one or more vaults
* This folder contains all the files necessary to manage your information in Dendron
* Important: This might be the concept that I know the least about. 

Vaults:
* A vault is simply a collection of notes, files and configuration files

Structured like this:
* Workspace
    * Valut.main
        * foo.md
        * foo.one.md
        * foo.two.md
    * vault.secret
        * secret.one.md
        * secret.two.md

Good to know! 

Hierarchies: 
* Dendron: You can refactor notes and hierarchies
* Domain is the root of the hierarchy

Remember templates for later.

Schema: 
* Can apply consistent structure to all your notes
* Optional type system, very cool
* A hierarchy for the hierarchy itself

{name}.schema.yaml

Example of a three level hierarchy
- id: cli
  desc: command line interface reference
  parent: root
  namespace: true
  children:
    - cmd
    - env
- id: env
  desc: variables relevant for command
- id: cmd
  desc: subcommands 
  namespace: true

This seems very useful. Careful not to overhhelm yourself now <3 You are getting a lot of information at the moment.

Stubs
Stubs are notes that do not exist but that you might want to create. They will show up as suggestions in lookup results. There are two reasons whu these suggested notes might show up. 
* They are the uncreated parent of a note deeper in the hierarcht
* They are possible notes according to the schema
* Plus sign means that the note does not exist yet. i.e a stub

Pods:
* Pods are used to import and export notes


Command palette:
* Native to VS COde
* Run dendron commands


Look up bar:
* Ctrl + L: Used to look up files and create new files


Glob patterns: 
* Lower kebab case is recommended in your files
* dendron-user-guide should have been the name of this file
* Dendron will create a title from the kebab style that will capitalize the first letter and the once comming after the dash in the file name.

Slug: Human readable part of URL

