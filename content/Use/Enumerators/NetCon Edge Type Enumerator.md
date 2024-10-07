---
title: NetCon Edge Type Enumerator
description: 
permalink: 
aliases: 
draft: false
date: 2024-10-02
tags: 
---
# NetCon Edge Type Enumerator

Enumerator encoding the edge types as used in NetCon.
The definition and contents of the table is standard and should not be altered.

| EdgeType | EdgeTypeValue | Description |
| -------: | ------------- | ----------- |
| 0        | Node     | Originated from a point asset. FromId and ToId will be the same (a loop). |
| 1        | Link     | Originated from a line asset. FromId and ToId cannot be the same (an edge). |
| 2        | Terminal | Generated between point and line asset for point asset that needs terminals. FromId and ToId cannot be the same (an edge, without geometry). |

