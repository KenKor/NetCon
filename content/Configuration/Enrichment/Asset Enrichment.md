---
title: Asset Enrichment
description: 
permalink: 
aliases: 
draft: false
date: 2024-10-01
tags: 
---
# Asset Enrichment

For each collection that is referenced by `AssetTableName` in the connection model, one can specify additional attributes that will be injected last minuted in the trace results.
For example, one can fetch the yearly power consumption of a service point.
Or, for a telecoms network, the state of a modem.
Or, for a cable, the build year.

In order to configure last minute data enrichment for assets, create a business collection with the name: `NetConAsset <asset_table_name>` where \<asset_table_name> matches the name refered by in the NetConConnection table.

The business collection that provides enrichment data should have its key field, often `id`, of type `long`, as the first field.
Besides that, there can be 1-n additional fields specified. Supported types are string, numeric types, date time or time span.

