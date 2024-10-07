---
title: Wildcards
description: 
permalink: 
aliases: 
draft: false
date: 2024-10-01
tags: 
---
# Wildcards

Some parameters can be supplied as an exact string value as well as a pattern supporting wildcards. The wildcard pattern works the same way as the Microsoft operating system supports file search: '?' must match one character, '\*' can match any character.
In addition, the comma ',' can be used to supply a list of values.

For example, this is denoted by the name of the parameter, e.g. [[./Parameters/AssetTableNamePattern|AssetTableNamePattern]] is the string or pattern that must match the `AssetTableName`. 

Typically, the search with the exact value may be faster than the wildcard matching, but it is tried to evaluate the wildcards to possible values before starting the search.

In addition, an overall search parameter [[./Parameters/WildCardAsRegex|WildCardAsRegex]] parameter can be provided which will change the type of pattern matching that is done.
If this set to `true` than regex wildcards can be used instead of the '?', '\*' en ',' descrived above.
NetCon uses the [dotNet regex syntax](https://learn.microsoft.com/en-us/dotnet/standard/base-types/regular-expressions).

The default it simple wildcard matching, and you can override that by providing the parameter [[./Parameters/WildCardAsRegex|WildCardAsRegex]].
Also you can override the default for all [[./NetCon API Calls|NetCon API Calls]] with [[./Default parameters in the API|Default parameters in the API]].
