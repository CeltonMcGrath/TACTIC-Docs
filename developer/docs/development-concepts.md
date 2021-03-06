# Development Concepts

## Introduction

The term "asset" is used often, and has many different meanings in
different industries and even in different areas of the same production
facility. In TACTIC, an asset is an *atomic entity* with metadata and
files associated with it. To avoid confusion, the TACTIC assets are
called "searchable objects," shortened to *sObjects*.

## sTypes and sObjects

sObjects are the atomic entities (or assets) that TACTIC uses to
manipulate data and check in files. An sObject can be any entity
required in a production. Examples of sObjects include shots, textures,
users, tasks, production notes, and so on.

Every sObject must belong to a search type, also known as sType. *Search
types* are a set of unique string entities that serve to classify all
variations of sObjects. Search types are registered in the
"search\_object" table in the "sthpw" database. This table defines the
properties for each search type, and is used to ensure that sObjects
adheres to their search type properties. For instance, in a custom
project, you may have a custom/shot sType created for shot. Once it’s
registered, you can add shot entries in the shot table that it
generates. The shot entries are the shot sObjects.

It is technically possible to store data on assets anywhere, but the
TACTIC approach is to use an SQL database so sObject data can be tracked
in the database and rules can be enforced. In TACTIC, each sObject is
represented as a table in the database. All sObjects for your project
are stored in a project-wide database and cross-project sObjects (for
example, those related to users) are stored in the main TACTIC database
"sthpw."
