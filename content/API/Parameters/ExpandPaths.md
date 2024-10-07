---
title: ExpandPaths
description: Enum that determines what to do with the results. '-1' = only take connections (fastest). '0' = expand the paths fully (default choice). '1' = expand the paths and sort them in ascending reading order (per paths, duplicates omitted, slowest). '2' = return paths and set previousid to the id other paths if in the results, if applicable.
Type: integer
Order: 999
Mandatory: false
permalink: 
aliases: 
draft: false
date: 2024-10-02
tags:
  - ApiParameter
  - ExpandPaths
  - NetCon2
---
# ExpandPaths

Type of: _integer_
Unique: __

Enum that determines what to do with the results. '-1' = only take connections (fastest). '0' = expand the paths fully (default choice). '1' = expand the paths and sort them in ascending reading order (per paths, duplicates omitted, slowest). '2' = return paths and set previousid to the id other paths if in the results, if applicable.

Note that in the first version of NetCon this parameter used to be a boolean.