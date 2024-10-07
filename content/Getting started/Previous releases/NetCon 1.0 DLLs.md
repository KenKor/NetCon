---
title: NetCon 1.0 DLLs
description: 
permalink: 
aliases: 
draft: false
date: 2024-10-01
tags: 
---
[[../Download and Install NetCon|previous]]
# NetCon 1.0 DLLs

For different versions of GSA or Spatial Workshop, different NetCon DLLs are available.

For configuration with 'desktop': GSA Ultimate or Spatial Workshop Ultimate;

- NetCon DLLs for desktop:
  - NetworkAggregationFeatureSource.dll _will be renamed to NetworkReductionFeatureSource_
  - NetworkClusteringFeatureSource.dll
  - NodeMapperFeatureSouce.dll
  - ZeroFormatter.dll
  - ZeroFormatter.Interfaces.dll

- For ETL-batch processing, materialized tracing and the transform task with 'server': GSA Warehouse or Spatial Warehouse. These server tasks are hosted in the GSA Server or XY server respectively, from here on called 'the server.'

- NetCon DLLs for server:
  - NetworkAggregationFeatureSource.dll _will be renamed to NetworkReductionFeatureSource_
  - NetworkAggregatorSyncTask.dll _will be renamed to NetworkReductionSyncTask_
  - NetworkClusteringFeatureSource.dll
  - NodeMapperFeatureSouce.dll
  - ZeroFormatter.dll
  - ZeroFormatter.Interfaces.dll
  - SpatialWarehouseTimestampTask.dll
