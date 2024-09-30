---
title: AssetHierarchyPattern
description: Comma separated list of AssetHierarchy pairs. Every pair looks like 'name=value', e.g. "substation.id=3". The pairs can be in any order, e.g. "substation.id=3,installation.id=17" is the same as "installation.id=17,substation.id=3". For a match, only one of the items needs to match, so if you search for "installation.id=17, installation.id=21, installation.id=43' this will match the aforementioned List that also contains "substation.id=3".
Type: string
Order: 999
Mandatory: false
permalink: 
aliases: 
draft: true
date: 2024-09-30
tags:
  - ApiParameter
  - AssetHierarchyPattern
  - AssetHierarchy
---
# AssetHierarchyPattern

Type of: _string_
Unique: __

Comma separated list of AssetHierarchy pairs. Every pair looks like 'name=value', e.g. "substation.id=3". The pairs can be in any order, e.g. "substation.id=3,installation.id=17" is the same as "installation.id=17,substation.id=3". For a match, only one of the items needs to match, so if you search for "installation.id=17, installation.id=21, installation.id=43' this will match the aforementioned List that also contains "substation.id=3".
