---
title: Asset Hierarchy Enrichment
description: 
permalink: 
aliases: 
draft: false
date: 2024-10-01
tags: 
---
# Asset Hierarchy Enrichment

For each items that occurs in the `AssetHierarchy` in the connection model, one can specify additional attributes that will become part of that asset hierarchy reference.

For example, if the asset hierarchy is 'rail.id=123, substation.id=456', one can specify a system for the rail and a name for the substation. With those enrichments, the asset hierarchy changes to 'rail.id=123, rail.system="lowersidebus", substation.id=456, substation.name="Holyfield"'.

The asset hierarchy enrichment data is read on startup of the NetConTrace feature source and is stored only once.

In order to configure data enrichment for asset hierachy items, create a business collection with the name: `NetConAssetHierchy <asset_table_name>` where \<asset_table_name> matches the name refered by in the NetConConnection table.

The business collection that provides enrichment data should have its key field first, often `id` (which must the name used in the asset hierarchy), of type `integer`.
Besides that, there can be 1-n additional fields specified. Supported types are string, numeric types, date time or time span.

