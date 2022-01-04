# Database Design

## Learning Outcomes

* Know how to make an ERD
* Understand what an entity is
* Understand relationships and how to represent them
* Develop intuition for how to turn business requirements into a database schema
* Know a few go-to column types to solve common problems
* Understand how primary and foreign keys fit into a design
* Become familiar with the most ubiquitous naming conventions

## Overview

* How do you design a database conceptually?
  * What information do you want to persist?
  * What kind of questions do you want to be able to answer about your data?
  * What are your entities?
  * What are their relationships to one another?
  * ERDs (entity relationship diagrams)
* How do you design a database mechanically?
  * **Tables**
    * What will your primary key be?
    * Will you have any foreign keys?
    * Naming conventions (plural, snake case, primary/foreign keys)
  * **Columns**
    * What columns should each table have?
    * What type should each column be?
    * Is it allowed to be null?
    * Should it have a default value?



## Conceptual Design

* What are your entities?
* What attributes should they have?
* What are their relationships?

## Technical Design

* What are your tables?
  * Usually pretty easy: A table for every entity!
  * You might have extra tables for many-to-many relationships, which you may or may not think of as entities
  * Naming conventions: Plural, snake_case
* What are your columns?
  * One of them had better be a primary key
  * What is each column's type? https://www.postgresql.org/docs/9.5/datatype.html
  * Are any of those foreign keys?
  * Can they be `NULL`?
  * Should they have a default value?
  * Naming conventions:
    * Foreign keys are the table name (but singular) followed by `_id`
    * Also snake case
