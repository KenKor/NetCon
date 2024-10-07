---
title: Data Enrichment
description: 
permalink: 
aliases: 
draft: false
date: 2024-10-01
tags: 
---
# Data Enrichment

The NetCon models can work with data which is outside of its tables, by following a certain convention in business collection naming.
Enrichment is handled by the NetConTrace feature source, so for this to work, you must add this to your configuration (or use the template that is provided).

For specifications (typically references to type tables) and asset hiearchy objects (for example rail or substation information), this information is read when the NetConTrace feature source starts up.
For additional asset information, this information is read when Trace results are produced (either by expressions or the TraceAPI).

NetCon support three types of enrichment:

* [[./Specifcation Enrichment|Specifcation Enrichment]]
* [[./Asset Hierarchy Enrichment|Asset Hierarchy Enrichment]]
* [[./Asset Enrichment|Asset Enrichment]]
