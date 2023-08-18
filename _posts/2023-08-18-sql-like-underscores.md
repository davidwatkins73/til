---
title: "Underscores in SQL Like statements"
date: 2023-08-18
---

# Another Title ?

We often use undescores when creating public indentifiers in our application.
Typically we have a column called something like `EXTERNAL_ID` and it would look like:

**Table :: foo**

id  | ... | external_id 
--- | --- | ---
1 | ... | SERVICE_THING_A
2 | ... | SERVICE_THING_B
3 | ... | SOMETHING_ELSE
4 | ... |  Service Config

I wrote a bit of code that looked like:

`select * from foo where external_id like 'SERVICE_%'`

When I executed the query it brought back rows 1,2 (no surprise) and 4 (surprised).

A bit of digging revealed that the underscore character acts as a single character wildcard [^1].

[^1]: For example: [SQL Wildcards](https://www.w3schools.com/sql/sql_wildcards.asp).



 

