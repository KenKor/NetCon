---
title: Specifcation Enrichment
description: 
permalink: 
aliases: 
draft: true
date: 2024-10-01
tags: 
---
# Specifcation Enrichment

For each items that occurs in the `Specification` field in the connection model, one can specify additional attributes that will become part of that specifaction.

For example, if the specification is '4637', one can specify a type that changes this to 'id=4637,numberofcores=4'.
Another example is that 'protection.id=777,diameter.id=7' is changed to 'protection.id=777,protection.material="HDPE",diameter.id=7,diameter.inner=900'.

The specification enrichment data is read on startup of the NetConTrace feature source and is stored only once.

In order to configure data enrichment for asset hierachy items, create a business collection with the name: `NetConSpecification <asset_table_name>` where \<asset_table_name> matches the name refered by in the NetConConnection table in the asset table field. If more than one specification tables are in use for a single table, the tables should be named `NetConSpecification <asset_table_name> <specification>`.

_ToDo: Note that looking up enriched information for multiple specifications is not yet implemented. It is supported to have them stored already._

In the example above, one could have two tables named `NetConSpecification gas_pipe protection` and `NetConSpecification gas_pipe diameter`.

The business collection that provides enrichment data should have its key field first, often `id` (which must the name used in the asset hierarchy), of type `integer`.
Besides that, there can be 1-n additional fields specified. Supported types are string, numeric types, date time or time span.

